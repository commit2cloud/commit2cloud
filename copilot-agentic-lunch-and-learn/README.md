# Copilot Agentic Workflows — Lunch & Learn Demo Session

> **Duration:** 15–20 minutes &nbsp;|&nbsp; **Format:** Live demos + discussion &nbsp;|&nbsp; **Audience:** Engineering teams exploring AI-assisted development (all experience levels)

## Synopsis

GitHub Copilot has evolved from code completion into a suite of **agentic capabilities** — AI that doesn't just suggest code, but takes action across the entire software development lifecycle. In this session, you'll see how AI agents can autonomously write code, review pull requests, and automate repository workflows — all while keeping humans in the loop.

**What you'll see:**

- **Coding Agent** — Assign a GitHub issue to Copilot and watch it plan, code, test, and open a pull request autonomously in the cloud.
- **Copilot Code Review** — An AI-powered first-pass reviewer that catches bugs and suggests improvements before your human reviewers look at a PR.
- **GitHub Agentic Workflows** — Write repository automations in plain Markdown. Describe your intent, and an AI agent executes it — issue triage, CI failure analysis, doc maintenance, and more.

**Key takeaway:** Agents handle the heavy lifting; your team stays in the loop for every decision. Nothing ships without human review.

**For all experience levels:** Whether you're new to Copilot or have been using it for years, you'll see practical examples of how agentic workflows can accelerate your team's development process.

---

