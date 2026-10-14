# Agent Skills

A collection of skills for Claude Code, Codex, Cursor, and other coding agents. Each skill is a self-contained folder under [`skills/`](skills/).

## Skills

| Skill | Version | What it does |
|---|---|---|
| [`thai-natural-writing`](skills/thai-natural-writing/) | **2.0.0** | Humanizes AI-sounding Thai into natural Thai matched to the audience. Removes structural AI writing patterns (staging, dramatic one-liners, forced triads, hype words, padded verbs) while keeping technical terms developers already say in English (Architecture, Backend, API, Deploy, Cache, Queue). |

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

## Update

To update an existing installation to **v2.0.0**:

Paste this into Claude Code, Codex, or Cursor:

```text
Update the /thai-natural-writing skill from https://github.com/Piya-Boy/piya-skill
```

Or re-run `npx`:

```sh
npx skills add Piya-Boy/piya-skill --skill thai-natural-writing --global --yes
```

For manual installs, pull the latest repo or overwrite `SKILL.md`:

```sh
# PowerShell (Windows)
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Piya-Boy/piya-skill/main/skills/thai-natural-writing/SKILL.md" -OutFile "$HOME\.claude\skills\thai-natural-writing\SKILL.md"

# Bash (macOS/Linux)
curl -fsSL "https://raw.githubusercontent.com/Piya-Boy/piya-skill/main/skills/thai-natural-writing/SKILL.md" -o ~/.claude/skills/thai-natural-writing/SKILL.md
```

## Use

```text
/thai-natural-writing (your Thai text)
```

Each skill documents its own usage in its `SKILL.md` and README section below.

---

## thai-natural-writing v2 (Humanizer-Powered)

Make Thai read like a person wrote it, not like an AI trying to write Thai. Wording is chosen by audience, structural AI tells are systematically removed, and technical terms that Thai practitioners already say in English stay in English.

### What's new in v2: Humanizer Integration

Version 2 combines audience-aware technical Thai writing with the structural AI removal principles from Wikipedia's "Signs of AI writing" and the Humanizer methodology:

1. **Elimination of Staged Writing:**
   - Cuts fake contrasts: "ไม่ใช่แค่ X แต่ยังเป็น Y", "ไม่ใช่เรื่องของ... แต่มันคือ..."
   - Eliminates dramatic one-line closers: "และนั่นคือจุดเปลี่ยน", "จำคำนี้ไว้ให้ดี"
   - Replaces hollow aphorisms ("หัวใจสำคัญคือ...", "...กลายเป็นกับดัก") with direct, concrete claims.
   - Drops staged run-ups: "ในยุคที่เทคโนโลยีก้าวหน้า ปฏิเสธไม่ได้ว่า...", "มาเจาะลึกกันเลย"
2. **Natural Rhythm & Syntax:**
   - Fixes forced triads: Stops packaging every list or description into groups of three by default.
   - Eliminates awkward passive voice translations ("ถูก... โดย...") and replaces them with active Thai sentence structures.
   - Replaces mechanical em-dashes (`—`) with natural Thai phrasing.
3. **Padded Verb & Buzzword Cleanup:**
   - Cuts padded verbs: "ดำเนินการ", "ทำการ", "มีความสามารถในการ", "ในส่วนของ", "ดังกล่าว"
   - Cleans up hype words: "ยกระดับ", "ขับเคลื่อน", "ตอกย้ำ", "ทรงพลัง", "อย่างแท้จริง", "ตอบโจทย์", "ครอบคลุม", "ไร้รอยต่อ"
4. **Expanded Modern Tech & AI Vocabulary:**
   - Protects modern AI/LLM terms: Prompt, Context Window, RAG, Fine-tuning, Vector DB, Agent, Embedding, Token.
   - Protects modern Cloud & DevOps terms: Ingress, Pod, Cluster, Serverless, Observability, Telemetry, CI/CD.

### Problem

AI writes Thai as translated English:

