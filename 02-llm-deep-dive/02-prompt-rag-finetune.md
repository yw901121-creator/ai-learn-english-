# Chapter 2 | Prompt, RAG, and Fine-tuning (the essential trio)

## One-sentence takeaway

There are three main ways to make AI stronger: **write better instructions (Prompt) -> connect it to data (RAG) -> train it for specialization (Fine-tuning)**.  
For education products, **90% of the time you should start with Prompt + RAG**. Fine-tuning is the advanced option.

---

## 1. Prompt Engineering

### What is it?
Designing the instructions and examples given to the model so the output becomes more stable and better aligned with your needs.

### Common techniques
| Technique | Description | Education example |
|---|---|---|
| Role | Assign a role | "You are a high school math teaching assistant." |
| Constraints | Add limits | "Do not give the final answer directly." |
| Few-shot | Provide examples | Give 2 examples of "good guided responses" |
| Structured output | Require a format | JSON: question, difficulty, knowledge point, explanation |
| Chain-of-Thought | Ask for step-by-step reasoning | "Reason step by step, but only show guided hints to the student." |

### Prompt rules every education product should add
1. If uncertain, say so and recommend asking the teacher  
2. Prioritize quoting the course unit or lesson material  
3. Guide with questions instead of leaking the answer directly  
4. Use age-appropriate language (elementary school vs. university)

---

## 2. RAG (Retrieval-Augmented Generation)

### What is it?
**Retrieve first, then generate.**  
Put course materials, lecture notes, and FAQs into a database. When a student asks a question, the system first finds the relevant passages, then lets the LLM answer based on those passages.

### Why is it so important in education?
- Reduces hallucinations (teaching the wrong thing)
- Makes answers citable (more explainable)
- Lets you update materials without retraining the model

### Simplified workflow
```
Student question
  -> Embedding (convert text into vectors)
  -> Vector DB similarity search
  -> Retrieve Top-K course material chunks
  -> Send them to the LLM together with the question
  -> Generate a grounded answer
```

### Key components
| Component | What it does |
|---|---|
| Embeddings | Convert text into semantic vectors |
| Vector Database | Store vectors and run similarity search (such as Pinecone, pgvector) |
| Chunking | Split long course materials into smaller sections |
| Reranker | Re-rank the results to improve relevance |
| Citation | Show which page or lesson the answer came from |

### Interview line to remember
> "RAG is the source of knowledge; education AI without RAG is like a teacher teaching from memory without opening the book."

---

## 3. Fine-tuning

### What is it?
Continue training the model on your own data so it better understands domain terminology or a fixed response style.

### When do you actually need it?
| Good fit | Not the best first move |
|---|---|
| You need fixed question formats or output formats | Course materials change often (RAG is more suitable) |
| You need a consistent brand voice | The dataset is small and messy |
| The domain contains lots of specialized terminology | Budget or staffing is limited |

### How do you choose between it and RAG?
```
If the data needs to stay current and searchable -> RAG
If the behavior needs to consistently feel like "our teachers" -> Fine-tuning (or a strong Prompt)
If you need both -> production systems often use RAG + light Fine-tuning
```

---

## 4. Side-by-side comparison (must memorize)

| | Prompt | RAG | Fine-tune |
|---|---|---|---|
| Change cost | Low | Medium | High |
| Update speed | Immediate | Fast (just update the index) | Slow (requires retraining) |
| Hallucination control | Limited | Strong | Medium |
| Best fit for education | ✅ Required | ✅ Almost required | ⚠️ Advanced |

---

## Quiz

1. Why does education AI almost always need RAG?  
2. "Do not give the answer directly; guide with questions instead" belongs to which technique?  
3. If course materials are updated every week, should you choose Fine-tuning or RAG?

<details>
<summary>Reference answers</summary>

1. It reduces teaching errors, allows citations to course materials, and avoids retraining every time content changes  
2. Prompt constraints / instructional strategy (Scaffolding)  
3. RAG (you only need to update the index)  

</details>

---

**Next lesson ->** [`../03-agents-tools/01-what-is-agent.md`](../03-agents-tools/01-what-is-agent.md)
