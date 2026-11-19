# software-crafting

An agent skill for [Claude Code](https://claude.com/claude-code) and other Claude surfaces that makes the agent work like a careful software crafter: test-first, in small green steps, with explicit refactoring, a fresh-eyes review, and an honest final report.

The whole skill is one file: [`SKILL.md`](SKILL.md).

## What it asks of the agent

1. **Understand before typing.** Read the code and its tests, restate the goal as observable behaviour, and list the test cases first.
2. **Red, green, refactor, commit.** One behaviour at a time, one small commit per green step, refactoring kept separate from behaviour changes.
3. **Handle the special cases.** Bug fixes start with a failing test; untested code gets characterization tests; spikes are labelled as spikes.
4. **Follow simple design rules.** Pass the tests, reveal intent, no duplicated knowledge, fewest elements.
5. **Keep its integrity.** Never weaken a test to get to green, never claim results it did not run, never call stubs finished.
6. **Review with fresh eyes.** Re-read the full diff as a reviewer, and run every check one last time.
7. **Capture what it learns.** Propose short notes for the project's `CLAUDE.md`.
8. **Report honestly.** What changed, the evidence, what is unverified, and the follow-ups.

## Install

Personal (available in all your projects):

```sh
git clone https://github.com/PSthelyBlog/software-crafting.git ~/.claude/skills/software-crafting
```

Per project (shared with your team through the repository):

```sh
git clone https://github.com/PSthelyBlog/software-crafting.git .claude/skills/software-crafting
```

On claude.ai, zip `SKILL.md` inside a `software-crafting/` folder and upload it under Settings → Capabilities → Skills.

## Use

The skill triggers on its own when you ask the agent to write, change, or refactor code. In Claude Code you can also invoke it explicitly with `/software-crafting`.

## License

[MIT](LICENSE)
