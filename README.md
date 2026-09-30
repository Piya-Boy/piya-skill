# Agent Skills

A collection of skills for Claude Code, Codex, Cursor, and other coding agents. Each skill is a self-contained folder under [`skills/`](skills/).

## Skills

| Skill | What it does |
|---|---|
| [`thai-natural-writing`](skills/thai-natural-writing/) | Rewrites AI-sounding Thai into natural Thai matched to the audience, keeping technical terms developers already say in English (Architecture, Backend, API, Deploy). |

More will be added over time.

## Install

Paste this into Claude Code, Codex, Cursor, or your favorite coding agent (replace the skill name):

```text
Install the /thai-natural-writing skill globally from https://github.com/Piya-Boy/piya-skill
```

Or use `npx`:

```sh
npx skills add Piya-Boy/piya-skill --skill thai-natural-writing --global --yes
```

Manual install for Claude Code: copy the skill folder (for example `skills/thai-natural-writing/`) into `~/.claude/skills/` (all projects) or `<project>/.claude/skills/` (one project).

## Use

```text
/thai-natural-writing (your Thai text)
```

Each skill documents its own usage in its `SKILL.md` and README section below.

---

## thai-natural-writing

Make Thai read like a person wrote it, not like an AI trying to write Thai. Wording is chosen by audience, and technical terms that Thai practitioners already say in English stay in English.

### Problem

AI writes Thai as translated English:

- "ดำเนินการ Implement ระบบ", "ทำการแก้ไข Bug", "ในส่วนของ Backend"
- "สถาปัตยกรรมของระบบ" where a dev team says "Architecture"
- "ในยุคที่...", "ปฏิเสธไม่ได้ว่า...", "ยกระดับ", "ทรงพลัง"

Over-correcting is just as bad: a customer email full of Request and Endpoint is unreadable. The right wording depends on who reads it.

### Usage

Say who reads it for the best result:

```text
/thai-natural-writing for developers: (your Thai text)
/thai-natural-writing for customers, non-technical: (your Thai text)
```

With no audience given, the skill reads the cues in the text (code blocks, jargon, document type) and falls back to neutral Thai that still keeps terms like Architecture and API. It also writes new Thai (README, docs, commit messages, PR descriptions, reports, articles) directly instead of translating word by word.

### What it does

- **Audience modes:** General, Developer, Business, Documentation.
- **Keeps technical terms:** Architecture, Backend, Frontend, API, Repo, Endpoint, Middleware, Deploy, Refactor, Commit, Merge, Cache, Queue and more stay in English for developers. General readers get plain Thai with a short gloss on first use.
- **Cuts AI-sounding Thai:** essay openers, overused connectors, padded verbs (ดำเนินการ, ทำการ, ในส่วนของ), hype words. Judged by context, not deleted mechanically.
- **Preserves the source:** code, names, URLs, paths, CLI commands, numbers, and Markdown structure are untouched. No added facts, no dropped facts.

| Before | After (Developer) |
|---|---|
| ในส่วนของ Backend เราได้ทำการปรับปรุงสถาปัตยกรรมของระบบ โดยดำเนินการ Refactor โมดูลการยืนยันตัวตน ซึ่งช่วยยกระดับประสิทธิภาพอย่างเห็นได้ชัด | ฝั่ง Backend เราปรับ Architecture ของระบบ และ Refactor โมดูล Authentication ทำให้ประสิทธิภาพดีขึ้นชัดเจน |

### Status

Early draft. First benchmark on 3 cases: 93% assertion pass rate with the skill vs 67% without. Small sample; treat as a signal, not a result.

---

## Adding a new skill

1. Create `skills/<skill-name>/SKILL.md` with `name` and `description` frontmatter. `name` must match the folder name. Put long material in `skills/<skill-name>/references/`.
2. Optional: `skills/<skill-name>/agents/openai.yaml` for Codex display name and default prompt, and `skills/<skill-name>/evals/evals.json` for test prompts.
3. Add a row to the Skills table above and a section for it below.
4. Add the skill's name to `keywords` or `longDescription` in [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json) if it changes what the collection covers. The plugin points at `./skills/`, so new folders are picked up automatically.

## License

MIT