- "ดำเนินการ Implement ระบบ", "ทำการแก้ไข Bug", "ในส่วนของ Backend"
- "สถาปัตยกรรมของระบบ" where a dev team says "Architecture"
- "ในยุคที่...", "ปฏิเสธไม่ได้ว่า...", "ยกระดับ", "ทรงพลัง", "ตอบโจทย์ทุกมิติ"
- "ไม่ใช่แค่ความเร็ว แต่คือความปลอดภัยอย่างแท้จริง และนั่นคือชัยชนะของทีม"

Over-correcting is just as bad: a customer email full of Request and Endpoint is unreadable. The right wording depends on who reads it.

### Usage

Say who reads it for the best result:

```text
/thai-natural-writing for developers: (your Thai text)
/thai-natural-writing for customers, non-technical: (your Thai text)
/thai-natural-writing for executives: (your Thai text)
```

With no audience given, the skill reads the cues in the text (code blocks, jargon, document type) and falls back to neutral Thai that still keeps terms like Architecture and API. It also writes new Thai (README, docs, commit messages, PR descriptions, reports, articles) directly instead of translating word by word.

### Audience modes

- **Developer / Engineer:** Keeps industry English terms intact: Architecture, Backend, Frontend, API, Repo, Endpoint, Middleware, Deploy, Refactor, Commit, Merge, Cache, Queue, Redis, etc.
- **Documentation:** Technically precise and consistently formatted. One term per concept across the entire guide.
- **Business / Executive:** Focus on outcomes, figures, impact, and timelines. Explain technical terms inline or use plain equivalents.
- **General / Customer:** Warm, natural, plain Thai. English terms are replaced with plain concepts or glossed on first use.

### Comparison

| Before (AI-Generated Thai) | After (Developer) |
|---|---|
| ในส่วนของ Backend เราได้ทำการปรับปรุงสถาปัตยกรรมของระบบ โดยดำเนินการ Refactor โมดูลการยืนยันตัวตน ซึ่งช่วยยกระดับประสิทธิภาพอย่างแท้จริง และนั่นคือชัยชนะของทีม | ฝั่ง Backend เราปรับ Architecture ของระบบ และ Refactor โมดูล Authentication ทำให้ประสิทธิภาพดีขึ้นชัดเจน |

| Before (AI-Generated Thai) | After (Customer / Non-technical) |
|---|---|
| ในยุคดิจิทัล เราได้ทำการปรับปรุงสถาปัตยกรรมของแอปพลิเคชัน โดยดำเนินการย้ายข้อมูลไปยัง Database ใหม่ เมื่อผู้ใช้ส่ง Request ไปยัง Endpoint ระบบจะทำการดึงข้อมูลจาก Cache ก่อน ซึ่งช่วยยกระดับประสบการณ์ของผู้ใช้อย่างแท้จริง ทั้งนี้ ท่านไม่จำเป็นต้องดำเนินการใด ๆ | เราปรับปรุงระบบของแอปและย้ายข้อมูลไปยังฐานข้อมูลใหม่แล้ว เมื่อท่านใช้งาน ระบบจะดึงข้อมูลที่เตรียมไว้ล่วงหน้าเพื่อให้เปิดหน้าจอได้เร็วขึ้น ท่านไม่ต้องตั้งค่าหรือดำเนินการใดๆ เพิ่มเติม |

### Status & Benchmarks

- **Round 1:** 93% assertion pass rate with the skill vs 67% baseline.
- **Round 2 (Harder cases):** 100% assertion pass rate with the skill vs 87% baseline.

---

## Adding a new skill

1. Create `skills/<skill-name>/SKILL.md` with `name` and `description` frontmatter. `name` must match the folder name. Put long material in `skills/<skill-name>/references/`.
2. Optional: `skills/<skill-name>/agents/openai.yaml` for Codex display name and default prompt, and `skills/<skill-name>/evals/evals.json` for test prompts.
3. Add a row to the Skills table above and a section for it below.
4. Add the skill's name to `keywords` or `longDescription` in [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json).

## License

MIT
