# Juan Pablo Figueroa

Senior Data Engineer & Desarrollador IA · GCP Certified · Chile

Trabajo en el cruce entre **datos, IA y producto**. Diseño pipelines en GCP,
sistemas RAG con métricas en producción, y SaaS multi-tenant type-safe end-to-end.

- Email: jpablofigueroar@gmail.com
- LinkedIn: [in/juan-pablo-mac-fig](https://linkedin.com/in/juan-pablo-mac-fig)

## Case studies

Cada uno documenta un sistema real (con nombres/clientes genericos) contado como
lo pensé, decidí y medí. Sin código de cliente — el código de referencia vive en
los repos hermanos abajo.

1. [**RAG industrial con doble juez y circuit breaker**](./case-studies/01-rag-industrial.md) — sistema RAG on-premise para un cliente industrial europeo. 2,2% de alucinación medida, 100% correcciones del supervisor resueltas con 0 regresiones. CRAG con doble juez OpenAI + Claude, reranking Voyage con circuit breaker hacia Cohere, chunking estructural, contextual retrieval estilo Anthropic.

2. [**Agente de voz en tiempo real**](./case-studies/02-voice-agent-realtime.md) — call center IA con streaming bidireccional Twilio ↔ OpenAI Realtime sobre WebSockets. Manejo de back-pressure, reconexión, adapter Twilio Media Streams.

3. [**Migración SAP BW → BigQuery**](./case-studies/03-sap-to-bigquery.md) — 8 modelos críticos migrados con Dataform. Reglas de negocio SAP preservadas. Queries optimizadas: −25% tiempo · −50% costos.

4. [**SaaS multi-tenant type-safe end-to-end**](./case-studies/04-multi-tenant-saas.md) — CRM para empresas de servicios en España. Next.js + tRPC + Drizzle + PostgreSQL. WebAuthn/passkeys, rate limiting con Upstash, tests con Playwright + Vitest.

5. [**Adapter pattern para integracion fiscal**](./case-studies/05-adapter-pattern-sii.md) — API interna FastAPI para extracción del registro de compras/ventas del servicio tributario chileno. Adapter intercambiable entre proveedor comercial y conexión directa via variable de entorno, contrato downstream invariante.

## Codigo de referencia (repos hermanos)

Snippets sinteticos que ilustran los patrones sin código de cliente:

- [**gcp-etl-pipeline**](https://github.com/jpfiguer/gcp-etl-pipeline) — pipeline Beam + Dataflow + Pub/Sub + BigQuery + Dataform + Terraform. Batch y streaming, deduplicacion, particionado dinamico, validacion post-load.
- [**rag-crag-reference**](https://github.com/jpfiguer/rag-crag-reference) — RAG con circuit breaker de rerankers, doble juez OpenAI + Claude, chunking estructural, eval pipeline con Ragas.
- [**multi-tenant-saas-starter**](https://github.com/jpfiguer/multi-tenant-saas-starter) — starter Next.js + tRPC + Drizzle + PostgreSQL con aislamiento por tenant desde el dia 1.

## Stack

**Datos & GCP**: BigQuery · Apache Beam · Dataflow · Pub/Sub · Cloud Composer / Airflow · Dataform · DBT · Looker Studio · Cloud Functions
**IA / ML**: Sistemas RAG en produccion · OpenAI · Anthropic Claude · Mistral · Gemini · Voyage / Cohere reranking · Qdrant · OCR (Tesseract, Mistral, Gemini Vision) · faster-whisper
**Backend**: FastAPI · Express.js · tRPC · Next.js API Routes
**Frontend & Mobile**: React 19 · Next.js 14-16 · Vue 3 · React Native / Expo · Tailwind · shadcn/ui
**Bases de datos**: PostgreSQL (Supabase, Neon) · Redis · SQLite · Qdrant (vector) · SQLAlchemy 2.0 · Prisma · Drizzle
**Cloud & DevOps**: GCP · Vercel · AWS S3 · Docker · nginx · Terraform · CI/CD con GitHub Actions
**Observabilidad**: Sentry · Prometheus · OpenTelemetry · pytest · Vitest · Playwright

## Contexto profesional

- **2024 – Presente**: Senior Data & AI Engineer @ Stratech
- **2020 – 2024**: Data Engineer & Fullstack Developer @ Agtec (KPIs Sodimac)
- **2018 – 2020**: DBA Manager & BI Developer @ Dentsu / IProspect (Entel)

Certificado en **Google Cloud**. 8 años en pipelines de datos en produccion.

## Como leo esta pagina

- Si es un rol de **Data Engineer** → empezá por case study #3 y el repo `gcp-etl-pipeline`
- Si es un rol de **AI Engineer** → case studies #1 y #2, y el repo `rag-crag-reference`
- Si es un rol de **Full-Stack** → case study #4, y el repo `multi-tenant-saas-starter`

## Como trabajo (breve)

- **Eval-driven**: si no lo medimos, no lo shippeamos
- **Fallos ruidosos, no silenciosos**: prefiero un error explicito que un swallow
- **Simple > clever**: los patrones (adapter, circuit breaker, keep-together) valen mas que abstracciones nuevas
- **Sanitizacion y compliance-first** en mercados regulados
