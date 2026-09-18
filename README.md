# Juan Pablo Figueroa

**AI Engineer con base de ingeniero de datos** · GCP Certified · Santiago, Chile

Diez años construyendo pipelines de datos en producción sobre GCP, y los dos
últimos llevando sistemas de IA de prototipo a producción con métricas.

Mi criterio: un sistema de IA que no se puede evaluar es un prototipo, corra
donde corra. La calidad de recuperación va en CI, junto a los tests.

- Email: jpablofigueroar@gmail.com
- LinkedIn: [in/juan-pablo-mac-fig](https://linkedin.com/in/juan-pablo-mac-fig)
- GitHub: [jpfiguer](https://github.com/jpfiguer)

## Casos de estudio

Cada uno documenta un sistema real —con nombres y clientes genéricos— contado
como lo pensé, lo decidí y lo medí. Sin código de cliente: el código público
vive en los repos de abajo.

1. [**RAG industrial con doble juez y circuit breaker**](./case-studies/01-rag-industrial.md)
   — sistema RAG on-premise para un cliente industrial europeo. Faithfulness
   0,96 mediana y context precision 0,997 medidos con RAGAS sobre tráfico real,
   capturados semanalmente como baselines versionados. CRAG con doble juez
   OpenAI + Claude, reranking Voyage con circuit breaker hacia Cohere, chunking
   estructural y contextual retrieval.

2. [**Agente de voz en tiempo real**](./case-studies/02-voice-agent-realtime.md)
   — call center de IA con streaming bidireccional sobre WebSockets. Manejo de
   back-pressure, reconexión y adapter para Twilio Media Streams.

3. [**Migración SAP BW → BigQuery**](./case-studies/03-sap-to-bigquery.md)
   — 8 modelos críticos migrados con Dataform, preservando las reglas de negocio
   SAP. Queries optimizadas: −25% de tiempo y −50% de costo.

4. [**SaaS multi-tenant type-safe de punta a punta**](./case-studies/04-multi-tenant-saas.md)
   — CRM para empresas de servicios en España. Next.js + tRPC + Drizzle +
   PostgreSQL, WebAuthn/passkeys, rate limiting y tests con Playwright + Vitest.

5. [**Patrón adapter para integración fiscal**](./case-studies/05-adapter-pattern-sii.md)
   — API interna en FastAPI para extraer el registro de compras y ventas del
   servicio tributario chileno. Adapter intercambiable entre proveedor comercial
   y conexión directa por variable de entorno, con el contrato downstream
   invariante.

## Código público

**Extraído de sistemas en producción** — las partes transferibles, con las
decisiones difíciles documentadas:

- [**rag-hybrid-citations**](https://github.com/jpfiguer/rag-hybrid-citations)
  — RAG híbrido sobre Postgres + pgvector: denso y BM25 fusionados con RRF
  dentro de SQL, citas que apuntan a documento y página, y rechazo explícito
  cuando el corpus no tiene la respuesta. Su `DECISIONS.md` documenta ocho bugs
  pagados en producción.
- [**guided-visual-check**](https://github.com/jpfiguer/guided-visual-check)
  — inspección visual contra una imagen de referencia. El modelo reporta
  evidencia con confianza; la decisión vive en código auditable, no en el
  prompt. Los ángulos y orientaciones se le entregan medidos, porque es donde
  los modelos de visión fallan con seguridad aparente.
- [**sistema-helper-en**](https://github.com/jpfiguer/sistema-helper-en)
  — entrenador de entrevistas en inglés con pipeline de voz en tiempo real.
  Las métricas las calcula el código y el juicio lo da el modelo, separados por
  diseño.
- [**surveybq-engine**](https://github.com/jpfiguer/surveybq-engine)
  — motor de encuestas CSAT/NPS sin dependencias ni build, con salida a
  BigQuery. Estático a propósito: quien escanea un QR llega con un navegador
  cualquiera, en algún teléfono, a veces sin señal.

**Implementaciones de referencia** — patrones que uso, escritos como código
sintético para ilustrarlos sin material de cliente:

- [**gcp-etl-pipeline**](https://github.com/jpfiguer/gcp-etl-pipeline)
  — Apache Beam sobre Dataflow, Pub/Sub, BigQuery, Dataform y Terraform. Batch
  y streaming, deduplicación, particionado dinámico y validación post-carga.
- [**rag-crag-reference**](https://github.com/jpfiguer/rag-crag-reference)
  — RAG con circuit breaker entre proveedores de reranking, doble juez
  OpenAI + Claude, chunking estructural y pipeline de evaluación con RAGAS.
- [**multi-tenant-saas-starter**](https://github.com/jpfiguer/multi-tenant-saas-starter)
  — Next.js + tRPC + Drizzle + PostgreSQL con aislamiento por tenant desde el
  primer día.

## Stack

**Datos y GCP** · BigQuery · Dataform · dbt · Apache Beam · Dataflow · Pub/Sub ·
Cloud Composer / Airflow · Cloud Functions · Cloud Run · Looker Studio

**IA** · Sistemas RAG en producción · evaluación con RAGAS · detección de
alucinaciones · reranking con circuit breaker · Qdrant · pgvector + HNSW ·
OpenAI · Claude · Gemini · Mistral · Ollama · faster-whisper · OCR

**Backend** · Python · FastAPI · SQLAlchemy 2.0 async · Celery · TypeScript ·
Express · tRPC · Next.js API Routes

**Frontend** · React · Next.js · Vue 3 · React Native / Expo · Tailwind ·
shadcn/ui

**Ops** · Docker · despliegue on-premise con GPU NVIDIA · nginx · Caddy · GCP ·
Vercel · GitHub Actions · Prometheus · OpenTelemetry · Sentry

---

Abierto a roles remotos. Español nativo, inglés técnico.