> **Prepared by:** Solutions Engineering (@commit2cloud)  
> **Demo App:** [octodemo/octocat_supply](https://github.com/octodemo/octocat_supply) (bootstrapped via [issue template](https://github.com/octodemo/bootstrap/issues/new?template=001_octocat_supply.yml))

---

## Session Agenda (18 min)

| Time | Segment | Focus |
|------|---------|-------|
| 3 min | What Are Agentic Workflows? | Level-set for the room — sync vs async, where agents fit in the SDLC |
| 6 min | Coding Agent (Async) | Assign an issue → agent codes → opens a PR |
| 4 min | Copilot Code Review | AI-powered review on the agent's PR |
| 4 min | GitHub Agentic Workflows (gh-aw) | Markdown-authored, event-driven repo automation via AI agents |
| 1 min | Wrap-Up & Q&A | Recap + open discussion |

---

## Presenter Notes *(internal — do not share)*

### Contents

| Document | Purpose |
|----------|---------|
| [Demo Script](demo-script.md) | Step-by-step walk-through with talk track, transitions, and live-demo instructions |

---

### Key Messaging

1. **Agentic ≠ autopilot** — humans stay in the loop at every decision point.
2. **Sync + Async = full coverage** — Agent Mode for real-time pairing; Coding Agent for background work.
3. **GitHub Agentic Workflows = Continuous AI** — Markdown-authored, event-driven repo automation that complements CI/CD.
4. **Accessible to all levels** — Whether new to Copilot or experienced, agentic workflows meet you where you are.

---

### Pre-Session Checklist

- [ ] Fork or clone [octodemo/octocat_supply](https://github.com/octodemo/octocat_supply) into your demo org
- [ ] Create a well-scoped issue ready to assign to `@copilot` (e.g., "Add a discount code field to the checkout page")
- [ ] Pre-run the Coding Agent on that issue so a draft PR exists (for smooth demo pacing)
- [ ] Have a second PR with Copilot Code Review comments already visible
- [ ] Install the `gh aw` CLI extension and have a sample `.md` workflow ready in `.github/workflows/`
- [ ] Compile the sample agentic workflow: `gh aw compile`
- [ ] Browser tabs open: demo repo (Issues, PRs), GitHub Agentic Workflows documentation



For demo-script.md, update with this content:
# Copilot Agentic Workflows — Lunch & Learn Demo Script

> **Session Duration:** 15–20 minutes  
> **Presenter:** @commit2cloud  
> **Demo App:** [octodemo/octocat_supply](https://github.com/octodemo/octocat_supply)  
> **Audience:** Mixed experience levels — from new Copilot users to experienced practitioners

---

## Segment 1 — What Are Agentic Workflows? (3 min)

### Goal

Level-set the room on what "agentic" means in the context of software development, and frame the rest of the session for all experience levels.

### Talking Points

> "Before we jump into demos, let me set the stage. When we talk about **agentic workflows**, we mean AI that doesn't just suggest a line of code — it takes action. It reads your issue, plans a solution, writes the code, runs tests, and opens a pull request."

**For those new to Copilot:** This goes beyond autocomplete in your editor. These are AI agents that can work independently on tasks you assign them.

**For experienced users:** You've likely used Agent Mode in your IDE for real-time pairing. Today we're focusing on the async cloud-based agents and continuous automation.

**Two modes to know:**

| Mode | How It Works | When to Use It |
|------|-------------|---------------|
| **Synchronous (Agent Mode)** | Real-time in your IDE — you watch, guide, and course-correct as Copilot works | Prototyping, pair programming, exploratory coding |
| **Asynchronous (Coding Agent)** | Background in the cloud — assign an issue, walk away, come back to a PR | Well-scoped tasks, sprint backlog items, maintenance |

> "Think of sync as pair programming and async as delegating to a junior developer. And there's a third pattern — **Continuous AI** — where agents run automatically on repo events, like triaging new issues or analyzing CI failures. We'll see that with GitHub Agentic Workflows."

### Transition

> "Let's start with the async side — the Coding Agent."

---

## Segment 2 — Coding Agent: Issue → PR (6 min)

### Goal

Demonstrate the full async loop: assign an issue to Copilot, the agent works autonomously, and a PR appears.

### Demo Steps

**Show the Issue (1 min)**

1. Open the demo repo on GitHub → **Issues** tab
2. Show a pre-created issue: *"Add a discount code field to the checkout page"*
3. Point out: clear title, description with acceptance criteria, labels

> **Talking point:** "Good issues make good agents. The more context you put into the issue — acceptance criteria, links, constraints — the better the result. This is true for human developers and AI agents alike."

**For new users:** Think of the issue as your specification. The agent treats it like a work ticket.

**For experienced users:** You can reference Custom Instructions, link to design docs, or specify test coverage requirements — the agent reads all of it.

**Assign to Copilot (1 min)**

4. Click **Assignees** → select `@copilot`
5. Show the status banner: *"Copilot is working on this issue…"*
6. Explain what's happening behind the scenes:

> "The agent spins up a secure sandboxed environment via GitHub Actions. It reads your repo — code, tests, custom instructions, CI config — builds a plan, and starts coding. No local machine needed, no compute on your end. It's all happening in GitHub's cloud."

**Review the PR (3 min)**

7. Switch to the **Pull Requests** tab → open the draft PR the agent created (pre-prepared)
8. Walk through the changes:
   - New component or field added
   - Tests written
   - CI pipeline passing (green checks)
9. Show the agent's session log (the summary comment on the PR)

> **Talking point:** "Notice three things: it followed the repo's coding patterns, it wrote tests, and CI is green. The agent didn't just generate code — it validated its own work. But it's still a *draft* PR. Your team reviews and approves before it ships."

**For new users:** This is like having an extra developer who works 24/7, but always submits their work for review.

**For experienced users:** The agent respects your `.github/copilot-instructions.md`, integrates with your test suite, and iterates based on CI feedback.

**Show the Iteration Loop (1 min)**

10. Leave a review comment: *"Please also add input validation for the discount code format"*
11. Point out: "The agent picks this up and pushes another commit. It's a conversation — just like working with a teammate on a PR."

> **Talking point:** "You can @mention the agent in PR comments, ask it to refactor, add features, or fix bugs. It responds to feedback and iterates."

### Transition

> "So the agent wrote the code. But who reviews it? Let's talk about Copilot Code Review."

---

## Segment 3 — Copilot Code Review (4 min)

### Goal

Show how Copilot can act as a first-pass reviewer on any pull request — catching bugs, suggesting improvements, and accelerating the review cycle.

### Talking Points

> "Code review is where most teams hit a bottleneck. PRs sit for hours or days waiting for a reviewer. Copilot Code Review doesn't replace your human reviewers — it gives them a head start."

**For new users:** Think of this as spell-check for code — it catches common issues before your team even looks.

**For experienced users:** It uses the same agentic architecture as Coding Agent, exploring related files and dependencies to find cross-file issues.

### Demo Steps

**Request a Review (1 min)**

1. On the agent's PR (or a second pre-prepared PR), click **Reviewers** → add **Copilot**
2. Wait ~30 seconds — Copilot analyzes the diff and surrounding code context

> **Talking point:** "Copilot reads the full diff plus the surrounding code — not just the changed lines. Since the recent agentic architecture update, it explores related files and cross-file dependencies."

**Walk Through the Feedback (2 min)**

3. Show Copilot's inline comments:
   - A potential bug (e.g., missing null check)
   - A style suggestion
   - A one-click suggested fix
4. Click **"Commit suggestion"** on one of the suggestions — show the fix applied instantly
5. Point out the review type: *"Comment"* — not Approve or Request Changes

> **Talking point:** "Copilot reviews are always 'Comment' type — they never block a merge or count toward required approvals. Your team's approval rules stay exactly as they are. Think of it as a helpful colleague doing a first pass before your senior engineers review."

**Key Benefits (1 min)**

> "What this means for your team:
> - **Faster feedback loops** — developers get instant reviews instead of waiting hours
> - **Better human reviews** — your reviewers focus on architecture and logic, not typos and missing null checks
> - **Learning opportunity** — newer team members see best practices highlighted in real-time"

### Transition

> "So we've seen agents that code and agents that review. But what about the tasks that happen *continuously* in your repo? That's where GitHub Agentic Workflows come in."

---

## Segment 4 — GitHub Agentic Workflows (4 min)

### Goal

Introduce GitHub Agentic Workflows (`gh-aw`) — Markdown-authored, event-driven repo automation that lets AI agents handle recurring tasks like issue triage, documentation maintenance, and CI failure analysis.

### Talking Points

> "Everything we've seen so far — Coding Agent, Code Review — involves a human kicking off a task. But what about the tasks that happen *continuously*? Issue triage, stale PR cleanup, CI failure investigation, doc updates. Those are the grind work that pulls your team away from building features."

**For new users:** This is automation, but instead of writing scripts, you write what you want in plain English.

**For experienced users:** Think GitHub Actions, but declarative and intent-driven instead of imperative YAML.

### Demo Steps

**Explain the Concept (1 min)**

1. Open the [GitHub Agentic Workflows docs](https://github.github.com/gh-aw/) in the browser (or show a slide)
2. Key framing:

> "Agentic Workflows are like GitHub Actions, but instead of writing imperative YAML step-by-step, you write **Markdown** — plain English describing what you want to happen. An AI agent interprets your intent and executes it. And there's a security model: agents get read-only access by default and can only perform write operations you explicitly allow."

**Show a Workflow File (2 min)**

3. Open a sample `.github/workflows/issue-triage.md` file in the demo repo:

   ````markdown
   ---
   on:
     issues:
       types: [opened, reopened]
   permissions:
     issues: read
   safe-outputs:
     add-labels: {}
     add-comment: {}
   ---
   # Issue Triage

   Analyze every new issue. Assign the appropriate label (bug, enhancement,
   documentation, question). If the issue is unclear, comment asking for
   more details.
   ````

4. Walk through the two sections:
   - **YAML frontmatter** — triggers (`on: issues`), permissions (read-only by default), and safe-outputs (the *only* write operations the agent can perform)
   - **Markdown body** — natural-language intent describing what the agent should do

> **Talking point:** "Notice the security model: the agent gets read-only access by default. The only things it can *write* are explicitly listed under `safe-outputs`. No surprise commits, no uncontrolled actions. You're in control."

**For new users:** The frontmatter tells GitHub *when* to run this (like when a new issue is opened). The Markdown tells the agent *what* to do.

**For experienced users:** This compiles to a standard GitHub Actions workflow with guardrails. You version control both the `.md` source and the generated `.lock.yml` artifact.

**Compile and Run (1 min)**

5. Show the compile step:
   ```bash
   gh aw compile
   ```
6. Explain: "This generates a hardened `.lock.yml` file — a standard GitHub Actions workflow that runs the AI agent. You commit both the `.md` and the `.lock.yml`."

7. Show a live example or screenshot of the workflow running:
   - New issue opened → workflow triggers → agent labels it and comments

> **Talking point:** "This is Continuous AI. Every new issue gets triaged automatically. Every CI failure gets investigated. Your team stops context-switching on maintenance and focuses on building features. And there's a growing sample library at [githubnext/agentics](https://github.com/githubnext/agentics) with templates for common patterns."

### Transition

> "Let me wrap up with a quick recap."

---

## Segment 5 — Wrap-Up & Q&A (1 min)

### Closing Summary

> "Here's what we covered in the last 18 minutes:
>
> | What | Why It Matters |
> |------|---------------|
> | **Agentic Workflows (Concept)** | AI that takes action, not just suggests — sync for pairing, async for delegation |
> | **Coding Agent** | Assign an issue, get a PR — autonomous coding in the cloud |
> | **Code Review** | AI first-pass review that accelerates your team's review cycle |
> | **GitHub Agentic Workflows (gh-aw)** | Markdown-authored Continuous AI — event-driven repo automation with security guardrails |
>
> The common thread: **humans stay in the loop**. Agents do the heavy lifting, but your team makes the decisions. No code merges without human approval."

### Open Q&A

> "What questions do you have? Happy to dive deeper into any of these areas — or talk about how to get started with your team."

---

## Q&A Prep — Likely Questions

| Question | Key Points |
|----------|-----------|
| "How do we get started with the Coding Agent?" | Enable it in your org's Copilot settings. Assign any well-scoped issue to `@copilot`. Start with low-risk tasks — docs updates, test coverage, bug fixes. |
| "Is the Coding Agent safe? Can it break production?" | It runs in a sandboxed GitHub Actions environment. All output is a draft PR — nothing merges without human review. Branch protections and required approvals still apply. |
| "What does this cost?" | Coding Agent and Code Review are included with Copilot Business and Enterprise. No additional per-seat fees. Premium requests may apply for heavy usage. |
| "Can we use this with our existing CI/CD?" | Yes — the agent triggers your existing CI workflows. If your tests fail, the agent sees the failure and tries to fix it. Your pipeline doesn't change. |
| "How do Agentic Workflows differ from GitHub Actions?" | Actions are imperative YAML — you script every step. Agentic Workflows are intent-driven Markdown — you describe the goal, and an AI agent figures out how to achieve it. |
| "What about IP and code privacy?" | Copilot Enterprise: no code used for training, data encrypted in transit and at rest, content exclusions available for sensitive repos. |
| "Can I customize how the agents work?" | Yes — Custom Instructions (`.github/copilot-instructions.md`) let you define coding standards, conventions, and preferences. Agents read and follow them. |
| "What if the agent makes a mistake?" | It's a draft PR. Review it like any other PR. Leave comments, request changes, or close it. The agent learns from feedback in the same PR thread. |

---

## Post-Session Follow-Up

- [ ] Share this agenda and any demo recordings with attendees
- [ ] Send relevant links (see below)
- [ ] Offer a deeper hands-on session if the team wants to try the Coding Agent themselves
- [ ] Check in at 2 weeks for feedback and adoption progress

## Useful Links

**Agentic Workflows:**
- [From idea to PR: A guide to GitHub Copilot's agentic workflows](https://github.blog/ai-and-ml/github-copilot/from-idea-to-pr-a-guide-to-github-copilots-agentic-workflows/)
- [Coding Agent 101: Getting started](https://github.blog/ai-and-ml/github-copilot/github-copilot-coding-agent-101-getting-started-with-agentic-workflows-on-github/)
- [The difference between coding agent and agent mode](https://github.blog/developer-skills/github/less-todo-more-done-the-difference-between-coding-agent-and-agent-mode-in-github-copilot/)

**GitHub Agentic Workflows (gh-aw):**
- [GitHub Agentic Workflows docs](https://github.github.com/gh-aw/)
- [Automate repository tasks with GitHub Agentic Workflows (blog)](https://github.blog/ai-and-ml/automate-repository-tasks-with-github-agentic-workflows/)
- [GitHub Agentic Workflows are now in technical preview (changelog)](https://github.blog/changelog/2026-02-13-github-agentic-workflows-are-now-in-technical-preview/)
- [githubnext/agentics — sample workflow templates](https://github.com/githubnext/agentics)

**Code Review:**
- [Using Copilot Code Review (docs)](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/request-a-code-review/use-code-review)
- [Copilot Code Review now runs on an agentic architecture](https://github.blog/changelog/2026-03-05-copilot-code-review-now-runs-on-an-agentic-architecture/)

**Demo Repo:**
- [octodemo/octocat_supply](https://github.com/octodemo/octocat_supply)