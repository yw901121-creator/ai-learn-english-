# Chapter 1 | Core Foundational Concepts (12 Must-Know Terms)

## One-sentence takeaway

If you can explain these 12 terms clearly, interviews are much less likely to catch you off guard.

---

## 12 terms you must understand

### 1. Model
The "brain" learned from data. You give it an input, and it produces an output.

### 2. Training
The process of adjusting model parameters using large amounts of data. It is expensive, slow, and compute-intensive.

### 3. Inference
After training is complete, this is the actual use of the model to answer questions. Every reply you get from ChatGPT is inference.

### 4. Parameters
The numerical weights inside the model. More parameters often mean stronger capability, but also higher cost.  
Example: Kimi K3 claimed around **2.8 trillion parameters** (2026-07).

### 5. Token
The smallest unit of text that AI processes (not necessarily one word or one character).  
Billing, speed, and context length are all calculated in tokens.

### 6. Context Window
The maximum number of tokens the AI can "remember / see" in a single interaction.  
A larger window helps with long documents, but it also costs more.

### 7. Prompt
The instruction you give the AI. The quality of the Prompt directly affects the quality of the output.

### 8. Hallucination
When AI confidently makes up incorrect information. This is especially dangerous in education scenarios.

### 9. Multimodal
The ability to handle multiple input/output types such as text, images, audio, and video.

### 10. Latency
The time from asking a question to receiving an answer. It is a key product experience metric.

### 11. Benchmark
A standard test set used to compare model performance. Important reminder: vendor self-reported results should be taken with caution.

### 12. Alignment
The process of making model behavior match human intent and safety requirements (for example, not giving dangerous advice casually).

---

## Common misunderstandings to clear up

| Misunderstanding | Correct view |
|---|---|
| AI can "think" | At its core, it predicts the next token by probability; more advanced models may also have reasoning modes |
| Bigger parameter counts always mean a better model | Training quality, alignment, and tool-use ability also matter |
| AI is always correct | It can hallucinate, so important content must be verified |
| Once trained, it stays correct forever | Knowledge has a cutoff date, so you need RAG or web-connected tools |

---

## How to say it in an interview

> "I understand that a model is a function trained on data, and using it in practice is called inference.  
> In real products, the most important things are not raw parameter counts, but **accuracy, latency, cost, and whether the system can connect to tools and proprietary data**."

---

## Quiz

1. What is the difference between Training and Inference?  
2. Why are education products especially sensitive to hallucinations?  
3. What is the trade-off of having a very large Context Window?

<details>
<summary>Reference answers</summary>

1. Training = learning; Inference = using the model  
2. Teaching the wrong thing is worse than not teaching at all; it damages learning outcomes and trust  
3. Higher cost, sometimes slower responses, and possibly more irrelevant noise  

</details>

---

**Next lesson ->** [`../02-llm-deep-dive/01-what-is-llm.md`](../02-llm-deep-dive/01-what-is-llm.md)
