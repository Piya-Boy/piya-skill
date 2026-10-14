---
name: thai-natural-writing
description: |
  Review, humanize, rewrite, or draft Thai text so it reads like a real person wrote it, not a chatbot or translation tool.
  Eliminates structural AI writing patterns (staging, dramatic one-liners, forced triads, excessive bolding, hype words, padded verbs like ดำเนินการ/ทำการ, passive voice, fake contrast) while adapting vocabulary to the target audience (Developer, Business, General, Documentation).
  Preserves technical terms developers say in English (Architecture, Backend, API, Deploy, Refactor, Cache, Queue, Database, etc.) and keeps all code, links, dates, numbers, and facts unchanged.
  Use whenever the user asks to polish, rewrite, proofread, or de-AI Thai text, draft Thai commit messages, PR descriptions, READMEs, API docs, incident summaries, executive reports, customer update emails, or landing copy.
  Triggers on phrases like "ภาษาไทยดูเป็น AI", "แก้สำนวน", "เกลาภาษา", "ตรวจภาษาไทย", "เขียนให้เหมือนคนเขียน", "ปรับให้เป็นธรรมชาติ", "เขียน commit message ภาษาไทย", "ปรับอีเมล", "แก้คำซ้ำในเอกสาร API", "ภาษาแปลๆ", "humanize Thai", or "make this Thai sound natural".
license: MIT
metadata:
  version: "2.0.0"
---

# Thai Natural Writing v2 (Humanizer-Powered)

Review, humanize, and rewrite Thai text so it reads like a knowledgeable human wrote it for that specific reader, not like an AI trying to write Thai. Combines deep de-AI structural editing with audience-specific technical vocabulary.

## Why AI Thai sounds robotic

A language model by default chooses words and structures that fit the widest range of contexts, resulting in generic, overly formal, and formulaic Thai. A human writes specifically, unevenly, and directly to their intended audience.

AI writing in Thai suffers from six structural flaws:
1. **Staging instead of stating:** Adding fake contrasts ("ไม่ใช่แค่... แต่ยัง..."), dramatic one-line closers ("และนั่นคือจุดเปลี่ยน"), and hollow aphorisms ("หัวใจสำคัญคือ...") instead of stating facts.
2. **Rhythm by rule:** Forcing ideas into triads of three ("รวดเร็ว ปลอดภัย และมีประสิทธิภาพ"), chaining em-dashes (`—`), and repeating sentence openings.
3. **Inflation & borrowed authority:** Using buzzwords ("ยกระดับ", "ขับเคลื่อน", "ตอกย้ำ", "ตอบโจทย์", "ครอบคลุม", "อย่างแท้จริง"), padded verbs ("ดำเนินการ", "ทำการ", "ในส่วนของ"), and passive voice ("ถูก... โดย...").
4. **Formatting by rule:** Decorating every bullet with bold labels and colons, or littering headings with emojis (🚀, 💡, 📌).
5. **Leftovers from chat & draft:** Chatbot residue ("แน่นอนครับ!", "หวังว่าจะเป็นประโยชน์"), knowledge-limit disclaimers, or reciting the document's own structure.
6. **Wrong reader:** Re-explaining the problem background to someone who already knows it (especially in Slack replies, PRs, and commit messages).

## Workflow

1. **Identify the audience:**
   - **Developer / Engineer:** Code blocks, CLI, file paths, git terms, stack traces. Keep terms in English (Architecture, Backend, API, Deploy, etc.).
   - **Documentation:** Technically exact, consistent terminology across all pages (never alternate between "Endpoint" and "จุดเชื่อมต่อ").
   - **Business / Executive:** Focus on outcomes, figures, timelines, and impact. Explain technical terms inline or use plain equivalents.
   - **General / Customer:** Warm, natural, jargon-free Thai. Use plain concepts ("ส่งคำขอ" instead of "ส่ง Request ไปยัง Endpoint").
2. **Identify the context and document type:**
   - Commit message, PR description, README, incident report, customer notification email, blog post.
3. **Check technical terms:** Consult `references/technical-terms.md`. Developer text keeps terms in English; general text uses plain Thai or a gentle first-mention gloss.
4. **Detect and eliminate AI patterns:** Apply the 21+ patterns in `references/ai-patterns.md`. Never delete mechanically; preserve real semantic meaning.
5. **Rewrite directly:** Cut preamble and padding. State the point in natural Thai.
6. **Verify hard preservation constraints:**
   - Facts, numbers, dates, monetary amounts, and versions must remain identical.
   - Code, inline code, URLs, CLI commands, markdown tables, and links must remain untouched.
7. **Deliver clean output:** Deliver the finished text in a copyable block without chatbot conversational filler.

---

## Audience modes

