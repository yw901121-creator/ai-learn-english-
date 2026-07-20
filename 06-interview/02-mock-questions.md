# Mock Interview Question Bank (with Scoring Criteria)

Practice method: answer with a timer -> compare your response against the "strong answer elements" and self-evaluate.

---

## Basic questions

### Q1. Explain what an LLM is in non-technical language
**Strong answer elements:** predicts text, trained on large-scale data, can handle conversation / writing / coding, can hallucinate  
**Fail:** only says "it's a smart robot"

### Q2. What's the difference between ChatGPT and Cursor?
**Strong answer elements:** general-purpose chat vs embedded in the development workflow (read project files, edit files, run commands, PR workflow)

### Q3. What is hallucination, and how should you handle it in education?
**Strong answer elements:** definition + RAG + refusal when uncertain + human review + citations

---

## Advanced questions

### Q4. How do you choose between RAG and Fine-tuning?
**Strong answer elements:** update frequency, cost, hallucination mitigation, behavioral consistency; course materials usually fit RAG better

### Q5. What is MCP, and why is it mentioned so often in 2026?
**Strong answer elements:** standardized way to connect tools, reduces custom integrations, works well with Agents

### Q6. What's the difference between an Agent and workflow automation?
**Strong answer elements:** fixed workflow vs dynamic planning; Agents are more flexible but need stronger guardrails

---

## Education scenario questions

### Q7. Design an MVP for an AI math tutor for middle school students
**Strong answer elements:**  
- Scope (algebra only)  
- RAG connected to handouts/materials  
- Guided dialogue  
- Practice / exam mode switch  
- Teacher review backend  
- Success metrics (accuracy, repeat practice rate, teacher time saved)

### Q8. How do you measure whether an AI tutor actually helped a student learn?
**Strong answer elements:** not just NPS; use delayed tests, transfer questions, and performance after prompts are removed

### Q9. If an institutional client says, "We're worried students will use AI to cheat," how do you respond?
**Strong answer elements:** product design (mode switching) + assessment design + policy + not relying on detection alone

### Q10. What would you do if AI went live and taught a formula incorrectly?
**Strong answer elements:** take it down / roll it back, assess impact scope, identify the root cause (retrieval / prompt / model), run regression evaluation, notify teachers and students

---

## Behavioral questions

### Q11. Describe a time you used AI to improve efficiency, with verified results
**Structure:** STAR (Situation-Task-Action-Result) + how you verified the outcome

### Q12. If you disagree with "Let's generate all teaching materials with AI and skip review," how would you say it?
**Strong answer elements:** respect the efficiency argument, but persuade using risk and trust-cost reasoning

---

## Self-scoring rubric (0–2 points per question)

| Score | Meaning |
|---|---|
| 0 | Cannot answer or clearly incorrect |
| 1 | Has the basic idea but lacks examples / limitations |
| 2 | Clear definition + scenario awareness + risks |

**Passing line:** total score >= 70%  
**Interview-ready:** total score >= 85%, and both Q7 and Q9 must be 2 points

---

**Next file ->** [`../07-news-updates/LATEST.md`](../07-news-updates/LATEST.md)
