# Chapter 3 | MCP, Tool Calling, and Modern AI Architecture

## One-Sentence Takeaway

**RAG helps AI "know more"; MCP helps AI "do more."**  
By 2026, the mainstream architecture is almost always: **LLM + RAG + Tools/MCP + Agent orchestration**.

---

## 1. Tool Calling / Function Calling

The model does not just return text - it can also output "I want to call this tool":

```
User: How many live classes are there next Wednesday?
Model: -> call get_schedule(date="next Wednesday")
System: returns timetable data
Model: generates the answer from the data
```

Example education tools:

- `search_curriculum` search course materials  
- `create_quiz` generate a quiz  
- `get_mastery(user_id, skill)` check mastery level  
- `notify_teacher` notify the teacher  

---

## 2. MCP (Model Context Protocol)

### What is it?
An **open standard** introduced by Anthropic and later widely adopted:  
it lets AI applications connect to external tools, files, databases, and services in a consistent way.

### Why does it matter?
Before: every tool needed a custom integration (an N x M explosion)  
Now: build a tool as an MCP Server, and many AI Hosts can connect to it

### Analogy
> USB for peripherals ~= MCP for AI tools

### Architecture
```
AI Host (Cursor / Claude / your own app)
   <-> MCP Client
MCP Server (GitHub, Notion, LMS, database, ...)
   -> provides: Tools / Resources / Prompts
```

### How to explain it in an interview
> "MCP is the standard plug between AI and external systems. With it, an education platform can expose its item bank, LMS, and notification system as tools, so an Agent can call them safely."

---

## 3. RAG vs. MCP vs. Agent (Frequently Tested)

| | What problem it solves | In one line |
|---|---|---|
| **RAG** | Outdated knowledge / hallucinations | Retrieve first, then answer |
| **MCP** | Fragmented integrations | Standardize tool access |
| **Agent** | Multi-step tasks | Plan and execute |

They are not mutually exclusive - they work together:

```
Agent (orchestration)
  ├─ RAG (read course knowledge)
  └─ MCP/Tools (check grades, build quizzes, send notifications)
```

---

## 4. Embeddings & Vector DB (Quick Refresher)

- **Embedding**: text -> vector (semantically similar items are closer together)  
- **Vector DB**: a database built to store vectors and run similarity search  
- Education use cases: similar-question recommendation, duplicate-content detection, content retrieval  

---

## 5. Guardrails

Essential for any production system:

| Guardrail | Purpose |
|---|---|
| Input filtering | Block prompt attacks and inappropriate content |
| Output checks | Prevent answer leakage, hate content, and privacy leaks |
| Permission control | Students, teachers, and admins should have different capabilities |
| Human review | High-risk actions need human approval |
| Evaluation set | Regularly run regression checks on education-specific test sets |

---

## 6. The One-Line Architecture to Memorize

> "Frontend question -> Agent orchestration -> RAG fetches course materials -> when needed, MCP calls the LMS API -> Guardrail checks -> reply to the student and write a learning log."

---

## Quick Quiz

1. What is the difference between RAG and MCP?  
2. Why do people say MCP is like USB?  
3. In education, what does a Guardrail at minimum need to prevent?

<details>
<summary>Suggested answers</summary>

1. RAG adds knowledge; MCP connects tools and systems  
2. It provides a standard interface, so things can plug in and work without one-off integrations  
3. Answer leakage, bad teaching, privacy leaks, inappropriate content, and unauthorized grade changes  

</details>

---

**Next lesson ->** [`../04-edtech-ai/01-edtech-landscape.md`](../04-edtech-ai/01-edtech-landscape.md)
