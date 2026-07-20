# How to Keep This Course Updated Daily

You want me to watch AI news every day, notify you when something changes, and update the teaching materials.  
That is possible, but it needs a trigger method — **I cannot run forever on my own unless you set up Cursor Automation**.

---

## Option A: The easiest way (recommended)

Spend 10 seconds each day and send this in this chat (or in a new Agent):

```
Update the AI course news
```

Or use a fuller version:

```
Please search for today's latest AI news and update ai-course-en/07-news-updates/LATEST.md.
If there are new terms, add them to 05-glossary; if the interview scripts are affected, update 06-interview and give me a bullet list of what I should memorize today.
```

I will:
1. Check the latest model, product, and paper developments online  
2. Update `LATEST.md`  
3. Revise the glossary, lessons, and interview scripts when needed  
4. Start my reply with "Today's reminder" to tell you what changed  

---

## Option B: Cursor Automation (true daily automation)

If you have Cursor Automations:

1. Go to Cursor Settings / Automations and create a daily schedule  
2. Paste in this prompt:

```
You are the AI course maintenance TA. Please:
1) Search for important AI news from the past 24-48 hours (model releases, open source, Agent/MCP/EdTech)
2) Update /agent/ai-course-en/07-news-updates/LATEST.md (include the date and CHANGELOG)
3) Write new terminology into 05-glossary/01-full-glossary.md
4) If there are major changes, update the relevant chapters as well and list "Today's reminder" in the reply
5) Keep the tone interview-oriented, professional, and avoid gossip or rumors
```

3. Set the frequency to **daily** (morning is recommended)

> If you later provide an Automation ID, I can help check whether it is enabled.

---

## Option C: Intensive mode before an interview

For the 7 days before the interview, send this every day:

```
Update the news + give me 5 quiz questions for today
```

I will update the briefing and write questions based on the newest news items, so you actually absorb them.

---

## Bilingual repository sync

Whenever content is updated, update **both** repositories:

- Chinese repo: `ai-learn`
- English repo: `ai-learn-english-`

That includes news updates, glossary entries, chapter revisions, and interview scripts. If one language is updated first, sync the other version promptly so the two course repos stay aligned.

---

## Update rules (the standards I follow)

What should be written into the course:
- Officially released models/products
- Technical directions confirmed by official sources or multiple credible outlets
- New terms that affect interview talk tracks

What should not be added casually:
- Unverified leaks
- Pure stock-price talk or gossip
- Overly detailed parameter debates that become irrelevant within a week

---

## What you can do right now

1. Open `README.md` and look at the 7-day path  
2. Start reading from `00-overview/01-welcome.md`  
3. Come back tomorrow and say "Update the AI course news"

---

## File locations

English course root: `/agent/ai-course-en/`  
Chinese course root: `/agent/ai-course/`

Note: this Cloud Agent workspace is **not currently connected to your GitHub repo**, so the files live inside this environment only.  
If you want to keep them long term, download or copy the `ai-course-en/` and `ai-course/` folders to your local machine, or regenerate them later in an environment that is connected to a repo.
