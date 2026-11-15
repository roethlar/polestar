# Agent Decisions

Keep open decisions and rules that still lack another canonical home here.
Each entry must stand without chat, name its evidence, and identify what
it supersedes. Once a rule lives in operative guidance, move its rationale
verbatim to `docs/history/decisions-archive.md`; keep one archive pointer,
not a stub per entry.

## Decisions

<!--
### YYYY-MM-DD — <Title>

Status: Active | Adopted YYYY-MM-DD | Superseded

Decision: <Rule and canonical home.>
Evidence: <Incident, owner ruling, or verified observation.>
Supersedes: <Prior rule, if any.>

Active: currently operative here. Adopted: implemented in its canonical
home; archive the rationale. Superseded: replaced; name the replacement
and archive the original verbatim.
-->

### 2026-11-15 — Upstream's agent file carved out; the toolkit's AGENTS.md is the root agent file

Status: Active

Decision: This clone is governed by the toolkit's `AGENTS.md`. Everything
upstream's "Polestar: for coding agents" file carried (the project summary,
the task-to-skill table, the rules for every task) lives in
`.agents/repo-guidance.md`. Upstream's skills under `skills/` and
`CONTRIBUTING.md` are unchanged and remain the canonical detail.
Evidence: The governance refresh recorded in commit 9fec78e2f refused to
replace the file, calling it a foreign governance file. The owner then ran
the toolkit's bootstrap procedure on 2026-11-15 and approved the carve-out.
The last upstream version of the file is in commit 19bd636e7
(`git show 19bd636e7:AGENTS.md`).
Supersedes: The root `AGENTS.md` as of commit 19bd636e7.

### 2026-11-15 — The fork's next is the owner's personal line; an upstream bug fix carries none of it

Status: Active

Decision: This fork exists to customize the addon for the owner's personal
use. Its `next` holds upstream's `next`, the governance commits and the
customizations, differs from upstream on purpose, and takes upstream's
changes by merge. The rare bug fix for upstream is made on a branch cut
from upstream's `next` and carries neither governance files nor
customizations. Upstream's contribution process binds only such a fix. The
working rules are in `.agents/repo-guidance.md` (Mission Detail, Remotes &
Sync, Earned Practices).
Evidence: The owner's statement in the bootstrap session of 2026-11-15:
the fork is for personal customization, and the only contributions would
be obvious bug fixes. `gh repo view roethlar/polestar --json isFork,parent`
shows a fork of fitzforge/polestar, and
`gh repo view fitzforge/polestar --json viewerPermission` shows read
access, both on 2026-11-15. On the same day
`git ls-remote https://github.com/fitzforge/polestar.git refs/heads/next`
returned 19bd636e7, the commit the first governance commit sits on.
Upstream asks that personal agent settings stay out of commits meant for it
(`CONTRIBUTING.md`, "Using an AI agent"), and upstream keeps changing its
own agent file (`git log --oneline 19bd636e7 -- AGENTS.md` lists the
commits).
Supersedes: Nothing.

### 2026-11-15 — The fork tracks the toolkit's CLAUDE.md; upstream's ignore rule for it is removed here

Status: Active

Decision: This fork's `.gitignore` no longer ignores a root `CLAUDE.md`,
and the toolkit's one-line `CLAUDE.md` is installed and tracked like every
other toolkit file. The two other personal agent files upstream ignores
(a root CLAUDE.local.md, and a CLAUDE.md inside the .claude folder) stay
ignored. The rule is in `.agents/repo-guidance.md` (Earned Practices).
Evidence: Upstream added the ignore rule in commit cc39d6e94 so that each
contributor's personal agent file stays out of commits meant for upstream;
its comment warns that a committed `CLAUDE.md` would stop Claude Code
reading `AGENTS.md`, which a file whose one line imports `AGENTS.md` does
not do. The refresh recorded in commit 9fec78e2f flagged the path as
ignored and skipped it, and would have flagged it on every later run.
Owner ruling at the bootstrap approval of 2026-11-15.
Supersedes: Lines 29 to 33 of `.gitignore` as of commit 19bd636e7.

## Open Decisions

Unadopted findings change no process. Record verified evidence, options,
recommendation and the pending owner ruling. On adoption, record where
the rule landed and archive its rationale.

<!--
### YYYY-MM-DD — <Finding>

Status: Open
Evidence: <Observation and verification.>
Options: <Outcomes, including leaving the process unchanged.>
Recommendation: <Scope and reason.>
-->
