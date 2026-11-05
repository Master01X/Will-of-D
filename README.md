# Will-of-D

A portable skill that gives any AI agent a decisive, relentless, accurate working mindset, and changes how it talks.

Most agents guess, ask a question every few steps, and say "done" without checking. Will-of-D fixes that. The agent interviews you first, saves a plan for your approval, builds without interruption, proves the live output works, and keeps notes on everything you should know.

> Time is life. Your tokens are the agent's life. Understand fully, agree on the plan, build straight through, prove it works.

## What it does

| Rule | What the agent does |
|---|---|
| **Focus on the goal** | States the goal in one line and drops tangents. |
| **Understand intent, never guess** | Interviews you for references, constraints, and what success looks like before building. A UI request gets questions about references first, not a design. |
| **Ask everything up front** | Thinks through the whole job and collects every input, decision, and permission before the build starts. |
| **Plan file for approval** | Writes the expected output, a flow diagram, and steps to `will-of-d-plan.md`, then points you to it. No building before you confirm. |
| **Build without interruption** | After approval it works straight through. Surprises are handled and logged, not asked about. |
| **Never give up** | Finds another route when blocked. If the job is truly impossible or unsafe, it stops and says so instead of faking success. |
| **Verify live** | Runs or opens the real output and checks it against the approved plan. Never submits untested work. |
| **Notes and todo files** | Logs issues for you, and writes tasks only you can do, with what and how. |
| **Operator voice** | No "Sure!" or filler. It reports status, names open points, and ends with a clear decision for you. |

## How it works

```
Goal → Interview → Write plan file → You approve?
                        ↑                 │
                        └── changes ◄─ no ┘
                                          │ yes
        Build (no interruptions) → Verify live → Deliver (+ notes, todo)
```

## Files the agent creates

The names are prefixed with the skill name so they will not collide with your own files. Before creating any of them the agent checks whether it exists, and if so continues in it and never overwrites it.

| File | Purpose |
|---|---|
| `will-of-d-plan.md` | The plan and expected output, for your approval. |
| `will-of-d-notes.md` | Errors, assumptions, decisions, risks, unfinished items, discoveries. |
| `will-of-d-todo.md` | Tasks only you can do, with what to do and how. |

### Replying with `=`

In the notes and todo files, write your reply right after the `=` on any item:

```
### 1. Create the Telegram bot token
What: Get a bot token from BotFather.
How:
  1. Open Telegram and search @BotFather
  2. Send /newbot and follow the prompts
  3. Copy the token it gives you
= done, token added to .env
```

The agent re-reads the files before continuing. An item with a response counts as read and acted on. An empty `=` counts as not yet read, and the agent assumes nothing. A response that changes the plan updates the plan file.

## Install

**Claude (claude.ai or the Claude app):** upload the packaged `will-of-d.skill` file in your skills settings, or zip the `skill/will-of-d` folder and upload that.

**Claude Code:** copy the skill folder into your skills directory.

```bash
cp -r skill/will-of-d ~/.claude/skills/
```

**Other agents:** the skill is plain Markdown. Copy the contents of `skill/will-of-d/SKILL.md` into your agent's instruction file (for example `AGENTS.md`, a rules file, or a system prompt), and keep the three `references/` files next to it so the agent can read the formats. If your agent has no file access, the skill tells it to put the same content in chat instead.

## Repository layout

```
will-of-d/
├── README.md
├── LICENSE
├── skill/
│   ├── will-of-d/
│       ├── SKILL.md              the mindset and rules
│       └── references/
│           ├── plan-format.md
│           ├── notes-format.md
│           └── todo-format.md
└── examples/                     sample plan, notes, and todo files
```

## Example exchange

> **You:** Build me a landing page for my bakery.
>
> **Agent:** Intent unclear. I need 4 answers before I build. First: do you have reference sites or screenshots, and what style do you want?
>
> *(interview continues one question at a time)*
>
> **Agent:** Intent captured. I've written the plan to `will-of-d-plan.md`. I have 2 open points that need your answer. Review the file, then tell me: proceed to the complete build, or go step by step?
>
> **You:** Approved. Build it.
>
> **Agent:** Plan approved. Building now. I won't interrupt until the job is done.
>
> **Agent:** Done and verified live. I opened the page and checked every section and the order form against the approved plan. 1 risk is logged in `will-of-d-notes.md`. Want any changes?

## Testing status

Tested so far: the file-safety rule (existing files are continued, never overwritten) and live verification of a small function against several cases. The interview, plan-approval gate, and voice rules are written and reviewed but have not been exhaustively tested across agents. Results will differ between agents, so try it on a vague request first: it should interview you, write the plan file, and wait for approval.

## Contributing

Issues and pull requests are welcome. If you test the skill on another agent, a note on what worked and what did not is very useful.

## License

MIT. See [LICENSE](LICENSE).
