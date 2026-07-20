# Chapter 3 | What Is an AI Agent?

## One-Sentence Takeaway

**A chatbot talks; an Agent gets things done.**  
Agent = LLM + goal + planning + tools + (often) memory.

---

## 1. Chatbot vs. Agent

| | Chatbot | Agent |
|---|---|---|
| Input | A single prompt | A goal |
| Output | A block of text | A sequence of actions and results |
| Example | "Explain photosynthesis." | "Create this week's practice worksheet for students and notify the teacher to review it." |
| Risk | Says something wrong | Does something wrong (and affects system data) |

---

## 2. The Four Core Parts of an Agent

```
┌──────────────────────────────────────────────┐
│                  AI Agent                    │
│  1. Brain: LLM (understanding and planning)  │
│  2. Tools (search, DB, API, browsing)        │
│  3. Memory (short-term chat / long-term files) │
│  4. Goal (success criteria for the task)     │
└──────────────────────────────────────────────┘
```

### Typical Work Loop (ReAct Pattern)
```
Think -> choose a tool -> take action -> observe the result -> think again -> ... -> done
```

---

## 3. The 2026 Buzzword: Agentic AI

It means a system can:

- **Plan autonomously** (break down tasks)
- **Use tools** (actually execute)
- **Persist across multiple steps** (long-horizon)
- **Act within policy** (permissions, approvals)

Product examples:

- Cursor Cloud Agent: edit code, run tests, open PRs  
- In education: learning early-warning Agent, auto quiz-generation Agent, course assistant Agent  

---

## 4. Multi-Agent

A complex task can be split across multiple specialist Agents:

| Agent | Responsibility (education example) |
|---|---|
| Tutor Agent | Answer questions and guide learners |
| Assessor Agent | Write questions and grade work |
| Analyst Agent | Flag learning-risk signals |
| Guardrail Agent | Check for answer leakage and bias |

Benefits: modular and auditable  
Tradeoff: coordination overhead, and errors can amplify each other

OpenAI GPT-5.6's **`ultra`** mode is conceptually parallel collaboration among multiple Agents to speed up hard problems.

---

## 5. Computer Use

AI can see the screen, click, fill out forms, and operate a GUI.  
Flagship 2026 models emphasize this capability, pushing AI closer to a "digital employee."

Possible education use cases:

- Automatically create course units in the LMS backend  
- Batch import item banks  
- Help teachers operate complex admin dashboards  

Risk: too much permission, accidental actions -> human approval gates are necessary.

---

## 6. Design Principles for Education Agents

1. **Read-only by default**; require approval for writes  
2. **Guide students without revealing full answers** (except where exam-mode rules say otherwise)  
3. **Log every action** (audit log)  
4. **Failures must be reversible**  
5. **Teachers remain the final authority**

---

## Interview Sound Bite

> "An Agent upgrades AI from 'answering questions' to 'completing workflows.'  
> In education products, the things I care about most are permissions, auditability, and teaching ethics - the system should be able to act, but it should never act recklessly."

---

## Quick Quiz

1. What does an Agent have that a chatbot does not?  
2. What are the pros and cons of a Multi-Agent setup?  
3. Why should education Agents not be given overly broad write permissions?

<details>
<summary>Suggested answers</summary>

1. A goal, planning, tool execution, and often memory  
2. Pro: specialized division of labor; con: hard coordination and error amplification  
3. They can accidentally change grades, send the wrong notifications, or damage data; approvals and logs are needed  

</details>

---

**Next lesson ->** [`02-mcp-and-tools.md`](02-mcp-and-tools.md)
