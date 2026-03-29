# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

Multilingual English vocabulary tracker with spaced repetition (Anki-style). The user learns English with translations in Japanese (日本語) and Vietnamese (Tiếng Việt).

## Key File

- `vocab.md` — The single vocabulary list with spaced repetition metadata (last review date, interval, next review date).

## Spaced Repetition Rules

- Intervals: 1d → 3d → 7d → 14d → 30d → 60d
- Correct answer: advance to next interval
- Wrong/forgotten: reset interval to 1d
- Track per-word: Last Review, Interval, Next Review
- "Quiz me": pick the most overdue words first (earliest Next Review date)

## Word Entry Format

Each word has: number, word, IPA pronunciation, 日本語 translation, Tiếng Việt translation, context, tags, and review tracking columns.

## Tags

- Comma-separated, lowercase, hyphenated for multi-word (e.g., `dev-anti-pattern, idiom`)
- A word can have multiple tags
- When adding a word, infer or ask for appropriate tags

## Workflow

- When the user asks to **explain a word**: add it to `vocab.md` with translations, IPA, tags, and initial review state (interval=1d, next review=today).
- **"quiz me"**: select most overdue words across all tags.
- **"quiz me on [tag]"**: filter by tag, then pick most overdue.
- **Commit once per session** (not per quiz question) — batch all changes into a single commit at the end.
