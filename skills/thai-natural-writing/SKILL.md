---
name: thai-natural-writing
description: Review and rewrite Thai text (often AI-generated) so it reads like a real person wrote it, choosing wording for the audience (general readers, developers, business, documentation) and keeping technical terms that Thai practitioners already say in English (Architecture, Backend, API, Deploy, etc.) instead of translating them literally. Use whenever the user asks to polish, proofread, rewrite, or "humanize" Thai text, fix Thai that sounds like AI or machine translation, or write Thai README, docs, reports, articles, commit messages, PR descriptions, or AI-generated reports. Trigger on phrases like "ภาษาไทยดูเป็น AI", "ปรับให้เป็นธรรมชาติ", "แก้สำนวน", "เกลาภาษา", "ภาษาแปลๆ", "ตรวจภาษาไทย", "เขียนให้เหมือนคนเขียน", "make this Thai sound natural", even if the user does not name this skill.
---

# Thai Natural Writing

Make Thai read like a person wrote it, not like an AI trying to write Thai. Choose words by **audience and context**, not by dictionary translation.

## Why this skill exists

AI tends to write Thai as translated English: "ดำเนินการ Implement ระบบ", "ในส่วนของ Backend", "สถาปัตยกรรมของระบบ" (a dev team says "Architecture"). The result is stiff and wordy, and Thai practitioners spot it immediately. The opposite failure also happens: for a general reader, a sentence packed with English jargon is unreadable. The goal is the wording that this specific reader group actually uses.

## Workflow

1. **Identify the audience.** Use the user's instruction, document type, and the terminology already in the source. If it is unclear and no cues exist, use General mode (neutral, easy Thai) but still keep terms that should stay in English (see "Keep in English"). Ask the user only when the audience would change the result a lot.
2. **Identify the context.** Document type (README, commit, report, article), tone (formal or casual), length.
3. **Check technical terms.** Keep terms the field uses in English. See `references/technical-terms.md`.
4. **Check for AI-isms and literal-translation phrasing.** See `references/ai-patterns.md`. Judge by context; never delete mechanically.
5. **Rewrite**, changing only what needs changing.
6. **Re-check meaning** against the source using "Preserve the source" below.
7. **Deliver the final text.**

### Audience signals

| Signal in the request or source | Likely audience |
|---|---|
| Code blocks, CLI, file paths, stack traces, terms like Repo/PR/Deploy/Refactor | Developer |
| README, API reference, runbook, ADR, changelog | Documentation (Developer-leaning) |
| KPI, timeline, cost, risk, stakeholder, "รายงานผู้บริหาร" | Business |
| Blog/article/social post, no jargon in source, "คนทั่วไป", "ลูกค้า" | General |
| Commit message, PR description | Developer |

Mixed signals: pick the audience that reads the text, not the one who wrote it. If still unclear, General mode plus kept-in-English terms.

## Audience modes

| Audience | Approach |
|---|---|
| **General** | Natural, easy Thai. Avoid technical terms that are not needed. "ส่งคำขอไปยังเซิร์ฟเวอร์" instead of "ส่ง Request ไปยัง Endpoint". |
| **Developer / Engineer** | Use the terms the field really uses; do not translate everything. "Architecture ของระบบ", "แก้ Bug", "Deploy แอป". |
| **Business** | Professional and easy to follow. Explain technical terms only as needed. Focus on outcomes over mechanisms. |
| **Documentation** | Clear, consistent, technically exact. Use one term per concept for the whole document (do not alternate "Endpoint" and "จุดเชื่อมต่อ"). |

### Using a term with general readers
Add a short gloss the first time, then use the term freely: "Architecture หรือโครงสร้างโดยรวมของระบบ ... ต่อมา Architecture นี้ ..."

## Keep in English (Developer / Documentation)

Do not switch to Thai just because a dictionary translation exists: Architecture, Backend, Frontend, API, Repository/Repo, Endpoint, Middleware, Runtime, Framework, Component, Dependency, Deploy/Deployment, Pipeline, Refactor, Commit, Merge, Build, Cache, Queue. Full list and borderline cases are in `references/technical-terms.md`.

❌ "สถาปัตยกรรมของระบบ" → ✅ "Architecture ของระบบ"

**Do not simplify away precision.** Terms with a specific meaning (Dependency Injection, Idempotent, Race Condition, Eventual Consistency) must not be replaced by a descriptive phrase. Keep the name, e.g. "Dependency Injection (DI)", and add an explanation only if the audience needs it.

## Avoid AI-sounding Thai

