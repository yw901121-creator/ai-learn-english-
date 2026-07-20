# Complete AI Glossary (Interview Edition)

> Updated: 2026-07-20 (v1.1)  
> How to use this: first learn the plain-English one-liner, then memorize the English term. Use the plain-English version in interviews and the English term in documents.

---

## A. Fundamentals

| Term | Plain English |
|---|---|
| **AI** | The broad category of technologies that make machines behave intelligently |
| **ML** | Machines learn patterns from data instead of relying on every rule being written by hand |
| **Deep Learning** | A type of machine learning built on multi-layer neural networks |
| **Generative AI** | AI that can generate text, images, audio, video, or code |
| **Model** | The trained "brain" |
| **Algorithm** | A method or step-by-step procedure for solving a problem |
| **Dataset** | A collection of data used for training or evaluation |
| **Supervised Learning** | Learning from examples that have correct answers |
| **Unsupervised Learning** | Finding structure in data, such as clusters |
| **Reinforcement Learning** | Learning a strategy through reward signals |

---

## B. LLM Core Concepts

| Term | Plain English |
|---|---|
| **LLM** | A Large Language Model |
| **Transformer** | The dominant architecture behind modern LLMs |
| **Token** | The unit the model reads, writes, and is billed on |
| **Context Window** | How much context the model can look at in one pass |
| **Prompt** | The instruction you give the model |
| **System Prompt** | The hidden high-priority rules that define role and safety behavior |
| **Temperature** | How random the output is (higher = more creative, less stable) |
| **Hallucination** | When the model says something wrong with complete confidence |
| **Cutoff** | The point in time where the model's training data stops |
| **Multimodal** | Able to work across multiple modalities such as text, images, audio, or video |
| **Reasoning / Thinking Model** | A mode where the model reasons internally before answering |
| **Latency** | Response delay |
| **Throughput** | How much work the system can process per unit of time |
| **Benchmark** | A standard way to evaluate performance |

---

## C. Ways to Make the Model Better

| Term | Plain English |
|---|---|
| **Prompt Engineering** | Writing better instructions |
| **Few-shot** | Guiding the model by giving it a few examples |
| **Chain-of-Thought (CoT)** | Asking for step-by-step reasoning |
| **RAG** | Retrieve relevant information first, then generate |
| **Embedding** | Text turned into a semantic vector |
| **Vector Database** | A database for storing vectors and running similarity search |
| **Chunking** | Splitting long content into pieces so it can be retrieved |
| **Reranking** | Re-sorting results to improve relevance |
| **Fine-tuning** | Adapting a model with your own data |
| **RLHF** | Aligning a model using human preference feedback |
| **Distillation** | Having a large model teach a smaller model |
| **LoRA** | One lower-cost method for fine-tuning |

---

## D. Agents and Systems (Very Hot in 2026)

| Term | Plain English |
|---|---|
| **AI Agent** | A system that can plan and call tools to accomplish a goal |
| **Agentic AI** | A product style that emphasizes autonomous, multi-step execution |
| **Tool Calling** | The model decides to call an external function or API |
| **MCP** | An open standard protocol for connecting AI to tools |
| **Multi-Agent** | Multiple specialist Agents collaborating together |
| **Orchestration** | Coordinating a multi-step or multi-Agent workflow |
| **Memory** | Short-term conversation memory or long-term user memory |
| **Computer Use** | AI operating a computer GUI |
| **Guardrails** | Safety and compliance controls |
| **Human-in-the-loop** | A person reviews critical steps |
| **Eval / Evaluation** | Systematic quality testing |
| **Observability** | Visibility into the system through logs, traces, and monitoring |
| **Agent Loop** | The cycle of perceive -> plan -> act -> observe -> reflect |
| **Harness** | The execution wrapper around a model: tools, permissions, memory, retries, and logs |
| **Skills** | Reusable, on-demand capability packs or SOP modules |
| **ReAct** | Reason + Act: the classic pattern of thinking while calling tools |

---

## D2. Context Engineering (Frequently Tested)

