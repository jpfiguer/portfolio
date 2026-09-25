# Juan Pablo Figueroa

**AI Engineer con base de ingeniero de datos** · Google Cloud Generative AI Leader · Santiago, Chile

Diez años en ingeniería de datos, los últimos siete sobre GCP, y los dos
últimos llevando sistemas de IA de prototipo a producción con métricas.

Mi criterio: un sistema de IA que no se puede evaluar es un prototipo, corra
donde corra. La calidad de recuperación va en CI, junto a los tests.

- Email: jpablofigueroar@gmail.com
- LinkedIn: [in/juan-pablo-mac-fig](https://linkedin.com/in/juan-pablo-mac-fig)
- GitHub: [jpfiguer](https://github.com/jpfiguer)

## Casos de estudio

Cada caso documenta un sistema real: el problema, las restricciones y las
decisiones que tomé. Uso nombres y clientes genéricos y no incluyo código de
clientes; el código que publico está en los repositorios de más abajo.

1. [**RAG industrial con doble juez y circuit breaker**](./case-studies/01-rag-industrial.md)

   Sistema RAG sobre manuales técnicos para un cliente industrial europeo,
   desplegado con GPU en su infraestructura. Faithfulness con mediana de 0,96
   y context precision de 0,997, medidas con RAGAS sobre tráfico real de
   producción y capturadas semanalmente como baselines versionados. CRAG con
   doble juez (OpenAI y Claude), reranking con Voyage y circuit breaker hacia
   Cohere, chunking estructural y contextual retrieval.

2. [**Agente de voz en tiempo real**](./case-studies/02-voice-agent-realtime.md)

   Call center de IA con streaming bidireccional sobre WebSockets. Manejo de
   back-pressure, reconexión y un adapter para Twilio Media Streams.

3. [**Migración de SAP BW a BigQuery**](./case-studies/03-sap-to-bigquery.md)

   Ocho modelos críticos migrados con Dataform, con las reglas de negocio de
   SAP preservadas. Consultas optimizadas: −25% de tiempo de procesamiento y
   −50% de costo.

4. [**SaaS multi-tenant type-safe de punta a punta**](./case-studies/04-multi-tenant-saas.md)

   CRM para empresas de servicios en España, con Next.js, tRPC, Drizzle y
   PostgreSQL. WebAuthn/passkeys, rate limiting y tests con Playwright y Vitest.

5. [**Patrón adapter para integración fiscal**](./case-studies/05-adapter-pattern-sii.md)

   API interna en FastAPI para extraer el registro de compras y ventas del
   servicio tributario chileno. Una variable de entorno elige el adapter, entre
   un proveedor comercial y la conexión directa, sin cambiar el contrato con
   los consumidores.

## Código público

**Extraído de sistemas en producción**, con las partes transferibles y las
decisiones difíciles documentadas:

- [**rag-hybrid-citations**](https://github.com/jpfiguer/rag-hybrid-citations):
  RAG híbrido sobre Postgres, con búsqueda densa en pgvector y búsqueda de
  texto completo de Postgres (`ts_rank_cd`) fusionadas con RRF dentro de SQL.
  Las citas apuntan a documento y página, y cuando el corpus no tiene la
  respuesta, el sistema se niega explícitamente a responder. Su `DECISIONS.md`
  documenta bugs y decisiones que solo aparecen cuando un sistema lleva tiempo
  corriendo con datos reales.
- [**guided-visual-check**](https://github.com/jpfiguer/guided-visual-check):
  inspección visual contra una imagen de referencia. El modelo reporta
  evidencia con su nivel de confianza y la decisión la toma código auditable.
  Los ángulos y las orientaciones se le entregan ya medidos, porque en ese tipo
  de medición los modelos de visión son poco confiables.
- [**sistema-helper-en**](https://github.com/jpfiguer/sistema-helper-en):
  entrenador de entrevistas en inglés con pipeline de voz en tiempo real. El
  código calcula las métricas y el modelo aporta el juicio, separados por
  diseño.

**Implementación de referencia**, con código sintético que muestra patrones que
uso sin material de clientes:

- [**gcp-etl-pipeline**](https://github.com/jpfiguer/gcp-etl-pipeline):
  Apache Beam sobre Dataflow, Pub/Sub, BigQuery, Dataform y Terraform. Batch y
  streaming, deduplicación, particionado dinámico y validación post-carga.

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
