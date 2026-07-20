# Chapter 8 | OCR and RAG: From Images to Retrievable Knowledge

## One-sentence takeaway

**OCR turns "invisible images" into text; RAG supplies "the right material" to the model before it answers.**  
In education, the two are often chained into one pipeline: homework photo -> recognition -> course-material retrieval -> guided response.

---

## 1. OCR (Optical Character Recognition)

### What is it?
Extracting **text** from images or scanned PDF pages (and sometimes layout, tables, or formula structure as well).

### Why is it so important in education?
| Input | What OCR enables afterward |
|---|---|
| Homework photo | Recognize a student's answer -> auto-grading / error analysis |
| Scanned handout PDF | Ingest into a RAG question bank and knowledge base |
| Whiteboard / notes | Convert into searchable review material |
| IDs / forms | Structure enrollment data (with strong privacy caution) |

### Modern OCR is more than just "reading characters"
Advanced capabilities often include:
- **Layout analysis** (headings, fields, reading order)
- **Table reconstruction**
- **Handwriting recognition** (HW-OCR, much harder)
- **Formula / chart understanding** (via multimodal models or specialized engines)
- Correct reading order for **multi-column PDFs**

### OCR vs Multimodal LLM
| | Traditional / specialized OCR | Multimodal LLM (answering from images) |
|---|---|---|
| Strength | Stable text extraction and structuring | Understands visual meaning and can reason |
| Weakness | Does not understand semantics | May skim, hallucinate, and cost more |
| Best practice | Use OCR first for reliable text | Bring in a VLM only when interpretation is needed |

> Interview bonus point: education products often use **OCR for text extraction + LLM for understanding**, instead of gambling on image-only prompting.

### OCR quality pitfalls (you should mention these)
1. Blurry photos, glare, or skew  
2. Joined-up handwriting, mixed Traditional/Simplified Chinese  
3. Math expressions get corrupted (`x²` becomes `x2`)  
4. Wrong reading order (double-column handouts)  
5. Personal data entering the model (student homework photos of minors)

### Mitigation
- Image preprocessing before upload (crop, binarize, deskew)  
- Use formula-specific recognition or a human correction step  
- Mark low-confidence characters for teacher confirmation  
- PII masking / local OCR

---

## 2. RAG (Retrieval-Augmented Generation) review and deeper understanding

### What is it?
Before answering, the system **retrieves relevant materials** and then has the model generate based on them.  
-> This reduces hallucination, supports citations, and avoids retraining every time course materials change.

### Standard pipeline

```text
Documents -> clean / chunk -> Embedding -> write to Vector DB
                                       ↑
User question -> Embedding -> similarity search Top-K -> (optional rerank)
                                       ↓
                          Assemble into Prompt (Context Construction)
                                       ↓
                                 LLM generation + citations
```

### What is special about educational material retrieval?
| General RAG | Education RAG |
|---|---|
| Finds relevant passages | Must also align by **grade level / unit / difficulty** |
| "Useful enough" answers are acceptable | Must **cite materials** and must not teach incorrectly |
| One knowledge base | Often multiple textbook versions, semesters, and curriculum standards |
| Can give the answer directly | In practice mode, it must follow a teaching strategy (guidance) |

### Advanced techniques (good interview bonus points)
- **Metadata filtering**: first narrow to "Grade 7, second semester, fractions unit," then run vector search  
- **Hybrid search**: keyword search (BM25) + vector search, more reliable for proper nouns and terminology  
- **Reranker**: coarse ranking first, then fine ranking to improve mid-list quality  
- **Parent-child chunk**: retrieve small chunks, generate with larger chunks (preserving full worked examples)  
- **Query rewriting**: rewrite a student's casual wording into textbook language before retrieval

---

## 3. Combining OCR + RAG (very common in product-design interviews)

### Scenario: a student takes a photo of homework and asks, "Where did I go wrong on this problem?"

```text
1) OCR: photo -> problem text + student's answer text
2) Clean-up: error correction, low-confidence marking
3) RAG: use the problem statement to retrieve the matching unit materials and similar examples
4) Context construction:
     - Rules: practice mode, guided tutoring
     - OCR result (problem / answer)
     - Course material snippets (with source)
5) Agent Loop: analyze the mistake -> guide with questions -> provide similar practice
6) Write back to learning records (update Knowledge Tracing)
```

### What do you do when it fails?
| Failure point | Handling |
|---|---|
| OCR confidence is low | Ask the student to retake the photo / ask the teacher to confirm |
| RAG cannot find a match | Admit uncertainty, escalate to a human, or broaden retrieval |
| Retrieval hits the wrong unit | Tighten metadata filters; add negative-example evaluation |
| The model wants to give the answer directly | Use Guardrails + Skills to enforce Socratic mode |

---

## 4. Relationship to Context Compact / Lost in the Middle

- Do **not** dump full OCR text and RAG Top-20 raw passages into the middle of the prompt  
- Include only the **Top 3-5 highly relevant chunks**, then restate the task at the end  
- After a long conversation, use a **state card** to remember that "this problem is about common denominators" instead of keeping all 20 OCR turns

---

## 5. Fast interview answers

### What is OCR?
> It extracts text from images. In education, it is used for homework photos and scanned handouts.

### What is RAG?
> It retrieves company/course materials before generation, reducing hallucination and enabling citations.

### What is the difference between the two?
> OCR solves "the input is an image"; RAG solves "the knowledge needs grounding." They are often combined into one pipeline.

### How do you prevent teaching errors?
> Use human review for low OCR confidence, add metadata and citations in RAG, and run grounding checks after generation.

---

## Quiz

1. Why do education scenarios often use "OCR + LLM" instead of just giving the image directly to the model?  
2. What is Hybrid search, and why is it useful for course materials?  
3. If a student uploads a photo and asks about a mistake, what is the full 4-6 step pipeline?

<details>
<summary>Suggested answers</summary>

1. OCR text extraction is more controllable and auditable; the LLM then handles understanding and teaching strategy  
2. Keyword + vector retrieval; it is more stable for textbook terminology and formula numbering  
3. OCR -> clean-up -> RAG -> build context -> guided generation -> write back learning state  

</details>

---

**Review ->** [`01-agent-loop-harness-skills.md`](01-agent-loop-harness-skills.md)  
**Next chapter ->** [`../05-glossary/01-full-glossary.md`](../05-glossary/01-full-glossary.md)
