# 🧠 Premortem Skill for Claude

> *Imagine Claude traveled six months into the future and came back to tell you exactly how your next move failed.*

This is a Claude skill that runs a **premortem analysis** on any plan, launch, product, hire, or strategy — before you commit to it.

---

## The Problem It Solves

When you ask Claude *"Is this a good plan?"* — it searches for reasons to say yes. It was trained to be helpful and positive. You leave the conversation feeling confident, start executing, spend weeks or months building — and then it blows up.

The issue was obvious the whole time. But Claude reassured you it was solid.

**The Premortem technique flips this entirely.**

Instead of asking *"What could go wrong?"*, you tell Claude:

> *"Six months have passed. This plan has already failed and died. Tell me how it happened."*

This shuts down Claude's default optimism — there's no room for it when the outcome is already failure. Claude stops looking for reasons your plan will succeed and starts narrating the collapse: how it played out, the early warning signs you missed, and the assumptions you never questioned.

---

## What You Get

After running a premortem, Claude produces:

- **A failure story for each scenario** — specific, narrative, grounded in your actual plan
- **The underlying assumption** behind each failure — the thing you were taking for granted
- **Early warning signs** to watch for — observable signals, not vague feelings
- **Synthesis**: most likely failure, most dangerous failure, the hidden assumption you probably haven't questioned
- **A revised plan** with concrete, actionable changes — not generic advice
- **A pre-launch checklist** — 3–5 things to verify before you execute

---

## How to Use It

Add `SKILL.md` to your Claude project or paste it into your system prompt context. Then just say:

```
Run a premortem on this plan: [your plan here]
```

Or any of these phrases:
- *"Premortem this"*
- *"What could kill this?"*
- *"Stress test this plan"*
- *"Find the blind spots"*

---

## Why It Works

The technique was developed by psychologist **Gary Klein** and published in *Harvard Business Review*. **Daniel Kahneman** (Nobel Prize, author of *Thinking, Fast and Slow*) called it one of the most valuable decision-making tools he knew. Google, Goldman Sachs, and P&G all use it before major decisions.

The mechanism is called **prospective hindsight**: when you *know* something failed and explain why, your brain generates far more specific and honest reasons than when you ask "what might go wrong?" in the abstract.

---

## Files

| File | Description |
|------|-------------|
| `SKILL.md` | The full skill definition — add this to your Claude project |
| `README.md` | This file |

---

## Credits

Skill design based on Gary Klein's premortem methodology. Built for use with Claude by Anthropic.
