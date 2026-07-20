# Chapter 8 | Agent Loop, Harness, and Skills

## One-sentence takeaway

**The model is the brain; the Harness is the body; the Agent Loop is the breathing rhythm; Skills are reusable professional capability packs.**

---

## 1. Agent Loop

### What is it?
The repeated cycle an Agent goes through to complete a task. It is not just "ask once, answer once."

### Standard loop (must memorize)

```text
┌──────────────────────────────────────────────┐
│  1. Perceive  Read the goal, state, tool output │
│  2. Plan      Decide what to do next            │
│  3. Act       Call tools / write files / search │
│  4. Observe   Check what the tool returned      │
│  5. Reflect   Was it good enough? Retry?        │
│         ↓ Return to 1 if unfinished             │
│  6. Stop      Done or stop condition triggered  │
└──────────────────────────────────────────────┘
```

It is also often described as **ReAct** (Reason + Act) or **Think -> Tool -> Observe**.

### Stop conditions (very important)
| Condition | Example |
|---|---|
| Task succeeded | The quiz is generated and passes validation |
| Step limit reached | Maximum 20 steps to avoid infinite loops |
| Budget exhausted | Token or cost limit reached |
| Human required | A teacher must confirm a high-risk action |
| Repeated failure | The same error happens 3 times in a row -> stop and report |

### Education scenario example
```text
Goal: Generate 10 word problems about fractions for Xiaoming this week
Loop:
  -> Check Xiaoming's weak points (get_mastery)
  -> Use RAG to retrieve the lesson materials
  -> Generate 10 questions
  -> Automatically validate difficulty and knowledge-point tags
  -> Regenerate if quality is not acceptable
  -> Notify the teacher for review
  -> Stop
```

### Strong interview line
> "Agent Loop turns AI from a one-shot responder into an executable workflow. The key is having clear stop conditions and failure fallback logic; otherwise it just spins and burns budget."

---

## 2. Harness

### What is it?
The full system wrapped around the model that allows the Agent to run safely in the real world.  
The model does the reasoning; the **Harness handles constraints, tools, memory, permissions, logging, and retries**.

### Analogy
| Role | Analogy |
|---|---|
| LLM | The rider / the horse's raw power |
| Harness | The saddle, reins, protective gear, and map |
| Model without a Harness | A naked brain—capable of thinking, but impossible to control well |

### What does a Harness usually include?

```text
Harness
├── Tool Layer         Callable tools (search, DB, MCP)
├── Memory Layer       Short-term dialogue + long-term summaries / files
├── Policy / Guardrail Permissions, safety, prohibited actions
├── Orchestrator       Controls the loop, retries, parallel subtasks
├── Observability      Logs, traces, cost monitoring
└── Human Gate         Steps that require human approval
```

### Why is Harness discussed so much in 2026?
Because people realized that **models are stronger now, but product success depends even more on the quality of the Harness.**  
The same Claude or GPT can behave very differently depending on the Harness around it.

### How to explain it in an interview
> "Choosing a model is only half the story; the other half is the Harness—tool interfaces, permissions, memory compression, evaluation, and auditing. Education products especially need a strong Harness because the cost of teaching incorrectly or changing grades improperly is very high."

---

## 3. Skills

### What are they?
Reusable modules that package a specialized way of working, so an Agent can load them when needed instead of rewriting the Prompt from scratch every time.

### A Skill usually looks like this
```text
Skill: create_math_quiz
├── Description: when to use it, input/output format
├── Steps / checklist
├── Examples (few-shot)
├── Available tools
└── Quality criteria (difficulty distribution, must not leak answers, etc.)
```

### Skills vs Tools vs Prompt

| | Skills | Tools | One-off Prompt |
|---|---|---|---|
| Core nature | Reusable "professional workflow" | Executable API/function | A one-time instruction |
| Example | "Quiz creation skill", "Essay grading skill" | `search_rag()` | "Create 5 questions for me" |
| Value | Stable quality, maintainable | Actually performs actions | Flexible but drifts easily |

### Why do we need Skills?
- Stuffing a huge Prompt into context is expensive, slow, and still prone to "middle forgetting"
- Skills use **on-demand loading**: only the relevant skills enter the context
- Teams can version and maintain them like internal SOPs

### Skills in Cursor / Agent products
You may have heard about Agent "skills." At their core, they are  
**reusable capability packs that solidify repeated workflows**, which the Harness then schedules inside the loop.

### Example Skills for education products
| Skill | What it does |
|---|---|
| `socratic_tutor` | Guided tutoring without directly giving the answer |
| `quiz_builder` | Generates questions by knowledge point and difficulty |
| `essay_rubric_grader` | Performs a first-pass essay evaluation using a rubric |
| `early_warning` | Produces alerts from learning data |
| `ocr_homework_ingest` | Homework photo -> text -> question bank |

---

## 4. How do the three work together?

```text
User goal
   ↓
Harness starts the Agent Loop
   ↓
Skills are loaded on demand inside the loop
   ↓
Skills call Tools (including RAG / OCR / MCP)
   ↓
Results are written back to Memory; use Context Compact when needed
   ↓
Stop condition reached -> return result / wait for human review
```

### 30-second interview version
> "Agent Loop is the execution rhythm; Harness is the shell that provides safety and tool access; Skills are reusable professional capabilities. Put together, they form a production-grade Agentic system—not just a chatbot."

---

## Quiz

1. What are at least two stop conditions an Agent Loop should have?  
2. How is a Harness different from simply choosing a stronger model?  
3. Why are Skills better than stuffing every SOP into the System Prompt?

<details>
<summary>Suggested answers</summary>

1. Examples: task success, step/budget limit, human required, repeated failure  
2. The model provides intelligence; the Harness provides a controllable execution environment (tools, permissions, logs, retries)  
3. On-demand loading, versionability, reduced context usage, and less lost-in-the-middle risk  

</details>

---

**Next lesson ->** [`02-context-engineering.md`](02-context-engineering.md)
