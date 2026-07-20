# Chapter 8 | Context Engineering: How Context Is Built, Compressed, and Forgotten

## One-sentence takeaway

**A larger Context Window does not mean AI automatically "remembers everything" or "cares about everything."**  
A strong system actively builds, prioritizes, and compresses context—this is called **Context Engineering**.

---

## 1. First clarify this: AI does not really have "memory"—it only sees the text included in this turn

Every model call is essentially a bundle of tokens:

```text
[System rules]
[Skills / tool instructions]
[Long-term memory summary]
[Course materials retrieved by RAG]
[Recent N turns of dialogue]
[Current user question]
        ↓
    Model generates
```

The model does **not** automatically know which part matters most.  
It simply runs attention over the whole token bundle, and middle sections are especially easy to ignore (see Section 4).

---

## 2. Context Construction

### The core question
> After giving AI 20 turns of dialogue, how does it know what deserves the most attention?

Answer: **It does not "figure it out" by itself. You—or the Harness—must assign priorities for it.**

### Common prioritization strategy (from highest to lowest)

| Priority | What goes here | Why |
|---|---|---|
| P0 | Current task goal + hard rules | Defines what must be accomplished in this run |
| P1 | Latest user request / latest tool output | The newest information is often the most relevant |
| P2 | Compressed decisions and constraints | Example: "Use Traditional Chinese" or "Do not leak answers" |
| P3 | High-relevance RAG hits | Evidence-based knowledge |
| P4 | Dialogue summary (not the full transcript) | Preserves flow without blowing up the window |
| P5 | Older raw messages | Drop them if possible, or keep only references |

### Practical techniques

1. **Structured sections**  
   Use explicit headings such as `## Goal` / `## Constraints` / `## Retrieved Docs` / `## Recent Turns`

2. **Put conclusions at the front and at the end**  
   Put the goal at the beginning; restate "Now do X" at the end (to counter Lost in the Middle)

3. **Pinning**  
   Keep key rules in the System prompt or a fixed prefix so they are never overwritten by summaries

4. **Relevance filtering**  
   If only 3 out of 20 turns are actually about "generating fraction questions," keep those 3 plus a summary

5. **Denoise tool output**  
   For long logs, extract the error lines or conclusion first; do not dump a full JSON blob into context

### Education example: how to build context after 20 tutoring turns

```text
[System] You are a Socratic math tutor for middle school students; in practice mode, do not give the final answer
[Pinned] Student: Xiaoming; weakness: fraction addition/subtraction; weekly goal: >80% accuracy
[Summary] First 15 turns summary: same-denominator questions are okay; stuck on common denominators
[RAG] Course material pp.42-44 on common-denominator steps (with examples)
[Recent] The most recent 3 raw turns (student's latest error)
[Ask] For the student's 1/3+1/4 attempt, guide the next step through questions
```

This way, the model understands that **the priority is guiding common-denominator reasoning, not restarting with small talk from the beginning.**

---

## 3. Context Compact

### What is it?
When the dialogue becomes long and tool output grows, you **compress older content into a short summary or state card** to free up room for new information.

### Why is it needed?
| Without compression | After compression |
|---|---|
| Tokens explode; expensive and slow | Cost stays manageable |
| More noise accumulates | Signal becomes clearer |
| Lost in the Middle becomes more likely | Key constraints are preserved |

### Common compression methods

| Method | How it works | Risk |
|---|---|---|
| **Sliding window** | Keep only the most recent K turns | Important earlier constraints may be lost |
| **Summary compression** | Use an LLM to summarize older turns | The summary may omit details or distort meaning |
| **State card** | Maintain `goal / constraints / progress / open_questions` | Requires good schema design |
| **Layered memory** | Hot memory (recent) / warm memory (summary) / cold memory (external storage) | More complex to implement |
| **Reference-based compression** | Keep only `filename + paragraph id` and expand when needed | Requires one extra retrieval step |

### Golden rules for Compact
1. **Non-compressible zone:** safety rules, hard user preferences, exam-mode switches  
2. **Compressible zone:** small talk, repeated explanations, verbose tool dumps  
3. **Compression must remain verifiable:** summaries should preserve both confirmed decisions and unresolved questions

### Example state card (worth memorizing)

```yaml
goal: Complete 10 practice questions on unlike-denominator addition/subtraction
constraints:
  - Practice mode; do not provide the final answer
  - Use Traditional Chinese
progress:
  - Same-denominator questions passed
  - Accuracy on finding common denominators is 40%
open_questions:
  - Does the student understand least common multiple?
last_error: Added numerator and denominator directly in 1/3+1/4
```

---

## 4. Lost in the Middle

### What is it?
Research and real-world practice both show that when important information sits in the **middle of a very long context**, model performance often gets worse.  
Models are usually more sensitive to the **beginning** and **end**, while the middle is easier to "see without really using."

### Why do interviewers like asking about it?
Because many people assume that "if the window is 200K, I can just stuff the entire textbook into it."  
**Fitting into context does not mean being used well.**

### How do you mitigate it?

| Strategy | How |
|---|---|
| Reorder placement | Put key constraints at the beginning; restate the task instruction at the end |
| Shorten the middle | Put only highly relevant RAG snippets in the middle, not entire chapters |
| Multi-pass retrieval | Use RAG Top-K instead of dumping the full corpus |
| Explicit citation | Say "Based on [CourseMaterial-3], point 2..." to force alignment |
| Break down the task | Summarize or extract key points first, then enter the answer loop |
| Evaluation | Run regression tests like "Did the answer cite the critical sentence from the middle?" |

### One-line rule to remember
> **Use the beginning for rules, the middle for refined evidence, and the end for the instruction.**

---

## 5. Full handling flow for a 20-turn conversation (memorize this)

```text
After each turn:
  1) Update the state card (goal / progress / constraints)
  2) If tokens exceed the threshold -> Context Compact (summarize older turns)
  3) When a new question arrives -> rebuild context:
        Pinned rules
      + State card
      + RAG (if external knowledge is needed)
      + A small number of recent raw turns
      + Current question (place it last)
  4) Send to the model
```

This is **Context Engineering**: not expecting the model to "remember on its own," but having the system continuously organize the desk for it.

---

## 6. Fast interview answers

### Q: When context is long, how does the model know what matters?
> Through structured construction and prioritization: pin rules, maintain a state card, filter by relevance, and place key instructions at both the beginning and the end to reduce lost-in-the-middle effects.

### Q: Can Context Compact cause important information to be lost?
> Yes, which is why you must separate non-compressible zones from compressible ones. After compression, preserve confirmed decisions and open questions, and expand from the source when necessary.

### Q: Why not just keep all 20 turns in full?
> Because it is expensive, slow, and noisy, and middle content is more likely to be ignored. Keeping the right state is better than keeping the full transcript.

---

## Quiz

1. What is Lost in the Middle, and how can you mitigate it?  
2. What usually belongs in the non-compressible zone of Context Compact?  
3. Explain in your own words: after 20 turns, how should context be rebuilt?

<details>
<summary>Suggested answers</summary>

1. Important information in the middle of long context is easier to ignore; put key items at both ends, shorten the middle, and use RAG Top-K  
2. Safety rules, hard preferences, mode switches, and confirmed key constraints  
3. State card + pinned rules + refined RAG + recent raw turns + current question placed last  

</details>

---

**Next lesson ->** [`03-ocr-and-rag.md`](03-ocr-and-rag.md)
