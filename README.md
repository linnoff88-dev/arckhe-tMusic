ï»¿tmusic ê¢â¬â Monorepo (Next.js + PNPM)

ConteêÂºdo

- Apps: `apps/web` (Next.js 14 ê¢â¬â App Router)
- Pacotes: `packages/shared` (tipos/validaêÂ§êÂµes ê¢â¬â a preencher)
- Infra: `infra/docker-compose.yml` (Postgres)

PrêÂ©ê¢â¬ârequisitos

- Node.js >= 18.17
- PNPM >= 8

InstalaêÂ§êÂ£o

- `pnpm i`

Executar (dev)

- `pnpm --filter @tmusic/web dev`
- App em `http://localhost:3000`

Build/Start (prod)

- `pnpm --filter @tmusic/web build`
- `pnpm --filter @tmusic/web start`

Lint/Format

- `pnpm --filter @tmusic/web lint`

Estrutura (web)

- `app/` ê¢â¬â pêÂ¡ginas (App Router)
  - `page.tsx` ê¢â¬â Home com Top 10 por categoria (MêÂºsicas, Bandas, DJs, IA)
  - `rankings/[category]/page.tsx` ê¢â¬â pêÂ¡ginas por categoria
  - `api/v1/*` ê¢â¬â rotas BFF (rankings, tracks, votes)
- `components/` ê¢â¬â UI (RankCard, RankSection, Filters, CategoryTabs, VoteToggle)
- `lib/` ê¢â¬â dados e mocks (rankings, tracks)

API (BFF)

- `GET /api/v1/rankings?category&scope&platform&timeframe` ê¢â¬â Top 10 por categoria (mock)
- `GET /api/v1/tracks/[id]` ê¢â¬â detalhe de faixa (mock)
- `POST /api/v1/votes` ê¢â¬â registra voto (gostei/neutral/detestei) [MVP]

PrêÂ³ximos Passos

- Prisma + Postgres para rankings reais e votos persistentes
- PêÂ¡ginas de perfil para Bandas/DJs
- Testes (unit/integration/e2e) + CI


Deploy
- Produê§êo: https://t-music-web.vercel.app
- CI: GitHub Actions (lint/build) em .github/workflows/ci.yml
- Vercel: Root apps/web, Install pnpm i, Build pnpm --filter @tmusic/web build, Output .next

SEO
- metadataBase configurado para a URL pêºblica
- OG image gerada em runtime (app/opengraph-image.tsx)

Documentaê§êo
- Plano de Integraê§êo de Fontes & APIs: docs/roadmap-fontes-e-apis.md

Documentaê§êo
- Plano de Integraê§êo de Fontes & APIs: docs/roadmap-fontes-e-apis.md
- Plano de Negê³cio: docs/negocio/plano.md

---

Projeto  - ARCKHÉe