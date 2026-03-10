## auto-skill

Make every token and every closed session **meaningful**.

`auto-skill` starts from a simple belief about vibe coding with AI:  
**we shouldn’t let our conversations – and the mistakes inside them – evaporate when a session ends.**

When we code with AI, we constantly discover things:

- Problems that only appear when human and model collaborate.
- Wrong turns that reveal hidden constraints in our codebase.
- Small tricks, prompts, and workflows that suddenly “just work”.

These are incredibly valuable, but today they usually disappear with the chat history.  
`auto-skill` tries to change that.

### Before & after (text flow)

Without `auto-skill`:

```text
┌──────────────────────────┐
│  Start coding with AI    │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Human + model explore   │
│  try / fail / fix        │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Session ends / tab      │
│  closed                  │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  ❌ Problems, wrong      │
│    turns, new tricks     │
│    disappear with chat   │
│  ❌ No memory next time  │
└──────────────────────────┘
```

With `auto-skill`:

```text
┌──────────────────────────┐
│  Start coding with AI    │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Human + model explore   │
│  try / fail / fix        │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Invoke auto-skill       │
│  before closing session  │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Agent + you reflect:    │
│  • Problems we hit       │
│  • What finally worked   │
│  • What we learned       │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  Turn insights into      │
│  artefacts:              │
│  • skills/<skill>/       │
│    SKILL.md              │
│  • AGENTS.md constraints │
│  • Optional SQL/JSON log │
└──────────────┬───────────┘
               │
               v
┌──────────────────────────┐
│  ✅ Knowledge carried    │
│     into future sessions │
│  ✅ Mistakes become      │
│     constraints & skills │
└──────────────────────────┘
```

The original purpose of this project is to make that reflection **easy and habitual**:  
so that every session leaves behind problems discovered, lessons learned, and new skills written down – instead of being lost when you close the window.

### Goals

- **Capture value from every session**: no more “wasted” tokens or forgotten experiments.
- **Turn mistakes into constraints**: explicitly record what should *not* be repeated in this project.
- **Grow a personal/Team skill library**: new patterns become Skills instead of staying buried in old chats.
- **Support two-way collaboration with agents**: not only “AI helps you”, but you and the agent co-design better rules, skills, and workflows over time.

### What auto-skill can help record

In a typical coding session, `auto-skill` aims to help you:

- **Problems encountered**
  - Bugs, dead-ends, confusing API behaviour.
  - Why the first attempts failed; how you fixed them.
- **New skills learned**
  - New tools, libraries, patterns, workflows.
  - “Recipes” that you want to reuse in future sessions.
- **Project-specific constraints**
  - Things you *must* respect in this repo (architecture, style, performance, product rules).
  - Mistakes that should not be repeated, turned into explicit “guardrails”.
- **Agent collaboration context**
  - Ideas that belong in `AGENTS.md` (how you want agents to behave here).
  - Notes you want the agent to remember next time so you don’t have to re-explain them.

These outputs can be written to:

- `skills/<skill name>/SKILL.md` – new or improved Skills for reuse.
- `AGENTS.md` – rules and preferences for agents in this repo.
- Other files (for example, a SQL database or JSON log) if you want a more structured knowledge store.

### Repository structure

Current minimal structure:

- `README.md` – this overview and philosophy.
- `skills/auto-skill/SKILL.md` – the `auto-skill` Cursor Skill definition and behaviour.

You can extend this pattern by adding more skills:

- `skills/<your-skill-id>/SKILL.md`

For example:

- `skills/web-ui-pitfalls/SKILL.md`
- `skills/ios-iap-helper/SKILL.md`

Each folder groups the Skill plus any supporting examples or assets.

### Usage (high level idea)

This repo does **not** lock you into a single implementation. Instead, it suggests a workflow:

1. **Work normally with your agent** on a coding task.
2. **Before closing the session**, invoke the `auto-skill` flow.
3. The agent:
   - Reviews what happened in the session.
   - Extracts problems, lessons, new skills, and constraints.
   - Suggests updates to `SKILL.md`, `AGENTS.md`, or other knowledge files.
4. You review the suggestions, adjust wording if needed, and save.

Over time, this builds a living knowledge base for your project and your personal way of working.

---

### Why this matters

Most AI coding workflows optimise for *speed in the current session* and ignore the long-term value of what we learned along the way. `auto-skill` focuses on the opposite:

- **Every session should leave a trace.**
- **Every meaningful mistake should improve future constraints.**
- **Every new pattern should be one step closer to a reusable Skill.**

If this resonates with you, feel free to fork, extend the `SKILL.md`, and adapt the workflow to your own projects.
