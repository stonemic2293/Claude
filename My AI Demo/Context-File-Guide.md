# How to Write a Great Context File

*A plain-English guide for people who aren't programmers*

---

## What is a context file?

A context file is a short note you leave for your AI assistant. It explains your project the way you'd brief a new coworker on day one. With Claude it's usually called `CLAUDE.md`. Claude reads it automatically at the start of every session.

Without one, the AI starts from zero every time. You end up re-explaining the same things, and it keeps repeating the same mistakes. A good context file fixes both problems.

**The key idea:** a good context file tells the AI *what to do*, not just *what things are*. "The report is in the Reports folder" is information. "Save finished reports to `/Reports` as PDF, named `YYYY-MM-DD-Topic.pdf`" is an instruction. Instructions are what make the AI useful.

---

## The six sections, in order

Write the sections in this order. It moves from the big picture down to the fine print, which is also the order a new person needs to learn things.

| # | Section | The question it answers |
|---|---|---|
| 1 | The problem and the goal | *Why does this exist, and what does "done" look like?* |
| 2 | How to run, test, check, build, and deliver it | *What are the exact steps?* |
| 3 | Where things live | *Where do I find each piece?* |
| 4 | Hidden rules and conventions | *What would a newcomer get wrong?* |
| 5 | Workflow and safety rules | *How should we work together, and what's off-limits?* |
| 6 | Mistakes, gotchas, and decisions | *What have we already learned the hard way?* |

---

### 1. The problem (or bottleneck) and the current goal

**What it is:** Two or three sentences about the problem this project solves and what you're working toward *right now*.

**Why it matters:** The AI makes hundreds of small judgment calls. If it knows the goal, it makes them the way you would.

**Tips**
- Name the bottleneck. Say what's slow, painful, or broken today.
- Give the *current* goal, not the whole vision. Update it when the goal changes.
- Say what "finished" looks like.

> ✅ **Good:** "Tailoring my résumé for each job takes about 45 minutes. Goal this month: get it under 10 minutes per job while still passing ATS screening. Done = 10 tailored résumés a week."
>
> ❌ **Weak:** "This is a résumé project."

---

### 2. How to run, test, check, build, and deliver it

**What it is:** The exact steps to use the project, check that it works, and hand off the result.

In programming these are called *run, test, lint, build,* and *deploy*. In everyday terms:

| Tech word | Plain meaning | Everyday example |
|---|---|---|
| **Run** | Start it / use it | "Run the job-search skill with a job title and city" |
| **Test** | Prove it works | "Open the .docx and confirm it opens without errors" |
| **Lint** | Check the style and rules | "Check for spelling, no tables, standard headings" |
| **Build** | Assemble the final product | "Export to PDF and .docx" |
| **Deploy** | Deliver it to where it's used | "Upload to the job site, then log it in the tracker" |

**Tips**
- Write the exact command, button, or step. Don't write "the usual way."
- Put each step on its own line.
- Say what success looks like, e.g. "you should see 20 job results."

---

### 3. Where the major pieces live

**What it is:** A map of your folders and files. It doesn't list every file, only the important ones.

**Why it matters:** Without a map, the AI guesses or wastes time searching. It might even create a duplicate of something you already have.

**Tips**
- A small table or indented list works best.
- Include the "source of truth," meaning the one master file everything else copies from.

> ```
> Resume/master-resume.docx   ← the master. Never edit it directly.
> Resume/tailored/            ← one copy per company
> context/job-search.md       ← target roles + application tracker
> ```

---

### 4. Hidden rules and conventions

**What it is:** The rules you can't tell just by looking at the files. They're the unwritten rules a new coworker would only learn by getting them wrong.

**Examples**
- Naming: "Name files `Firstname_Lastname_Company.docx`."
- Style: "Use American spelling. No first person in résumé bullets."
- Outside requirements: "ATS systems can't read tables or text boxes, so never use them."
- Preferences: "Lead with the recommendation, then the reasoning."

**Tip:** If you've corrected the AI on something twice, it belongs here.

---

### 5. Workflow expectations and safety rules

**What it is:** How you want the AI to work *with* you, and the lines it must never cross.

**Workflow examples**
- "Show me a draft before you send anything."
- "When something is unclear, make a sensible assumption, tell me what it was, and keep going."
- "Keep answers short unless I ask for detail."

**Safety examples** (be firm and specific)
- "**Never** delete or overwrite the master résumé."
- "**Never** send email, post online, or submit an application without my OK."
- "**Never** put personal details (address, SSN, account numbers) in any file."
- "Ask before spending money or signing up for anything."

**Tip:** Use words like *never* and *always* here. Save them for the rules that really matter so they stand out.

---

### 6. Recurring mistakes, gotchas, and decisions

**What it is:** A running log of lessons learned. This is the section that makes your AI smarter every week.

Three kinds of entries go here:
- **Mistakes:** "The AI kept inventing metrics. Rule: only use numbers from `work-history.md`."
- **Gotchas:** "LinkedIn job links expire after about 30 days. Save the job text, not just the link."
- **Decisions:** "Decided on 2026-09-20 to use .docx instead of PDF, because more ATS systems read it cleanly."

**Tip:** For decisions, write down *why*. Otherwise you or the AI will argue the same point again next month.

---

## Fill-in-the-blank template

Copy this into a file named `CLAUDE.md` and fill in the brackets.

```markdown
# CLAUDE.md — [Project name]

## 1. Problem and current goal
- **Problem / bottleneck:** [What is slow, painful, or broken today?]
- **Current goal:** [What are we working toward right now?]
- **Done looks like:** [How will we know we succeeded?]

## 2. How to run, test, check, build, and deliver
- **Run / use:** [exact steps]
- **Test (prove it works):** [exact steps + what success looks like]
- **Check (style and rules):** [checklist]
- **Build (final product):** [exact steps]
- **Deliver:** [where it goes and how]

## 3. Where things live
- `[path/file]`: [what it is]
- `[path/folder]/`: [what goes in it]
- **Source of truth:** [the one master file]

## 4. Hidden rules and conventions
- [Naming rule]
- [Style rule]
- [Outside requirement the files don't show]

## 5. Workflow and safety
- **How we work:** [drafts first? how much detail? when to ask?]
- **Never:** [delete X / send Y / share Z]
- **Always:** [ask before A / back up B]

## 6. Mistakes, gotchas, and decisions
- **Mistake → rule:** [what went wrong] → [the new rule]
- **Gotcha:** [surprising thing to watch out for]
- **Decision (date):** [what we chose] because [why]
```

---

## Quick checklist for a high-performing context file

- [ ] **Short.** One or two pages. Put the deep detail in separate files and point to them.
- [ ] **Instructions, not descriptions.** Most lines tell the AI what to *do*.
- [ ] **Specific.** Exact names, paths, steps, and examples.
- [ ] **Current.** The goal in Section 1 matches what you're doing *this week*.
- [ ] **Safety rules stand out.** "Never" and "always" are used only for rules that really matter.
- [ ] **Keeps growing.** Every correction becomes a new line in Section 6.
- [ ] **No secrets.** No passwords, account numbers, or private details you wouldn't want copied.

> **Rule of thumb:** If you've explained something to the AI more than once, it belongs in the context file.
