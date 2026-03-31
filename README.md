# CLAUDE.md

Production-grade agent directives for Claude Code. Reverse-engineered from the source and hardened on billions of real-world agent logs.

## What This Is

Claude Code has bottlenecks that cause predictable failures: context compaction destroys working memory mid-refactor, file reads silently truncate at 2,000 lines, tool results get cut to 2,000-byte previews, and the default system prompt biases toward minimal output over correct output.

This CLAUDE.md overrides all of it.

Full technical breakdown: [https://www.linkedin.com/posts/samy-metref-77744133b_aileaks-breakingnews-aiagents-share-7444859568989405184-ea0R?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFVQ7wsBh8pyqoP08LZIkk4rZeGzc_HUjCk]

## Install

Drop it in your project root:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/predaaaasaaaaaaa/claude-md-directives/main/CLAUDE.md
```

Or clone and copy:

```bash
git clone https://github.com/predaaaasaaaaaaa/claude-md-directives.git
cp claude-md-directives/CLAUDE.md /path/to/your/project/
```

Claude Code reads CLAUDE.md from the project root automatically.

## What It Fixes

| Problem | Root Cause | Directive |
|---|---|---|
| "Done!" with 40 type errors | Success = bytes on disk, no compile check | Forced Verification |
| Hallucinations after ~15 messages | Auto-compaction nukes context at ~167K tokens | Step 0 + Phased Execution |
| Band-aid fixes instead of real solutions | System prompt mandates minimal intervention | Senior Dev Override |
| Context decay on large refactors | Single agent = single 167K context window | Sub-Agent Swarming |
| Edits reference code it never saw | File reads capped at 2,000 lines | File Read Budget |
| Grep finds 3 results, there are 47 | Tool results truncated to 2,000-byte preview | Tool Result Blindness |
| Rename misses dynamic imports | Grep is text matching, not an AST | No Semantic Search |

## Works With

- **Claude Code** - reads CLAUDE.md natively
- **Cursor** - paste into `.cursorrules`
- **Other agents** - paste into whatever rules/system prompt file your tool uses

## Context

Built by [@samymetref](https://www.linkedin.com/in/samy-metref-77744133b/).

## License

MIT.
