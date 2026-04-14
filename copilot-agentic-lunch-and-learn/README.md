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