# Creativa Studio — Technical Architecture

**Status:** Proposed architecture; validate versions and compatibility before implementation.

## 1. Architecture principles
- Keep the design document model independent of any rendering library.
- Separate editor UI, document state, rendering, persistence, export, and AI.
- Use incremental migrations and preserve data.
- Keep provider-specific AI logic behind adapters.
- Make manual editing independent of cloud AI availability.
- Avoid paid infrastructure until cost and alternatives are reviewed.

## 2. Proposed stack
| Layer | Proposed choice |
|---|---|
| Web application | Next.js App Router + React |
| Language | TypeScript |
| Styling | Tailwind CSS |
| Canvas adapter | Fabric.js initially, behind an application-owned abstraction |
| Validation | Zod |
| Backend/data | Supabase PostgreSQL |
| Authentication | Supabase Auth |
| File storage | Supabase Storage, with local draft support |
| Tests | Vitest + Playwright |
| CI | GitHub Actions |
| Deployment | Vercel or compatible host, subject to cost review |

Pin exact package versions after checking current compatibility. Do not add dependencies without a clear use case.

## 3. Logical application modules
- app: routes and page composition
- components: reusable accessible UI
- features/editor: editor shell, tools, panels, interactions
- features/document: document model, validation, commands, history
- features/templates: template catalog and application
- features/brands: brand-kit management
- features/carousels: multi-page documents
- features/bulk: data mapping and batch generation
- features/ai: provider adapters and structured outputs
- features/export: raster/vector/PDF export adapters
- lib: shared utilities and configuration
- supabase: migrations, policies, and edge functions
- tests: unit, integration, and end-to-end tests

## 4. Canonical design document
Persist structured editable objects, never only a screenshot. Proposed top-level fields:
- schemaVersion
- documentId
- title
- canvas: width, height, unit, background, optional DPI metadata
- objects: stable IDs, type, position, dimensions, rotation, opacity, order, visibility, lock state, and type-specific properties
- groups: group membership and transforms
- assets: references and metadata
- pages: optional ordered page/slide documents
- metadata: created/updated timestamps and editor version

Validate all documents with a versioned schema. Implement explicit migrations for future schema changes. Do not store arbitrary executable code in a document.

## 5. Editor command model
All user actions should flow through commands with reversible operations where possible. This enables undo/redo, keyboard shortcuts, reliable autosave, and future collaboration. Keep selection state separate from persisted document content.

## 6. Rendering and export
The editor renderer and export renderer must consume the same canonical document model. Export should load required fonts and assets, wait for rendering readiness, apply output dimensions and pixel ratio, and report failures. Test transparent backgrounds, font substitution, clipping, image loading, and large canvases. Do not claim print readiness until DPI and physical dimensions are verified.

## 7. Persistence
- Local draft/recovery layer for interrupted sessions
- Debounced autosave with explicit saved/saving/error state
- Cloud persistence for authenticated users
- Version snapshots at meaningful checkpoints
- Conflict handling before any multi-device collaboration is enabled

## 8. Proposed logical data entities
- profiles
- projects
- design_documents
- design_versions
- brand_kits
- templates
- assets
- carousels
- carousel_slides
- bulk_jobs
- calendar_items
- ai_jobs

This is a logical model only. Implement tables in reviewed migrations, not as one large unreviewed schema dump. Add ownership columns, indexes, constraints, and row-level security policies. Private-by-default policies must be tested with multiple users.

## 9. AI provider boundary
Define provider interfaces for text generation, structured layout proposals, image generation, and background removal. Validate structured outputs against schemas before rendering. Store provider configuration server-side. Never expose API keys to browser bundles. Log minimal operational metadata and avoid storing sensitive prompts unnecessarily.

## 10. Security
- Supabase RLS for every user-owned table
- Server-side authorization for privileged actions
- Upload MIME/type/size validation
- Safe SVG handling and sanitization
- Rate limits for expensive endpoints
- No service-role keys in client code
- Audit administrative changes
- Private project URLs must not grant access by obscurity
- Account export/deletion workflows with applicable retention rules

## 11. Deployment and CI
CI should run formatting/lint, type checks, unit tests, production build, and selected end-to-end tests. Use environment variable examples without secrets. Keep preview and production environments isolated. Database changes must be migration-based and reviewed. Do not run destructive migrations against existing projects.

## 12. Observability
Capture application errors, export failures, autosave failures, and provider errors with privacy-aware metadata. Avoid collecting design contents unless strictly necessary and disclosed.