Common patterns (details and examples in `references/ai-patterns.md`):
- Essay-style openers: "ในยุคที่...", "ปฏิเสธไม่ได้ว่า...", "สิ่งที่น่าสนใจคือ...", "เรียกได้ว่า..."
- Overused connectors: "อย่างไรก็ตาม", "ทั้งนี้", "โดยเฉพาะอย่างยิ่ง", "ไม่เพียงแต่... แต่ยัง..."
- Padded verbs: "ดำเนินการ", "ทำการ", "มีความสามารถในการ", "ในส่วนของ", "ดังกล่าว"
- Hype words: "ทรงพลัง", "ยกระดับ", "ขับเคลื่อน", "ตอกย้ำ", "อย่างแท้จริง"

Decision rule: these words are not wrong in themselves. If removing or simplifying one keeps the meaning and reads smoother, change it. If it does real work (e.g. "ดังกล่าว" pointing back to something several sentences earlier in a formal document), keep it.

### Literal-translation examples
- ❌ "ดำเนินการ Implement ระบบ" → ✅ "Implement ระบบ"
- ❌ "ดำเนินการ Deploy แอปพลิเคชัน" → ✅ "Deploy แอป"
- ❌ "ทำการตรวจสอบระบบ" → ✅ "ตรวจสอบระบบ"
- ❌ "ทำการแก้ไข Bug" → ✅ "แก้ Bug"
- ❌ "ในส่วนของ Backend" → ✅ "ฝั่ง Backend"

## Mixed Thai-English conventions

Consistent mechanics make mixed text look human. Follow the source's existing style first; when the source has none, use these:
- Put a space between Thai and English words: "แก้ Bug", "Deploy แอป", not "แก้Bug".
- Do not add Thai inflection to English terms (no "การ Deploy" when plain "Deploy" works; "การ" is only for genuinely noun-like use, e.g. "การ Deploy ครั้งนี้ล้มเหลว").
- Use Arabic numerals in technical and business text. Keep numbers, units, and versions exactly as written.
- Use ๆ for repeated words in casual text ("เร็วๆ" or "เร็ว ๆ" per the source's habit); avoid it in formal documents.
- Keep the source's punctuation style for quotes, brackets, and ellipses. Thai has no sentence-ending period convention: follow the source (many Thai texts use a space instead of ".").

## Writing new Thai text (not editing)

When asked to write Thai from an English source, notes, a diff, or a code change:
1. Identify the audience first, as in the workflow.
2. Write directly in the natural Thai you would use for that audience; do not draft a literal translation and then fix it.
3. Keep only facts present in the source. Do not pad with an intro, a summary, or hype.
4. Run the same checks (terms, AI-isms, preserved items) on your own draft before returning it.

## Register (formality)

Match the source's register: formal (รายงาน, เอกสารทางการ), neutral (README, docs, articles), casual (blog, chat, PR comments). Do not raise or lower it unless asked. Keep the source's pronouns and polite particles; do not add ค่ะ/ครับ that were not there.

## Preserve the source (hard constraints)

The user will paste this text elsewhere, so altering these breaks things:
- Do not add information that is not in the source. Do not drop important information. Do not change technical meaning.
- Do not edit or translate: code, code blocks, inline code, library/framework/API/function/variable names, product names, CLI commands, URLs, file names and paths, numbers and versions.
- Keep Markdown structure (heading levels, list and table layout, link targets) unless the user asks to restructure. The wording inside headings, list items, table cells, and link text is ordinary text: check it like the body. "## ภาพรวมสถาปัตยกรรม" becomes "## ภาพรวม Architecture" for developers.
- Commit messages: keep the Conventional Commits prefix (`feat:`, `fix:`) and existing format.

## Output

Default: return **only the final text**, ready to copy. If the user asks, or if an ambiguous audience forced an important call, append a short note: the assumed audience plus 2-5 key changes. If the source is a file in a project, edit it in place and report briefly.

If the text is already good, change as little as possible. Do not rewrite just to look busy.

## Full examples

**Input (Developer):**
> ในส่วนของ Backend เราได้ทำการปรับปรุงสถาปัตยกรรมของระบบ โดยดำเนินการ Refactor โมดูลการยืนยันตัวตน ซึ่งช่วยยกระดับประสิทธิภาพอย่างเห็นได้ชัด

**Output:**
> ฝั่ง Backend เราปรับ Architecture ของระบบ และ Refactor โมดูล Authentication ทำให้ประสิทธิภาพดีขึ้นชัดเจน

Note what did not change: "ประสิทธิภาพ" stays (not narrowed to "เร็ว"), and no new claim was added.

**Input (General):**
> ระบบจะส่ง Request ไปยัง Endpoint เพื่อดึงข้อมูล

**Output:**
> ระบบจะส่งคำขอไปยังเซิร์ฟเวอร์เพื่อดึงข้อมูล
