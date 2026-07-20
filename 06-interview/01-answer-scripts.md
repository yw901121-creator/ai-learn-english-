# Interview Answer Scripts (Ready to Memorize)

> Target company type: Online learning platform x AI  
> Updated: 2026-07-20

---

## A. "How well do you understand AI?" — 30-second version

> I have a practical understanding of AI, with a particular focus on **AI x Education**.  
> Right now, the industry's main focus is Generative AI, especially LLMs and **Agents** that can call tools to complete tasks.  
> In learning scenarios, AI mainly does three things: **personalized learning, automating repetitive teacher work, and using data to flag struggling students early**.  
> I also understand the limitations: models can hallucinate, and AI can become a cheating tool, so we need RAG, guided instruction, and human review.  
> My view is this: **AI is an accelerator for great teachers, not a replacement**.

---

## B. Full 2-minute version

> I look at AI from three layers:  
>  
> **Technical layer:** The core is the LLM. To make it production-ready, you usually also need RAG (retrieve course materials before answering), Tools/MCP (connect to LMS platforms, question banks, and other systems), and Agents to orchestrate multi-step tasks. In 2026, the mainstream approach is combining these pieces together rather than relying on chat alone.  
>  
> **Education application layer:** There are five major areas—AI teaching assistants, adaptive learning (Knowledge Tracing), automated assessment, content generation, and learning analytics with early warnings. The ideal closed loop is: a student practices at night with AI guidance -> mastery is updated -> the next day the system recommends adaptive questions -> the teacher reviews an alert list and intervenes precisely where needed.  
>  
> **Reality layer:** In education, you cannot afford to teach the wrong thing. So AI can be enabled in practice mode, but it should be disabled in exam mode; high-risk grading needs human review; and student data must stay compliant.  
>  
> I also keep up with model progress, such as OpenAI's GPT-5.6 tiering, Anthropic's Claude Fable 5, and the open-source side represented by Kimi K3. The key is not chasing star models for their own sake, but choosing technology based on **accuracy, cost, latency, and controllability**.

---

## C. Quick answers to common follow-up questions

### 1) Will AI replace teachers?
> No. AI can take over repetitive explanation and grading, while teachers remain responsible for motivation, values, and complex guidance. Teachers who know how to use AI will become even stronger.

### 2) What is the biggest risk?
> Teaching the wrong thing, cheating, bias, and privacy. The solutions are RAG plus citations, guided tutoring that avoids leaking answers, process-based assessment, fairness review across groups, and data minimization.

### 3) How would you design an AI teaching assistant?
> Three layers: (1) RAG grounded only in official course materials, (2) Socratic questioning, and (3) sending student friction points back to the teacher dashboard. The KPI should focus on "independent problem-solving ability," not just satisfaction scores.

### 4) What's the difference between RAG, MCP, and Agent?
> RAG supplies knowledge; MCP standardizes tool connectivity; Agent plans and executes. In practice, they are often used together.

### 5) Why do you want to work in education AI?
> Because this is one of the most socially valuable real-world applications of AI. LLMs make one-on-one tutoring scalable for the first time. I want to build products that genuinely help people learn, not just chat-based toys.

### 6) What new technologies are you following recently?
> Agentic AI, MCP, Multi-Agent systems, Computer Use, Context Engineering, and model-tier routing (flagship / balanced / low-cost). In education, I'm especially interested in how OCR + RAG + Agent can become an auditable teaching assistant system.

### 7) What are Agent Loop, Harness, and Skills?
> Agent Loop is the cycle of perceive -> plan -> act -> observe. Harness is the execution framework around the model, including tools, permissions, memory, and retries. Skills are reusable, on-demand capability packages. The model is the brain; Harness + Skills are what make it stable enough for production.

### 8) If you give an AI 20 turns of context, how does it know what matters most?
> It does not figure that out by itself. You need Context Engineering: pin the rules, maintain a state card, keep only relevant turns, refine evidence through RAG, and place key instructions at both the beginning and the end to avoid Lost in the Middle.

### 9) What is Lost in the Middle?
> In very long context windows, models often overlook information in the middle. So important constraints should go at both ends, and the middle should contain only short, highly relevant evidence rather than dumping an entire textbook into the prompt.

### 10) How are OCR and RAG used in education?
> OCR turns homework photos or scanned handouts into text; RAG then retrieves the matching course materials before generation. A common pipeline is: take a photo -> recognize text -> retrieve materials -> guide the student, with human confirmation for low-confidence cases.

---

## D. Questions to ask the interviewer (pick 2–3)

1. Is your current AI teaching assistant based mainly on RAG, or do you also use fine-tuning? How do you make sure it does not teach the wrong thing?  
2. Is your Adaptive Learning mastery model built in-house or based on an existing package?  
3. Do you define success more by course completion, score improvement, or teacher time saved?  
4. How do you handle AI-enabled cheating in exam scenarios?  
5. Do you rely on a single model provider, or do you use multi-model routing?  
6. How does your Agent harness manage permissions and context compacting?  
7. What is the OCR error rate for homework photo uploads, and what does the human correction workflow look like?

---

## E. Opening self-introduction (with AI, about 45 seconds)

> My name is XX, and my background is in XX.  
> In the past, I worked on XX at XX. In my day-to-day work, I use Cursor / ChatGPT / Claude to improve efficiency, and I have also studied LLMs, RAG, Agents, and education use cases in a more systematic way.  
> I'm especially interested in joining your company because you're applying AI to online education—and that requires not only technical capability, but also sound judgment in learning science and ethics.  
> I want to turn AI into a measurable product capability that improves learning outcomes, not just a flashy feature.

> (Replace XX with your real experience. If you do not have directly related experience, talk about self-study projects and hands-on usage instead of inventing something.)

---

**Next lesson ->** [`02-mock-questions.md`](02-mock-questions.md)
