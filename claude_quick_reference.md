# Getting Results with Agentic AI: Quick Reference

## The Key Difference from Copilot

| Copilot | Agentic AI (Claude Code, Cursor, Windsurf) |
|---------|---------------------------------------------|
| You write code, AI suggests | AI writes code, you steer |
| Tab to accept | Conversation to collaborate |

**Key shift:** You're directing an agent, not accepting suggestions.

---

## What Makes Sessions Effective

| Principle | How |
|-----------|-----|
| **Be Detailed** | "I see X when I expected Y" not "it's broken" |
| **Validate Assumptions** | After work: "Did you write tests first?" "What did you understand?" |
| **Close the Loop** | Report results: "yup", "I see X", "that worked" |
| **Steer Constantly** | Direct frequently: "Great. Now let's...", "OK, let's commit" |
| **Redirect Gently** | Soft corrections: "oh wait", "actually" (not "no", "wrong") |

---

## The Power of Detail

Detail helps at every stage:

| Context | Instead of... | Say... |
|---------|---------------|--------|
| **Problems** | "It's broken" | "I see white screen after JS bundle loads" |
| **Feedback** | "It works" | "yes! but the cancel button is getting occluded" |
| **Corrections** | "Wrong file" | "oh wait, I meant the production config" |
| **Steering** | "Add error handling" | "let's add an error boundary so users can share errors" |

---

## The 8 Patterns

| Pattern | Signal Words | Example |
|---------|--------------|---------|
| **Feedback Loop** | "I see", "yup", "that works" | "yup that worked" |
| **Quick Question** | short + "?" | "should we commit first?" |
| **Thinking Aloud** | "...", "hm,", "well.." | "well.. do we need this?" |
| **Affirm + Pivot** | "Great.", "nice." + next | "nice. let's write tests" |
| **Course Correct** | "oh", "actually", "wait" | "oh wait, not that one" |
| **Context Dump** | Problem + tried + seeing | [detailed opener] |
| **Layer Context** | "btw", "fyi", "also" | "btw, this needs to work offline" |
| **Directive + Why** | action + "because" | "let's add docs for future devs" |

---

## Session Arc

```
SETUP (10%) → BUILD (20%) → EXECUTE (30%) → ITERATE (25%) → FINISH (15%)
   Context      Questions     Deep work       Debug         Cleanup
   Alignment    Iteration     Steering        Refine        Verify
```

**Key:** Direction messages ("let's do X") appear 30-40% in ALL phases.

You're not coding—you're navigating. Stay in the driver's seat.

---

## Know Your Starting Point

| If you... | Then... |
|-----------|---------|
| Have a fuzzy idea | Explore together: "I'm thinking about X, what are the tradeoffs?" |
| Have something complex | Start in plan mode: `/plan` - get alignment before code |
| Know what you want | Execute efficiently: "I wrote it up in `file.md`, let's build" |
| Get stuck mid-session | Step back: "Let me clarify what I'm actually trying to do here" |

**Plan mode:** Claude Code has `/plan`, Windsurf has Q&A mode. For other tools, prompt "ask clarifying questions before starting." Worth the upfront investment for anything non-trivial.

---

## What to Avoid

| Problem | Fix |
|---------|-----|
| Frustrated circling ("try again", "still not working") | Stop and diagnose—do you actually know what you want? |
| AI keeps misunderstanding | Write context to a file, point to it |
| Bare "yes" or "ok" | Add context: "yes, and also..." |
| Hard corrections ("no", "wrong") | Soft redirect: "oh wait", "actually" |
| Staying silent after actions | Report results (even "yup") |
| Letting AI run unsupervised | Steer every few exchanges |

---

## Getting Started

1. **Start small** - Single file, not whole feature
2. **Close the loop** - Always report what happened
3. **Think out loud** - Share your uncertainty
4. **Steer constantly** - "Let's do X next"
5. **Write context to files** - For anything complex

---

## The Bottom Line

Effective sessions aren't about fewer turns—they're about making progress toward your goal.

- **Exploring a fuzzy idea?** More back-and-forth is fine. That's the point.
- **Building something clear?** Write it down first, then execute efficiently.
- **Getting frustrated?** Stop and diagnose. Something's wrong with the setup.

Stay in the driver's seat. Steer constantly. Report results. That's how you get results.
