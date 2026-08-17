# 👋 Hola, soy Miguel Hernández

**AI Engineer | Full-Stack Developer** — Construyo sistemas de IA que funcionan en producción, no demos.

---

## 🎯 Lo Que Hago

| Área | Tecnologías Clave | Experiencia |
|------|-------------------|-------------|
| **RAG & Hybrid Search** | BM25, Sentence-Transformers, RRF, Cross-Encoder, pgvector, Evaluation (RAGAS-style) | 2+ años |
| **AI Agents** | LangGraph, LangChain, ReAct pattern, Multi-agent orchestration, Tool calling | 1.5+ años |
| **LLM Engineering** | OpenAI, Anthropic, Local models, Prompt engineering, Fine-tuning awareness | 2+ años |
| **Backend** | Python, FastAPI, Node.js, PostgreSQL, Redis, Celery, SQLite | 3+ años |
| **Frontend** | React, Next.js, TypeScript, Tailwind CSS | 2+ años |
| **DevOps/MLOps** | Docker, GitHub Actions, CI/CD, Cloudflare Workers, n8n | 2+ años |
| **Voice AI** | Whisper, pyttsx3, TTS/STT local pipelines | 1+ año |
| **Security** | Network scanning, JWT auditing, HTTP security headers, stdlib-only tools | 1+ año |

---

## 🚀 Proyectos Destacados

### 1. [hybrid-rag-evals](https://github.com/MaikolProx/hybrid-rag-evals) ⭐ **Proyecto estrella para AI Engineer**
> **Pipeline RAG híbrido production-ready con framework de evaluación reproducible**

**Qué hace:** Implementa retrieval híbrido (BM25 + embeddings densos + fusión RRF + reranking cross-encoder) **desde cero con numpy puro** + suite de evaluación que mide recall@k, MRR, NDCG@k, faithfulness.

**Resultados medibles en corpus de 21 docs / 14 queries:**
| Sistema | Recall@5 | MRR | NDCG@5 |
|---------|----------|-----|--------|
| BM25 (baseline) | 0.643 | 0.607 | 0.617 |
| Híbrido (BM25 + dense + RRF) | 0.821 | 0.677 | 0.702 |
| **Híbrido + rerank (cross-encoder)** | **0.964** | **0.812** | **0.845** |

**Stack:** Python, FastAPI, `all-MiniLM-L6-v2` (384d), `ms-marco-MiniLM-L-6-v2` (rerank), pytest (23 tests, 93% coverage)

**Por qué importa:** Sin dependencias de frameworks RAG — entiendo cada pieza y fallo. Evaluación automática detecta regresiones antes de deploy.

---

### 2. [medusa](https://github.com/MaikolProx/medusa) ⭐ **Sistema completo en uso diario**
> **Segundo cerebro autónomo: RAG local + 6 agentes multi-modelo + voz bidireccional + n8n**

**Qué hace:** Mi herramienta diaria real. Procesa 234+ documentos, indexa en SQLite con embeddings 100% locales (`all-MiniLM-L6-v2`), expone 17 herramientas MCP, orquesta flujos con n8n.

**Arquitectura:**
- **Ingesta:** `RAW/` → `WIKI/` (wikilinks `[[...]]`) → Chunking → Embeddings → SQLite
- **Retrieval:** Búsqueda semántica local CPU, sin API externa
- **Agentes:** 6 agentes con providers distintos (evita rate limits / single point of failure)
- **Voz:** Whisper (STT) + pyttsx3 (TTS) — 100% local, sin nube
- **MCP:** 17 herramientas expuestas al agente principal

**Stack:** Python 3.12, SQLite, sentence-transformers, Whisper, pyttsx3, n8n, opencode, MCP

**Nota:** Código compartible en repo; claves, base de conocimiento real y orquestación n8n completa en `.gitignore`.

---

### 3. [security-toolkit](https://github.com/MaikolProx/security-toolkit) ⭐ **Backend/Seguridad sólido**
> **Herramientas de auditoría red/web — solo stdlib Python, 16/16 tests pasando**

**Qué hace:** CLI `sec-tool` con 5 herramientas para labs autorizados (THM, HTB):

| Herramienta | Función |
|-------------|---------|
| `portscan` | TCP connect scan + service detection + banner grabbing |
| `subenum` | Enumeración subdominios DNS + wordlist |
| `httpaudit` | Auditoría cabeceras seguridad HTTP (HSTS, CSP, X-Frame, etc.) |
| `jwtdump` | Decodificación + inspección JWT (incluye detección `alg:none` / CVE-2015-9235) |
| `dirbust` | Fuerza bruta directorios con wordlist + códigos HTTP |

**Por qué stdlib solo:** Legible en una tarde, corre en cualquier máquina de lab sin `pip install`, cada pieza testeada.

**Tests:** `pytest -q` → 16/16 passing (port ranges, common ports, HTTP headers, JWT parsing + weak sig detection)

**Write-ups:** Plantilla en `writeups/` con dead-ends documentados (lo que más preguntan en entrevistas).

---

### 4. [tryhackme-roadmap](https://github.com/MaikolProx/tryhackme-roadmap)
> **Plan 90 días validado: THM + HTB + KC7/Kusto + Certificaciones → Prueba de trabajo verificable**

**Qué hace:** Roadmap estructurado para convertir práctica en portafolio técnico:

- **Fase 1 (Días 1-30):** Security+ (Messer + objetivos CompTIA) + 3 write-ups + perfil THM
- **Fase 2 (Días 31-60):** KC7 Cyber (threat hunting KQL) + HTB medium + MITRE ATT&CK mapping
- **Fase 3 (Días 61-90):** eJPT/OSCP + 5 write-ups consolidados + CV con métricas

**Diferenciador:** KC7 Cyber + detective.kusto.io = mentalidad threat hunting rara en CVs.

---

### 5. [medusa-auto-publisher](https://github.com/MaikolProx/medusa-auto-publisher)
> **Landing estática + páginas legales para publicación automatizada de contenido**

**Qué hace:** HTML estático (index, privacy, terms) + verificación TikTok. Parte de la automatización de contenido con n8n.

---

### 6. [MaikolProx](https://github.com/MaikolProx/MaikolProx) 
> **Configuración del perfil de GitHub (este README)**

---

## 📊 Métricas de Calidad

| Repo | Tests | Coverage | CI/CD | Type Hints | Docs |
|------|-------|----------|-------|------------|------|
| hybrid-rag-evals | 23 passing | 93.27% | ✅ GitHub Actions | ✅ | ✅ Completo |
| medusa | — | — | — | Parcial | ✅ Completo |
| security-toolkit | 16 passing | 100% core | ✅ GitHub Actions | ✅ | ✅ Completo |
| tryhackme-roadmap | N/A | N/A | — | N/A | ✅ Completo |

---

## 📫 Contacto

- **Email:** [paz243482@gmail.com](mailto:paz243482@gmail.com)
- **LinkedIn:** [miguel-hernandez-04129542a](https://www.linkedin.com/in/miguel-hernandez-04129542a/)
- **GitHub:** [github.com/MaikolProx](https://github.com/MaikolProx)

---

## 🏷️ Topics para Búsqueda

`ai-engineer` `rag` `langgraph` `fastapi` `python` `hybrid-search` `bm25` `sentence-transformers` `cross-encoder` `evaluation` `multi-agent` `voice-ai` `security` `stdlib-only`

---

*Construyendo sistemas que funcionan. Midiendo todo. Compartiendo lo que aprendo.*