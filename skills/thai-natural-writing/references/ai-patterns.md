# AI-style Thai patterns: check, then decide by context

Rule: do not delete mechanically. If removing or changing a phrase keeps the meaning and reads smoother, change it. If it does real work in the sentence, keep it.

## Openers and lead-ins

| Pattern | Problem | Fix |
|---|---|---|
| ในยุคที่... | Broad framing, no information | Cut; go straight to the point |
| ปฏิเสธไม่ได้ว่า... | Filler | Say it directly |
| สิ่งที่น่าสนใจคือ... | Teases without content | Cut and state the thing itself |
| เรียกได้ว่า... | Filler / exaggeration | Cut, or use "คือ" |

## Connectors

- **อย่างไรก็ตาม / ทั้งนี้**: use only for real contrast or conditions. If every paragraph starts with one, cut it, use "แต่", or order the sentences so they connect on their own.
- **โดยเฉพาะอย่างยิ่ง** → "โดยเฉพาะ" or cut
- **ไม่เพียงแต่... แต่ยัง...** → split into two sentences, or "ทั้ง X และ Y"
  - ❌ "ไม่เพียงแต่เร็ว แต่ยังปลอดภัย" → ✅ "เร็วและปลอดภัย"

## Padded verbs (nominalization)

| ❌ | ✅ |
|---|---|
| ดำเนินการ + verb | the verb directly: "ดำเนินการตรวจสอบ" → "ตรวจสอบ" |
| ทำการ + verb | "ทำการแก้ไข" → "แก้" |
| มีความสามารถในการ + verb | "สามารถ ..." or the verb: "มีความสามารถในการประมวลผล" → "ประมวลผลได้" |
| ในส่วนของ X | "ฝั่ง X" / "ส่วน X" / cut |
| X ดังกล่าว | "X นี้" / repeat X / cut |
| มีการ + verb (passive) | "มีการอัปเดต" → "อัปเดต" (name the actor if it matters) |
| เป็นการ + verb | drop "เป็นการ" |
| stacked ความ + verb | use the verb or adjective directly |

`ดำเนินการ` is fine for multi-step formal procedures (e.g. "ดำเนินการตามขั้นตอนทางกฎหมาย"). With technical verbs, cut it almost every time.

## Hype words

ทรงพลัง, ยกระดับ, ขับเคลื่อน, ตอกย้ำ, อย่างแท้จริง, ไร้ขีดจำกัด, ปฏิวัติ, ครบครัน, ล้ำสมัย, ทลายข้อจำกัด

- Replace with facts: "ยกระดับประสิทธิภาพ" → "เร็วขึ้น 30%" (only if the source has the number) or "ประสิทธิภาพดีขึ้น" (if not; **never invent numbers**, and do not narrow "ประสิทธิภาพ" to "เร็ว")
- In marketing copy where the user wants a promotional tone, keep some but lower the frequency

## Text-level structure

- Long multi-clause sentences chained together → split
- Lists of exactly three every time (rule of three) when the content has fewer or more → follow the real content
- Closing summary that repeats what was just said ("โดยสรุปแล้ว...") → cut unless needed
- Bold bullets on every line of a short message → prose for short text
- Mixed pronouns (คุณ/เรา/ผม) → pick one, follow the source
- Polite particles (ค่ะ/ครับ): follow the source; do not add or remove unless told

## AI reports / commits / PRs

- Commit: short, direct verb. ❌ "ดำเนินการแก้ไขปัญหา Login" → ✅ "fix: แก้ Login ที่ Token หมดอายุแล้วไม่ Redirect" (keep the source's prefix)
- PR description: say what and why directly; no preamble
- AI reports: cut self-congratulation ("ประสบความสำเร็จอย่างสมบูรณ์"); state facts and real status

## Before / after

**Before:** ในยุคที่เทคโนโลยีก้าวหน้า ปฏิเสธไม่ได้ว่า API ที่ทรงพลังช่วยยกระดับการทำงานของทีมอย่างแท้จริง
**After (Dev):** API ที่มีประสิทธิภาพช่วยให้ทีมทำงานได้ดีขึ้น

(Opener cut, hype words swapped for plain equivalents, no new claim such as "เร็วขึ้น" or "ออกแบบดี" added.)

**Before:** ทั้งนี้ ในส่วนของ Deployment ได้ทำการตั้งค่า Pipeline ดังกล่าวเรียบร้อยแล้ว
**After:** ตั้งค่า Pipeline สำหรับ Deploy เรียบร้อยแล้ว
