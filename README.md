# schematic

A skill that reverse engineers a detailed product and technical specification from a git branch's implementation.

Use it when:
- A branch has shipped or is in-progress and needs documentation
- You need to understand what a branch does at product and architecture level
- Onboarding to someone else's feature branch
- Creating PR descriptions or design docs after the fact

Produces a structured markdown spec covering problem statement, product requirements, architecture, technical design, file inventories, testing strategy, rollout plan, and risks.

## Install

### Claude Code

```bash
git clone https://github.com/blader/schematic.git ~/.claude/skills/schematic
```

Restart Claude Code to pick up the new skill.

### Codex

```bash
git clone https://github.com/blader/schematic.git ~/.codex/skills/schematic
```

Or use the built-in skill installer:

```
Install the skill from github.com/blader/schematic
```

Restart Codex to pick up the new skill.

## Usage

In Claude Code or Codex, just ask:

- "Reverse engineer a spec from this branch"
- "Analyze this branch"
- "Write a spec from the code"
- "Document what this branch does"

The skill will systematically analyze every file changed on the branch and produce a comprehensive specification document.

## How it works

1. **Scope the branch** - Gets the full diff stats and categorizes files
2. **Parallel deep exploration** - Launches 2-4 parallel agents to read file groups concurrently
3. **Cross-check for gaps** - Diffs analyzed files against the full file list to catch stragglers
4. **Write the spec** - Produces a structured 11-section markdown document
5. **Verify completeness** - Ensures every changed file is accounted for

## License

MIT
