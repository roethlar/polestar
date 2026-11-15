# Agent State

Keep only live work here; archive historical entries verbatim under
`docs/history/state-archive.md`. The `catchup` sweep performs hygiene;
`handoff` only snapshots. Use canonical pointers instead of copied counts.
Stamp volatile facts `as of <commit>`. Whether work has been pushed is
checked live in git and never stored here. Put machine facts in
`.agents/machines.md`, keyed by machine and dated.

## Now

- Governance bootstrap, directly on `next` (no work branch). On 2026-11-15
  upstream's agent file was carved out into `.agents/repo-guidance.md`. The
  bootstrap is finished when the root `AGENTS.md` is the toolkit's (its
  first line is "# Agent Guidance") and the owner has decided whether the
  governance commits are published to the fork. Check both live.
- No customization is recorded yet. As of 9fec78e2f the tree was clean,
  `next` was the only local branch, and there were no stashes or extra
  worktrees.

## Next

- Owner: name the first customization. The fork exists for them
  (`.agents/repo-guidance.md`, Mission Detail).
- Owner: decide whether to publish the governance commits to the fork
  (`.agents/push-policy.md` says ask first). Upstream's
  `.github/workflows/ci.yml` is written to run on any push to `next`. No
  workflow is registered in the fork today (`.agents/repo-guidance.md`,
  Verification), so whether a push would start it there is not known.
- Before the first merge from upstream or the first upstream bug fix: a
  remote for upstream, added on the owner's go (`.agents/repo-guidance.md`,
  Remotes & Sync).

## Blockers

- None recorded.

## Verification

- See `.agents/repo-guidance.md` (Verification). Record only a currently
  active deviation here.

## Active Sources

- `AGENTS.md`
- `.agents/repo-guidance.md`
- `.agents/decisions.md`

## Unrecorded Repo Memory

- Not settled: how a customization gets from this fork into the game.
  Which generated files are rebuilt, with which command, and whether this
  fork commits them is the owner's call. Upstream's rule that contributors
  do not commit generated files is about pull requests to upstream.
- No machine facts are recorded. Which of Lua, forge and the reference data
  a machine has decides which checks can run there;
  `node tools/polestar.js doctor` answers it live.
- The code review playbook expects `.agents/review/harnesses.local.json`
  to be git-ignored, and no rule in this repository ignores it. The owner
  settles where that rule goes before the first code review.