| Audience | Vocabulary & Approach | Example |
|---|---|---|
| **Developer** | Keep standard industry English terms untouched. Direct, concise engineer voice. | "ฝั่ง Backend เราปรับ Architecture และ Refactor โมดูล Auth ทำให้ประสิทธิภาพดีขึ้น" |
| **Documentation** | Technically precise, perfectly consistent terms throughout. One term per concept. | "ติดตั้ง Dependency ด้วย `pnpm install` และกำหนดค่าตัวแปรใน `.env`" |
| **Business / Executive** | Professional, outcome-focused, numbers preserved, jargon translated or glossed. | "ทีมย้ายระบบชำระเงินไปใช้โครงสร้างแบบแยกส่วน (Microservices) ช่วยรองรับได้ 5,000 ธุรกรรมต่อวินาที" |
| **General / Customer** | Warm, friendly, plain Thai. No bare jargon. Clear action items for the customer. | "เราปรับปรุงระบบหลังบ้านเพื่อให้ใช้งานแอปได้เร็วขึ้น ท่านไม่ต้องดำเนินการใดๆ เพิ่มเติม" |

### Using technical terms with general readers
- Lead with plain Thai first.
- If keeping an English term helps the reader, gloss it once on first use: "โครงสร้างแบบแยกส่วน (Microservices)", "ที่พักข้อมูลชั่วคราว (Cache)".
- Never use bare jargon without explanation (e.g. avoid "พบปัญหาในส่วนของ Dependency ของ Third-party").
- Never invent facts or consequences in a gloss that were not in the original text.

---

## Key AI patterns to remove in Thai

Full details in `references/ai-patterns.md`. Key highlights:

### 1. Padded verbs (กริยาฟุ่มเฟือย)
- ❌ "ดำเนินการ Implement ระบบ" → ✅ "Implement ระบบ"
- ❌ "ทำการแก้ไข Bug" → ✅ "แก้ Bug"
- ❌ "มีความสามารถในการประมวลผล" → ✅ "ประมวลผลได้"
- ❌ "ในส่วนของ Backend" → ✅ "ฝั่ง Backend" หรือ "ส่วน Backend"
- ❌ "ระบบดังกล่าว" → ✅ "ระบบนี้"

### 2. Essay openers & staged lead-ins (ลีลาเกริ่นนำ)
- ❌ "ในยุคที่เทคโนโลยีก้าวหน้า ปฏิเสธไม่ได้ว่า..." → ✅ ตัดทิ้ง เข้าประเด็นทันที
- ❌ "สิ่งที่น่าสนใจคือ..." / "มาเจาะลึกกันเลย" → ✅ พูดข้อเท็จจริงตรงๆ
- ❌ "ทั้งนี้" / "อย่างไรก็ตาม" ที่ใส่มาทุกย่อหน้า → ✅ ตัดออก หรือใช้คำเชื่อมที่กระชับ ("แต่", "โดย")

### 3. Hype words & meaningless buzzwords
- ❌ "ยกระดับ", "ขับเคลื่อน", "ตอกย้ำ", "ทรงพลัง", "อย่างแท้จริง", "ตอบโจทย์ทุกมิติ", "ไร้รอยต่อ"
- ✅ แทนที่ด้วยข้อเท็จจริง เช่น "เร็วขึ้น 30%", "ทำงานร่วมกันได้ทันที", "ตรงกับความต้องการของลูกค้า" (ห้ามแต่งตัวเลขขึ้นมาเอง)

### 4. Passive voice & English syntax
- ❌ "ฟังก์ชันนี้ถูกเขียนขึ้นโดยทีมเรา" → ✅ "ทีมเราพัฒนาฟังก์ชันนี้"
- ❌ "โค้ดได้รับการ Refactor" → ✅ "เรา Refactor โค้ด"

### 5. Em-dash overload (ขีดกลางยาว —)
- ❌ "ระบบใหม่ — ซึ่งเพิ่งเปิดตัว — ช่วยลดเวลาโหลด"
- ✅ "ระบบใหม่ที่เพิ่งเปิดตัวช่วยลดเวลาโหลด"

---

## Hard preservation constraints

The rewritten text will be copied directly into codebases, pull requests, emails, or production documents. Altering these will break functionality:
1. **Zero invented facts & zero dropped facts:** Never add claims, reasons, or metrics not in the source. Never drop numbers, dates, deadlines, or warnings.
2. **Preserve code & technical entities exactly:** Code blocks, inline backticks (`` `Next.js` ``), CLI commands, file paths, URLs, environment variables, and config keys must not be changed by even a single character.
3. **Preserve markdown structure:** Headings, tables, lists, and link targets must stay intact. Only rewrite the human prose inside headings and table cells (e.g., `## ภาพรวมสถาปัตยกรรม` → `## ภาพรวม Architecture` สำหรับ developer).
4. **Commit messages & PRs:** Keep Conventional Commits tags (`feat:`, `fix:`, `refactor:`, `chore:`) and existing bullet structure.

