# NEXORA Marketplace

**Discover more. Trade smarter. / اكتشف أكثر، وتسوّق بذكاء**

NEXORA is a multi-vendor marketplace platform for physical products, digital goods, and services. It is designed as a production-grade frontend architecture with a fully functional mock data layer and Supabase-ready migrations, RLS, storage design, and repository adapters.

This is **not** a generic e-commerce template. It includes buyer, seller, moderator, and admin experiences with localization (English/Arabic + RTL), light/dark themes, and mobile-first navigation.

## Stack

- Next.js 14 (App Router)
- React 18 + TypeScript (strict)
- Tailwind CSS + Radix primitives
- TanStack Query, Zustand, Zod, React Hook Form
- Vitest + Testing Library + Playwright
- Supabase-ready PostgreSQL migrations and RLS

## Quick start (mock mode)

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

Mock mode is the default (`NEXT_PUBLIC_DATA_PROVIDER=mock`). No Supabase credentials are required.

## Demo accounts

Password for all demo accounts: `demo1234`

| Email | Roles |
| --- | --- |
| `buyer@nexora.demo` | Buyer |
| `seller@nexora.demo` | Buyer + Seller |
| `staff@nexora.demo` | Store staff |
| `moderator@nexora.demo` | Moderator |
| `admin@nexora.demo` | Admin |
| `super@nexora.demo` | Super admin |

## Scripts

```bash
npm run dev          # local development
npm run build        # production build
npm run start        # start production server
npm run lint         # ESLint
npm run typecheck    # TypeScript
npm run test         # Vitest unit/component/integration
npm run test:e2e     # Playwright (requires build + browsers)
npm run test:all     # typecheck + lint + unit tests + build
```

## Environment

Copy `.env.example` to `.env.local`:

```bash
cp .env.example .env.local
```

Important variables:

- `NEXT_PUBLIC_DATA_PROVIDER=mock|supabase`
- `NEXT_PUBLIC_APP_URL`
- `NEXT_PUBLIC_SUPABASE_URL` / `NEXT_PUBLIC_SUPABASE_ANON_KEY` (Supabase mode only)

## Project structure

```text
src/
  app/                 # routes (public, account, seller, admin)
  components/          # UI, layout, commerce, discovery
  config/              # brand, platform, navigation, features
  features/            # domain client modules
  adapters/mock        # fully working mock repositories
  adapters/supabase    # Supabase-ready repository stubs
  repositories/        # repository interfaces
  services/            # service locator
  mocks/               # seed data + in-memory DB
  i18n/                # EN/AR dictionaries
  lib/                 # money, errors, env, utils
  types/               # shared domain types
supabase/migrations/   # ordered SQL migrations + RLS
docs/                  # architecture and operational docs
e2e/                   # Playwright flows
```

Branding is centralized in `src/config/brand.ts` (and related config modules). Do not scatter product naming through components.

## Supabase later

1. Create a Supabase project.
2. Apply migrations in `supabase/migrations` in order.
3. Configure storage buckets (see `docs/supabase-setup.md`).
4. Add env vars and set `NEXT_PUBLIC_DATA_PROVIDER=supabase`.
5. Replace stubbed Supabase repository methods with SDK implementations using the existing interfaces.

The UI does not call Supabase directly from pages/components.

## Documentation

- `docs/architecture.md`
- `docs/product-overview.md`
- `docs/data-model.md`
- `docs/security.md`
- `docs/authorization.md`
- `docs/supabase-setup.md`
- `docs/environment.md`
- `docs/testing.md`
- `docs/deployment.md`
- `docs/admin-guide.md`
- `docs/seller-guide.md`
- `docs/mock-data.md`
- `docs/known-limitations.md`

## Current status notes

- Mock mode is intended for local demonstration and development.
- Payment, payout, tax, and shipping providers are abstracted and mocked.
- Supabase adapters are interface-complete stubs until credentials and live SQL are applied.
- See `docs/known-limitations.md` for an honest gap list.
