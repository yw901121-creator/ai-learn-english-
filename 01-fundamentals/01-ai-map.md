# Chapter 1 | The AI Map: From Machine Learning to Generative AI

## One-sentence takeaway

**AI is the umbrella term; when people talk about "AI" in interviews today, they usually mean Generative AI, especially LLMs.**

---

## 1. The AI family tree (must memorize)

```
Artificial Intelligence (AI)
│
├── Machine Learning (learning rules from data)
│   ├── Supervised Learning (with labels: classification, prediction)
│   ├── Unsupervised Learning (without labels: clustering)
│   └── Reinforcement Learning (learning strategies through rewards: games, recommendation)
│
├── Deep Learning (using neural networks)
│   ├── CNN -> vision (faces, OCR)
│   ├── RNN / LSTM -> early language processing
│   └── Transformer -> the foundation of modern language and multimodal systems
│
└── Generative AI <- ★ the current mainstream
    ├── LLM (text: GPT, Claude, Gemini)
    ├── Image generation (Midjourney, DALL·E, Flux)
    ├── Voice / video generation
    └── AI Agent (can plan + take actions)
```

---

## 2. How each era differs (a common interview question)

| Era | Representative capability | Limitation |
|---|---|---|
| Rule-based systems | If-else expert systems | Impossible to write everything, not flexible |
| Traditional ML | Prediction, recommendation, classification | Needs lots of labeled data and feature engineering |
| Deep Learning | Breakthroughs in vision and speech | Black-box behavior, heavy compute needs |
| Generative AI | Generates text / images / code | Hallucinations, cost, security |
| Agentic AI (2025-2026) | Automatically completes multi-step tasks | Controllability, error amplification |

---

## 3. Why did it suddenly explode after 2022?

Three conditions matured at the same time:

1. **The Transformer architecture** (2017) -> parallel training and long-range dependency handling  
2. **Massive compute and data** -> model parameters grew into the hundreds of billions and trillions  
3. **Alignment techniques (such as RLHF)** -> models became more able to "understand human intent and be helpful"

ChatGPT (2022) was the ignition point; 2024-2026 moved into the era of **Agent + tool calling**.

---

## 4. Interview line to remember

> "AI is a broad field, but the industry's focus today is **Generative AI**.  
> Chatbots are only the entry point; the real value comes from systems that can connect to data (RAG), connect to tools (MCP), and automatically complete tasks as **Agents**."

---

## Quiz

1. What is CNN mainly used for? What about Transformer?  
2. What is the biggest difference between Generative AI and traditional ML?  
3. In 2026, what is the "next layer" often called?

<details>
<summary>Reference answers</summary>

1. CNN -> vision; Transformer -> the foundation of language and multimodal systems  
2. Traditional ML mostly predicts or classifies; Generative AI can generate new content  
3. Agentic AI (AI that can plan and execute actions)  

</details>

---

**Next lesson ->** [`02-key-concepts.md`](02-key-concepts.md)
