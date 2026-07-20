# Chapter 2 | What Is an LLM?

## One-sentence takeaway

**LLM = Large Language Model**  
It is trained on massive amounts of text and is good at understanding and generating natural language (as well as code).

---

## 1. What does an LLM actually do?

At its core, it predicts the **next most likely token**.  
That sounds simple, but once the scale is large enough and alignment is done well, it can demonstrate:

- Translation, summarization, and writing
- Coding and debugging
- Reasoning and planning (especially in reasoning / thinking modes)
- Multi-turn conversation

---

## 2. Mainstream model families in 2026 (must remember)

| Company | Flagship / core lineup | Positioning (interview phrasing) |
|---|---|---|
| **OpenAI** | GPT-5.6 family (Sol / Terra / Luna) | Three tiers: flagship, everyday use, and high cost-performance |
| **Anthropic** | Claude Fable 5, Claude Sonnet 5 | Long tasks, coding, and professional work |
| **Google** | Gemini 3.5 (Flash and others) | Multimodal, fast, agentic |
| **Moonshot** | Kimi K3 | Ultra-large open-source direction, long context |
| **Alibaba** | Qwen3.8 (preview) | Open weights and strong value competition |
| **Tools such as Cursor** | Composer and others | Models embedded inside IDE / Agent products |

> The numbers will change. In interviews, the key is not memorizing version numbers, but **knowing multiple competitors, understanding flagship vs. value tiers, and understanding open-source vs. closed-source trade-offs**.

---

## 3. Closed-source vs. open-source

| | Closed-source (GPT, Claude) | Open-source / open-weight (Llama, Kimi, Qwen) |
|---|---|---|
| Strengths | Usually stronger, better maintained, convenient APIs | Can be privately deployed, more controllable, flexible cost structure |
| Weaknesses | Data leaves the company, pricing, vendor dependence | You must handle operations yourself and take responsibility for security and quality |
| Common choice for education companies | Fast SaaS launch | Private deployment when security or localization requirements are strong |

---

## 4. Reasoning / Thinking Model (hot term in 2025-2026)

Some models "think before answering" through internal multi-step reasoning:

- Best for: hard problems, math, complex code, planning
- Trade-off: slower and more expensive (more tokens)

Interview phrasing:

> "Use fast models for simple tasks; use thinking mode for complex reasoning, and make deliberate trade-offs between cost and quality."

---

## 5. How should you choose a model for education scenarios?

| Scenario | Top priorities |
|---|---|
| AI teaching assistant Q&A | Accuracy, ability to cite course materials, latency |
| Automatic question generation | Structured output, controllable difficulty |
| Essay feedback | Tone, fairness, explainability |
| Batch grading | Cost (high traffic volume) |
| Research-oriented Agent | Tool calling, long-task stability |

---

## Interview line to remember

> "The LLM is the brain of education AI, but the brain should not run naked — you need RAG to reduce hallucinations, rules to prevent cheating, and teacher review to protect quality."

---

## Quiz

1. What is an LLM fundamentally predicting?  
2. What product strategy do GPT-5.6's Sol / Terra / Luna represent?  
3. When should an education company consider using open-source models?

<details>
<summary>Reference answers</summary>

1. The next token  
2. A tiered lineup of flagship / balanced / low-cost options, so you choose the model by task  
3. When private deployment, data residency, or controllable cost is required  

</details>

---

**Next lesson ->** [`02-prompt-rag-finetune.md`](02-prompt-rag-finetune.md)