| Term | Plain English |
|---|---|
| **Context Engineering** | Proactively designing, ordering, and compressing the context the model can see |
| **Context Construction** | Assembling the content package shown to the model for the current turn |
| **Context Compact** | Compressing old dialogue or long outputs into a summary or state card |
| **Pinning** | Keeping critical rules fixed at the front so summaries do not overwrite them |
| **State Card** | A structured record of goal / constraints / progress |
| **Lost in the Middle** | In very long context, the model often ignores information in the middle |
| **Sliding Window** | Keeping only the most recent K turns of conversation |
| **OCR** | Optical Character Recognition: extracting text from images or scans |
| **VLM** | A Vision-Language Model that can see images and understand text |
| **Chunking** | Splitting long documents into smaller retrievable pieces |
| **Hybrid Search** | Combining keyword search with vector search |
| **Reranker** | A model or step that re-ranks retrieval results |
| **Grounding** | Anchoring the answer to retrieved sources to reduce made-up claims |

---

## E. Education-AI Terms

| Term | Plain English |
|---|---|
| **EdTech** | Education technology |
| **AI Tutor / AI TA** | An AI teaching assistant |
| **Adaptive Learning** | Personalized learning that adjusts to the learner |
| **Knowledge Tracing** | Tracking how well a learner has mastered each knowledge point |
| **BKT / DKT** | Classic / deep-learning knowledge-tracing algorithms |
| **Mastery Learning** | Do not move to the next level until mastery is reached |
| **Scaffolding** | Step-by-step support that is gradually removed |
| **Socratic Tutoring** | Guiding the learner through Socratic questioning |
| **Auto Grading** | Automated grading |
| **Learning Analytics** | Analysis of learning behavior and outcomes |
| **Early Warning System** | A system that flags learners at risk early |
| **Knowledge Graph** | A network of concepts and their relationships |
| **Item Bank** | A question bank |
| **Bloom's Taxonomy** | Bloom's cognitive levels, from remembering to creating |
| **Learning Science** | The science of how people learn, such as spaced repetition and retrieval practice |

---

## F. Business and Product

| Term | Plain English |
|---|---|
| **Token Cost** | Usage-based cost calculated from token consumption |
| **Model Routing** | Automatically choosing the right model for each task |
| **A/B Testing** | A controlled experiment comparing two versions |
| **KPI / North Star** | Key metrics / the main guiding metric |
| **Retention** | How well users keep coming back |
| **Completion Rate** | The percentage of learners who finish a course |
| **Time-to-Mastery** | How long it takes a learner to master something |
| **Moat** | A durable advantage, such as data, content, or network effects |

---

## G. 2026 Model and Product Shorthand

| Name | What you should know |
|---|---|
| **GPT-5.6 Sol / Terra / Luna** | OpenAI's three tiers: flagship / balanced / cheap-and-fast |
| **Claude Fable 5** | Anthropic's flagship long-horizon task model |
| **Claude Sonnet 5** | Main production model for coding and Agents |
| **Gemini 3.5 Flash** | Google's fast agentic / coding model |
| **Kimi K3** | Moonshot's very large open-source-oriented model (2026-07) |
| **Qwen3.8** | Alibaba's open-model competitor (preview) |
| **Cursor** | An AI IDE plus Cloud Agent |
| **Copilot** | GitHub's coding assistant, more focused on completion |
| **Khanmigo** | A representative education AI tutor |

---

## Memory Mnemonic

```
Brain = LLM
Knowledge = RAG (retrieve materials first)
Eyes = OCR (turn images into text)
Hands = Tools / MCP
Worker = Agent
Rhythm = Agent Loop
Body = Harness
Skill pack = Skills
Desk organization = Context Engineering
Middle-section trap = Lost in the Middle
Classroom rules = Guardrails
Teacher = Human-in-the-loop
```

---

**Advanced lesson ->** [`../08-agent-context/01-agent-loop-harness-skills.md`](../08-agent-context/01-agent-loop-harness-skills.md)  
**Next lesson ->** [`../06-interview/01-answer-scripts.md`](../06-interview/01-answer-scripts.md)