---

## Output conventions

- **Pasted text:** Return the final deliverable inside a fenced code block or blockquote, completely clean and ready to copy.
- **No chatbot residue:** Never add openers like "นี่คือข้อความที่ปรับปรุงแล้วครับ" or closers like "หวังว่าข้อมูลนี้จะเป็นประโยชน์ครับ หากมีอะไรสอบถามเพิ่มเติมได้เลยครับ" inside the deliverable.
- **Short notes (outside the block only):** Add a note outside the block only if an audience had to be assumed or if a critical ambiguity was resolved. Keep it under 2 lines.
- **File mode:** When targeting a file in a workspace, edit the file in place and summarize the changes concisely.

---

## Examples

### Example 1: Developer PR Description
**Input:**
> feat: เพิ่มระบบ Rate Limiting
> 
> ## สรุป
> ในการนี้ ได้ทำการเพิ่มความสามารถในการจำกัดจำนวน Request โดยดำเนินการ Implement Middleware ใหม่ที่ `src/middleware/rateLimit.ts` ซึ่งใช้ Redis เป็น Queue สำหรับเก็บข้อมูลดังกล่าว
> - ทำการแก้ไข Bug ที่ทำให้ Cache ไม่ถูก Invalidate
> - ดำเนินการอัปเดต Dependency `ioredis` เป็นเวอร์ชัน 5.3.2
> 
> ทั้งนี้ สามารถทดสอบได้ด้วยคำสั่ง `npm test -- rateLimit`

**Output:**
```markdown
feat: เพิ่มระบบ Rate Limiting

## สรุป
เพิ่มระบบจำกัดจำนวน Request โดยสร้าง Middleware ใหม่ที่ `src/middleware/rateLimit.ts` และใช้ Redis เป็น Queue สำหรับเก็บข้อมูล
- แก้ Bug ที่ทำให้ Cache ไม่ถูก Invalidate
- อัปเดต Dependency `ioredis` เป็นเวอร์ชัน 5.3.2

ทดสอบได้ด้วยคำสั่ง `npm test -- rateLimit`
```

### Example 2: General Customer Announcement Email
**Input:**
> ในยุคดิจิทัล เราได้ทำการปรับปรุงสถาปัตยกรรมของแอปพลิเคชัน โดยดำเนินการย้ายข้อมูลไปยัง Database ใหม่ เมื่อผู้ใช้ส่ง Request ไปยัง Endpoint ระบบจะทำการดึงข้อมูลจาก Cache ก่อน ซึ่งช่วยยกระดับประสบการณ์ของผู้ใช้อย่างแท้จริง ทั้งนี้ ท่านไม่จำเป็นต้องดำเนินการใด ๆ

**Output:**
```text
เราได้ปรับปรุงระบบการทำงานของแอปพลิเคชันและย้ายข้อมูลไปยังฐานข้อมูลใหม่ เมื่อท่านใช้งาน ระบบจะดึงข้อมูลที่เตรียมไว้ล่วงหน้าเพื่อให้เปิดหน้าจอได้เร็วขึ้น ท่านไม่ต้องตั้งค่าหรือดำเนินการใดๆ เพิ่มเติม
```

### Example 3: Executive Summary
**Input:**
> สรุปผลโครงการสำหรับผู้บริหาร: ในไตรมาสที่ผ่านมา ทีมวิศวกรรมได้ดำเนินการ Migrate ระบบชำระเงินไปยัง Microservices Architecture ซึ่งช่วยยกระดับความสามารถในการรองรับผู้ใช้อย่างทรงพลัง ปัจจุบันระบบสามารถรองรับ 5,000 ธุรกรรมต่อวินาที เพิ่มขึ้นจากเดิม 2,000 ธุรกรรมต่อวินาที และมีอัตราการล่มลดลงจาก 1.2% เหลือ 0.3% อย่างไรก็ตาม ยังมีความเสี่ยงในส่วนของ Dependency กับผู้ให้บริการภายนอก 2 ราย ซึ่งทีมจะดำเนินการแก้ไขภายในไตรมาสหน้า

**Output:**
```text
สรุปผลโครงการสำหรับผู้บริหาร: ไตรมาสที่ผ่านมา ทีมวิศวกรรมย้ายระบบชำระเงินไปใช้โครงสร้างแบบแยกส่วน (Microservices) ทำให้ระบบรองรับการใช้งานได้มากขึ้น ปัจจุบันรองรับได้ 5,000 ธุรกรรมต่อวินาที จากเดิม 2,000 ธุรกรรมต่อวินาที และอัตราระบบขัดข้องลดลงจาก 1.2% เหลือ 0.3% แต่ยังมีความเสี่ยงจากการพึ่งพาผู้ให้บริการภายนอก 2 ราย ซึ่งทีมมีกำหนดแก้ไขในไตรมาสหน้า
```
