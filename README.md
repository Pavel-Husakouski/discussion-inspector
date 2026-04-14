# Discussion Analysis Agent Team

**v0.5.0** · [Changelog](CHANGELOG.md)

Analyzes discussion transcripts using a team of AI agents. Produces participant positions, tactics assessment, and violation audit — in the discussion's own language.

## Prerequisites

- [Claude Code](https://claude.ai/code) installed (VS Code extension, JetBrains plugin, or `claude` CLI)
- Active Anthropic subscription

## Setup

1. Clone or unzip this project
2. Open the project folder in Claude Code

## Usage

1. Drop your discussion file into the `input/` folder — prefer `.txt` or `.md`; avoid `.pdf`, `.html`, or `.rtf`
2. In Claude Code, run one of:
   ```
   /agents synthesizer input/<your-file>
   /agents synthesizer-ru input/<your-file>
   ```
   Use `synthesizer` for auto-detected language output, `synthesizer-ru` for Russian output.
3. Wait for the agents to finish

## Results

Find the output in `output/<your-filename>/`:

| File | Contents |
|---|---|
| `summary.md` | Overview and key findings |
| `positions.md` | Each participant's stance and claims |
| `tactics.md` | Argumentation style and fallacies |
| `audit-<name>.md` | Violations per offending participant (only created if violations found) |

## Notes

- Each run processes a single file, writing results to its own output folder
- `synthesizer` writes output in the discussion's dominant language
- `synthesizer-ru` always writes output in Russian
