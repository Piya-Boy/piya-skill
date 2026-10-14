# Technical terms: keep in English or translate

Use for Developer / Documentation audiences. For General/Business, use the "Plain-language alternative" column.

## Always keep in English (Developer / Technical)

### Core Software & Architecture
Architecture, Backend, Frontend, API, Repository/Repo, Endpoint, Middleware, Runtime, Framework, Component, Dependency, Deployment/Deploy, Pipeline, Refactor, Commit, Merge, Build, Cache, Queue, Branch, Pull Request/PR, Bug, Config, Token, Session, Database/DB, Schema, Query, Migration, Container, Cluster, Log, Test, Lint, Debug, Rollback, Hotfix, Release, Package, Module, Library, SDK, CLI, Webhook, Payload, Thread, Async, Load Balancer, Rate Limit, Ingress, Pod, Node, Microservices, Event-driven, Message Broker, Worker, Cron Job.

### Modern AI / LLM / Machine Learning
Prompt, Prompt Engineering, Context Window, Token, LLM, Fine-tuning, RAG (Retrieval-Augmented Generation), Embedding, Vector Database/Vector DB, Hallucination, Inference, Agent, Guardrails, Temperature, Benchmark, Model, Multimodal, Latency, Throughput.

### Cloud, DevOps & Security
Kubernetes/K8s, Serverless, Lambda, Ingress, CI/CD, IaC, Observability, Telemetry, Trace, Metrics, Secret, IAM, OAuth, SSO, Gateway, Canary, Blue-Green, Health Check, Zero-downtime, Disaster Recovery.

## Plain-language alternatives (general readers)

| Term | Plain Thai | First mention gloss example |
|---|---|---|
| Request/Response | คำขอ / คำตอบ | คำขอ (Request) |
| Server | เซิร์ฟเวอร์ | เซิร์ฟเวอร์ |
| Endpoint | ปลายทางรับข้อมูล / ช่องทางเชื่อมต่อ | จุดเชื่อมต่อ (Endpoint) |
| Backend | ระบบหลังบ้าน | ระบบหลังบ้าน (Backend) |
| Frontend | หน้าจอที่ผู้ใช้เห็น / ระบบหน้าบ้าน | ระบบหน้าบ้าน |
| Deploy | นำขึ้นใช้งานจริง / ปล่อยระบบ | ปล่อยระบบขึ้นใช้งานจริง (Deploy) |
| Bug | ข้อผิดพลาด / จุดที่ทำงานผิด | ข้อผิดพลาดในระบบ (Bug) |
| Cache | ที่พักข้อมูลชั่วคราวเพื่อให้เร็วขึ้น | ที่พักข้อมูลชั่วคราว (Cache) |
| Dependency | ส่วนประกอบภายนอกที่ระบบต้องใช้ | ส่วนประกอบภายนอกที่ต้องพึ่งพา |
| Refactor | จัดโครงสร้างโค้ดใหม่โดยไม่เปลี่ยนการทำงาน | ปรับโครงสร้างโค้ดภายใน |
| Architecture | โครงสร้างโดยรวมของระบบ | โครงสร้างของระบบ (Architecture) |
| Database | ฐานข้อมูล | ฐานข้อมูล (Database) |
| Token / Session | ข้อมูลยืนยันตัวตน / รอบการเข้าใช้งาน | ข้อมูลเข้าใช้งานระบบ |
| Prompt | คำสั่งหรือข้อความป้อนให้ AI | คำสั่งสำหรับ AI (Prompt) |
| RAG | การดึงข้อมูลองค์กรมาช่วยตอบ | ระบบค้นหาข้อมูลมาประกอบการตอบ (RAG) |
| Vector DB | ฐานข้อมูลค้นหาตามความหมาย | ฐานข้อมูลเชิงความหมาย |
| Fine-tuning | การฝึกสอนโมเดลเพิ่มเติมด้วยข้อมูลเฉพาะ | การเทรนโมเดลเพิ่มเติมเฉพาะด้าน |
| Observability / Telemetry | การติดตามและตรวจวัดสุขภาพระบบ | ระบบติดตามการทำงานของเซิร์ฟเวอร์ |

First use in a general-audience document: Lead with the plain Thai meaning, followed by the English term in brackets or an inline gloss ("โครงสร้างแบบแยกส่วน (Microservices)", "Cache หรือที่พักข้อมูลชั่วคราว..."), then use one form consistently throughout the document.

## Never paraphrase (precise engineering meaning)

Dependency Injection (DI), Idempotent, Race Condition, Deadlock, Eventual Consistency, Monorepo, Immutable, Polymorphism, Closure, Callback, Hook, Serverless, Zero-downtime, CI/CD, RAG, Ingress, Vector Embedding.

If an explanation is needed for non-engineers, keep the original term first and attach a plain explanation directly after it. Never replace the term with a vague paraphrase that strips away technical specificity.

## Borderline: decide by context

- **Software / Application**: devs say "แอป" or "Software"; formal text uses "แอปพลิเคชัน" or "ซอฟต์แวร์"
- **Server**: dev "Server"; general "เซิร์ฟเวอร์"
- **Authentication**: dev "Authentication/Auth"; general "การยืนยันตัวตน"
- **Performance**: dev "Performance"; general "ประสิทธิภาพ / ความเร็ว"
- **Error**: either "Error" or "ข้อผิดพลาด", by tone
- **Feature**: dev "Feature"; general "ฟีเจอร์ / ความสามารถใหม่"
- **Release / Launch**: dev "Release / ปล่อย"; general "เปิดตัว / ปล่อยอัปเดต"
- Loanwords Thai speakers already use keep their usual spelling (อีเมล, แอป, เว็บไซต์, ออนไลน์, ดิจิทัล). Do not invent new coinages or awkward royal institute terms that no one uses in daily work (e.g. avoid "แถบระวาง" for Cache, avoid "จุดบริการเครือข่าย" for Endpoint).

## Consistency

Use one form per term per document. Follow the source's convention if it is already consistent (Endpoint vs endpoint, capitalization). Do not force capitalization or alternate between Thai and English for the same concept within one text.
