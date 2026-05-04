---
name: premortem
description: "Run a premortem on any plan, launch, product, hire, strategy, or decision. Assumes it already failed 6 months from now and works backward to find every reason why. Produces a revised plan with blind spots exposed. MANDATORY TRIGGERS: 'premortem this', 'premortem my', 'run a premortem', 'what could kill this', 'future-proof this', 'stress test this plan', 'what am i missing here', 'find the blind spots'. STRONG TRIGGERS: 'what could go wrong', 'am i missing anything', 'poke holes in this', 'where will this break', 'devil's advocate this'. Do NOT trigger on simple feedback requests, factual questions, or LLM Council requests. DO trigger when someone has a plan or commitment where the cost of being wrong is high."
---

# Premortem Skill

## What is a Premortem?

A premortem is the **opposite of a postmortem**. Instead of figuring out what went wrong after something fails, you imagine it already failed and figure out *why* — before you start.

The technique comes from psychologist **Gary Klein** and was published in the *Harvard Business Review*. **Daniel Kahneman** (Nobel Prize-winning author of *Thinking, Fast and Slow*) called it his single most valuable decision-making tool. Google, Goldman Sachs, and Procter & Gamble all use it before major launches and decisions.

### Why it works

When you ask "what could go wrong?" — people give cautious, hedged answers. When you say **"this already failed, tell me why"** — brains switch into narrative mode. The output becomes more specific, more creative, and far more honest. Wharton and Cornell researchers called this **"prospective hindsight"** and found it significantly increases the ability to identify causes of future outcomes.

### Why it matters for AI-assisted decisions

Claude defaults to agreeable, optimistic responses. Ask "is this a good plan?" and it searches for reasons to say yes. The premortem breaks this pattern by locking the frame as failure. Claude stops looking for reasons your plan will work and starts explaining how it fell apart.

---

## When to Run a Premortem

**Good targets:**
- A product or feature you're about to build
- A launch with money or reputation on the line
- A pricing change or business model shift
- A hire you're about to make
- A strategy or positioning pivot
- A partnership or deal you're evaluating
- Any commitment where the cost of being wrong is high

