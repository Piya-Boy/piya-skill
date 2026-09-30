# Technical terms: keep in English or translate

Use for Developer / Documentation audiences. For General/Business, use the "Plain-language alternative" column.

## Always keep in English (Developer)

Architecture, Backend, Frontend, API, Repository/Repo, Endpoint, Middleware, Runtime, Framework, Component, Dependency, Deployment/Deploy, Pipeline, Refactor, Commit, Merge, Build, Cache, Queue, Branch, Pull Request/PR, Bug, Config, Token, Session, Database/DB, Schema, Query, Migration, Container, Cluster, Log, Test, Lint, Debug, Rollback, Hotfix, Release, Package, Module, Library, SDK, CLI, Webhook, Payload, Thread, Async, Load Balancer, Rate Limit

## Plain-language alternatives (general readers)

| Term | Plain Thai |
|---|---|
| Request/Response | คำขอ / คำตอบ |
| Server | เซิร์ฟเวอร์ |
| Endpoint | ปลายทางของ API / ที่อยู่ที่ระบบรับคำขอ |
| Backend | ระบบหลังบ้าน |
| Frontend | หน้าจอที่ผู้ใช้เห็น |
| Deploy | นำขึ้นใช้งานจริง / ปล่อยระบบ |
| Bug | ข้อผิดพลาด / จุดที่ทำงานผิด |
| Cache | ที่พักข้อมูลชั่วคราวเพื่อให้เร็วขึ้น |
| Dependency | ส่วนประกอบภายนอกที่ระบบต้องใช้ |
| Refactor | จัดโครงสร้างโค้ดใหม่โดยไม่เปลี่ยนการทำงาน |
| Architecture | โครงสร้างโดยรวมของระบบ |
| Database | ฐานข้อมูล |

First use in a general-audience document: "Cache หรือที่พักข้อมูลชั่วคราว ..." then keep using "Cache".

## Never paraphrase (precise meaning)

Dependency Injection (DI), Idempotent, Race Condition, Deadlock, Eventual Consistency, Monorepo, Immutable, Polymorphism, Closure, Callback, Hook, Serverless, Zero-downtime, CI/CD.

If an explanation is needed, put the original name first and explain after it.

## Borderline: decide by context

- **Software / Application**: devs say "แอป" or "Software"; formal text uses "แอปพลิเคชัน"
- **Server**: dev "Server"; general "เซิร์ฟเวอร์"
- **Authentication**: dev "Authentication/Auth"; general "การยืนยันตัวตน"
- **Performance**: dev "Performance"; general "ประสิทธิภาพ / ความเร็ว"
- **Error**: either "Error" or "ข้อผิดพลาด", by tone
- Loanwords Thai speakers already use keep their usual spelling (อีเมล, แอป, เว็บไซต์). Do not invent new coinages.

## Consistency

Use one form per term per document. Follow the source's convention if it is already consistent (Endpoint vs endpoint, capitalization). Do not force capitalization.
