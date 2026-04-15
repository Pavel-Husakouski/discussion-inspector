# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/).

## [0.6.0] — 2026-04-15

### Added
- Summarizer agents (`summarizer`, `summarizer-ru`) — write a brief topic/direction/character/idea summary to `summary.md`
- Auditor violation types: **Labeling** and **Overgeneralization** (both EN and RU agents)

### Changed
- Parser output switched from grouped-by-speaker to chronological message format with `[N] Name — timestamp` entries, examples, and strict constraints
- Synthesizer now runs 4 parallel analysis agents (added summarizer) instead of 3
- Synthesizer final output renamed from `summary.md` to `report.md` (summary is now produced by the summarizer agent)
- Validator `PIPELINE_STOP` message says "calling agent" instead of "synthesizer"

## [0.5.0] — 2026-04-14

### Changed
- Expanded permissions: added `Agent`, `Bash(mkdir:output/**)`, `Bash(claude:*)` to allow agent invocation and directory creation
- Fixed agent path in changelog (`.github/agents/` → `.claude/agents/`)
- Updated README version badge to `v0.4.0`

## [0.4.0] — 2026-04-14

### Added
- Reviewer agents for English and Russian (`.claude/agents/Reviewer-en.agent.md`, `Reviewer-ru.agent.md`)

### Changed
- All agents now explicitly document input/output parameters for consistency
- Non-quote content always written in English; participant quotes preserved in original language

### Removed
- Language detection from parser — `## Language` section and downstream language inheritance dropped

## [0.3.0] — 2026-04-09

### Added
- Russian language agent pipeline (`synthesizer-ru`, `parser-ru`, `position-analyst-ru`, `tactics-analyst-ru`, `auditor-ru`, `audit-splitter-ru`, `validator-ru`)
- Each synthesizer is now a standalone entry point — no dispatcher needed

### Changed
- Both synthesizers now accept a single file path instead of scanning `input/`
- Russian agents always output in Russian (no language auto-detection)

### Removed
- Dispatcher agent (replaced by direct synthesizer invocation)

## [0.2.0] — 2026-04-09

### Added
- Audit splitter agent — splits `audit.md` into per-participant files
- Validator agent — rejects non-text files before processing
- Language detection in parser — downstream agents write in the discussion's language

## [0.1.0] — 2026-04-09

### Added
- Initial pipeline: synthesizer → parser → position-analyst / tactics-analyst / auditor
- Structured output: `parsed.md`, `positions.md`, `tactics.md`, `audit.md`, `summary.md`

