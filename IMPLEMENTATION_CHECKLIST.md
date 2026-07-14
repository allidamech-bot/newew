# NEXORA Marketplace — Implementation Checklist (evidence-based)

## Complete / implemented in repo
- [x] Next.js App Router foundation + strict TypeScript
- [x] Central brand/platform/navigation/feature config (NEXORA)
- [x] Design tokens light/dark + local fonts (no Google Fonts network)
- [x] EN/AR i18n with structure-typed dictionaries + RTL dir switching
- [x] Mock DB + realistic seed + repository interfaces
- [x] Service locator with mock default and Supabase adapter stubs
- [x] Public marketplace: home, discover, search, categories, product, stores, deals, collections, compare
- [x] Auth UI: sign-in/up/forgot + demo accounts
- [x] Cart + multi-step mock checkout + order creation (idempotent)
- [x] Buyer account areas: overview, profile, orders/details, returns, disputes, messages, notifications, wishlists, following, reviews, addresses, security, preferences, privacy
- [x] Seller workspace: dashboard, products, wizard, inventory, orders/fulfillment, returns, messages, reviews, promotions, analytics, customers, staff model UI, shipping, store, settings, onboarding
- [x] Admin workspace: overview, users, applications, sellers/stores, product moderation, categories/attributes, orders, disputes, reports, reviews, promotions, CMS modules, feature flags, settings, audit, analytics
- [x] Help center + contact + sell landing + policy/static IA routes
- [x] Ordered Supabase migrations, helpers, RLS policies, function stubs, storage notes
- [x] Vitest unit/component tests + Playwright smoke suite
- [x] Documentation set under `docs/` + README

## Partial / limited
- [~] Supabase repositories: interface-complete stubs, not live SDK implementations
- [~] Advanced seller bulk/CSV, multi-warehouse UI depth
- [~] Full realtime chat/presence
- [~] Full Playwright 15-scenario enterprise matrix (smoke critical paths exist)
- [~] Visual QA automation at every listed viewport width (responsive CSS exists; automated multi-width suite not exhaustive)

## Missing / external credentials required
- [ ] Live Supabase project credentials
- [ ] Real payment/payout provider credentials
- [ ] Production email/SMS/push providers
- [ ] Remote repository push/PR if no git remote is configured