**Poor targets:**
- Vague ideas with no concrete plan yet (develop the plan first, then premortem)
- Questions with one right answer (just answer them)
- Creative feedback requests on a draft (that's editing, not a premortem)
- Decisions already made and irreversible (only useful when you can still change course)

---

## How to Trigger

Just give Claude your plan and say:

> **"Run a premortem on this plan."**

Or any of these natural phrases:
- *"Premortem this"*
- *"What could kill this?"*
- *"Stress test this plan"*
- *"Find the blind spots"*
- *"What am I missing here?"*

---

## How It Works (Step by Step)

### Step 1 — Context Gathering

Before running the premortem, Claude scans for existing context: the current conversation, any uploaded files, workspace files like `CLAUDE.md`, and anything relevant to the plan. It evaluates whether it has enough to run a useful premortem across three dimensions:

1. **What is it?** — A clear description of the thing being analyzed
2. **Who is it for?** — The audience, customer, team, or stakeholders
3. **What does success look like?** — The intended outcome (failure = inverting this)

If anything is missing, Claude asks one focused question at a time — conversational, not interrogative — until the threshold is met.

### Step 2 — Set the Frame

Claude sets the premortem frame explicitly before any analysis:

> *"It's 6 months from now. [The plan] has failed. It's done. We're looking back trying to understand what went wrong."*

This framing is the psychological mechanism. Without it, the analysis defaults to polite risk assessment instead of honest failure identification.

### Step 3 — Generate Failure Reasons

Claude runs a raw premortem: a comprehensive list of every genuine reason the plan could have died. No prescribed categories. No lenses. Just the core Klein method applied to the specific plan.

Each failure reason is:
- **Specific** to this plan (not generic advice)
- **Grounded** in actual details provided
- A **genuine threat** (not a minor inconvenience or extreme edge case)

The number of failure reasons should be whatever is real — not padded to a round number, not truncated early.

### Step 4 — Deep-Dive on Each Failure (Parallel Agents)

For every failure reason identified, Claude spawns a sub-agent to go deep independently. Each agent produces:

1. **The Failure Story** — A 2-3 paragraph narrative of how this specific failure played out. Specific. Grounded in plan details. Written like a case study of something that actually happened.

2. **The Underlying Assumption** — The one thing the user was taking for granted that made this failure possible. One sentence.

3. **Early Warning Signs** — 1-2 concrete, observable signals to watch for that would indicate this failure mode is starting to play out. Things you can actually see or measure.

All agents run in parallel so earlier findings don't contaminate later ones.

### Step 5 — Synthesis

After all deep-dives complete, Claude produces the synthesis:

| Section | What it contains |
|---|---|
| **Most Likely Failure** | The scenario most probable given the plan. Why. What to focus on first. |
| **Most Dangerous Failure** | The scenario causing the most damage if it happens — even if less likely. Worth insuring against. |
| **The Hidden Assumption** | The single biggest assumption being made that probably hasn't been questioned. Often the most valuable output of the entire premortem. |
| **Revised Plan** | Specific, concrete changes that make the plan more resilient. Each change maps to a failure scenario. Not "consider your pricing" — "test pricing at $X with 20 people before committing publicly." |
| **Pre-Launch Checklist** | 3-5 specific things to verify, test, or put in place before executing — each one preventing or detecting a specific failure mode. |

### Step 6 — Report & Transcript

The session produces two files:

```
premortem-report-[timestamp].html    # visual report for scanning
premortem-transcript-[timestamp].md  # full reasoning for reference
```

The HTML report surfaces the synthesis prominently (most people read this first), then shows one card per failure reason with the deep-dive details. The transcript preserves the full reasoning chain.

---

## Output Example

**Input:**
> "Premortem this: I'm launching a $297 live workshop on Claude for marketing teams. 50 seats. Targeting marketing managers at companies with 10–50 employees."

**Raw premortem finds 6 failure reasons:**
1. Marketing managers at this company size need approval to spend $297 — friction you haven't accounted for
2. "Claude for marketing teams" is a tool-specific pitch; most managers are still figuring out whether AI is relevant at all
3. The audience that actually buys might be solopreneurs, not team managers — content/attendee mismatch
4. Realistic demo environments with multi-seat setups take 5 weeks to build, not the 2 budgeted
5. If 60% of attendees are solopreneurs, your reviews won't resonate with the team-manager audience for future cohorts
6. At $297 × 50 seats = $14,850 max — may not justify prep time against other opportunities

**6 agents go deep on each in parallel.**

**Synthesis output:**
- **Most likely failure:** Audience doesn't self-identify as "marketing managers at 10–50 person companies" and doesn't congregate in reachable places.
- **Most dangerous failure:** Attracting solopreneurs means case studies won't resonate with the target buyer for future cohorts — the problem compounds.
- **Hidden assumption:** You're assuming this audience is reachable through your existing channels.
- **Revised plan:** Run a $47 pilot with 20 people first. Build the full workshop for whoever actually shows up.

---

## Important Principles

- **Always spawn agents in parallel** — sequential spawning lets early responses bias later ones
- **Always set the premortem frame** — "this has already failed" is the psychological mechanism; without it, you get polite risk assessment
- **Be comprehensive, not padded** — the number of failure reasons should match reality, not a target
- **The synthesis is the product** — most users skim the failure cards; the synthesis is what changes decisions
- **Don't sugarcoat** — the entire point is to tell users what they don't want to hear before reality does
- **Revised plan must be concrete** — every revision should be something actionable this week
- **This is not a pros/cons list** — it's a narrative from the future, grounded in specifics

---

## Inspiration & Further Reading

- Gary Klein, *"Performing a Project Premortem"* — Harvard Business Review
- Daniel Kahneman, *Thinking, Fast and Slow* (Chapter on overconfidence and pre-mortems)
- Deborah Mitchell et al., *"Back to the Future: Temporal Perspective in the Explanation of Events"* — Journal of Behavioral Decision Making (the "prospective hindsight" research)
