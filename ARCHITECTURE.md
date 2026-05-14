# Personal Knowledge Architecture

I model myself across five git repositories. Each one captures a different dimension
of who I am and how I operate. Together they function as a personal OS — not a
productivity system, but a structured representation of a person.

---

## The five repositories

| Repository | What it models |
|---|---|
| `logician666` | Identity — who I am, career, profile |
| `thoughts` | Thinking — life strategy, decisions, journals, personal memory |
| `knowledge` | Knowledge — what I have formally learned and validated |
| `laboratory-configs` | Setup — my Linux workstation, tooling, and work environment |
| `parkour` | Training — my physical conditioning programme |

The cuts are not arbitrary. Each repo answers a different question:
*Who am I? How do I think? What do I know? How do I work? How do I move?*

---

## The core distinction: thinking vs. knowledge

The most important boundary in the system is between `thoughts` and `knowledge`.

**`thoughts`** is where I think out loud. Journals, fragments, life strategy, decisions.
Content here is unvalidated, exploratory, and personal. It is allowed to be incomplete,
wrong, or half-formed. Its job is not to be correct — it is to be honest.

**`knowledge`** is where I record what I have actually understood. Every node in the
knowledge repo is dependency-ordered: it says what must be understood before it, and
what it unlocks. Nothing enters a knowledge node without being validated — first
encountered in a source, then understood, then scribed. The repo is not a storage
system. It is a model of my current epistemic state.

The separation exists because conflating the two produces a pile of notes — some true,
some speculative, some stale — that can only be searched, not reasoned about.

---

## Bounded contexts

Each repository has a `CLAUDE.md` file that defines its purpose, scope, and constraints.
Content never crosses boundaries:

- Personal strategy and life thinking never enters `knowledge`
- Formal knowledge nodes never enter `thoughts`
- Parkour content stays in `parkour`

When a thought in `thoughts` connects to a knowledge node, I use a notation convention
(`→knowledge:node-name`) to mark the connection without merging the contexts. The repos
stay separate; the links are traceable.

---

## How the system moves

**From thought to knowledge:**
`thoughts/journal` → `thoughts/synthesis` → `thoughts/fragments` → `knowledge/nodes/inbox` → `knowledge/nodes/`

A journal entry surfaces a half-formed idea. A monthly synthesis pass extracts patterns
and promotes sharp ideas to fragments. A fragment that proves durable and validated
gets routed to the knowledge inbox. The inbox is a staging area — content stays there
until it survives a return visit. Then it earns a node.

**Decisions:**
Significant choices — career model, certification path, exit conditions — live in
`thoughts/decisions/` as formal records. Each one has context, options considered,
the decision, rationale, and a review trigger. They are not journal entries;
they are commitments with an audit trail.

**Synthesis:**
Once a month I do a synthesis pass over recent journals. The output is a synthesis
document that names patterns, surfaces decisions, promotes fragments, and identifies
knowledge candidates. It is the mechanism that prevents `thoughts` from becoming
a chronological log with no emergent structure.

---

## The role of AI

Each repository has a `CLAUDE.md` file that governs how Claude Code behaves when
working inside it. This is not just configuration — it is a form of context management.
The AI operating in `thoughts` knows it is in a personal thinking space and responds
accordingly. The AI in `knowledge` knows it is in a formal learning system and will
not scribe unvalidated content.

Two automated routines run in the background:

- **Weekly:** validates `laboratory-configs` for gaps and opens a GitHub issue if
  anything would break a fresh machine migration
- **Quarterly:** reviews the `logician666` profile vault for drift against reality

Auto-commit hooks in `thoughts` and `knowledge` ensure that edits made during a
Claude Code session are immediately committed — the session leaves a trace.

---

## What makes this different from other PKM approaches

I am not trying to be productive. I am trying to be accurate — about what I know,
what I have decided, and who I am.

Zettelkasten is associative: notes link to whatever they connect to. My knowledge
repo is dependency-ordered: a node's position in the graph encodes what it
presupposes and what it enables. You can query it — not just search it.

PARA organises by actionability. This system organises by the nature of the content
itself. A thought and a knowledge node are fundamentally different kinds of things;
they deserve different homes.

Most PKM systems are single-vault. This one is multi-repo because the content types
are genuinely distinct and cross-contamination degrades both. A personal journal entry
and a formal ontology node should not live in the same place.

---

## The honest tradeoff

The system works only if the scribing discipline holds. A knowledge node that isn't
written stays in someone's head — outside the model. A synthesis pass that doesn't
happen leaves journals as a time-series log with no synthesis.

The architecture is sound. The weak point is always execution.

---

## Adapting this

The five repos reflect my specific life — the cuts between identity, thinking,
knowledge, work setup, and physical training made sense for me. Yours may be
different. The principle that transfers: **model the distinct dimensions of yourself
in separate bounded contexts, and be rigorous about what belongs where.**

The knowledge architecture (dependency-ordered nodes, validated/exploratory separation,
inbox staging) transfers more directly. It is a general answer to the question of
how to build a knowledge system that remains queryable as it grows.

---

*Profile vault: [`logician666/profile/`](profile/Hisham.md)*
*Stack: Obsidian · Git · Claude Code*
