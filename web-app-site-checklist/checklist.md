# ✅ Web App / Website Quality Checklist

## 1. Product & UX
- [ ] **Clear value proposition** (what, who, why → visible within 5s)
- [ ] **Onboarding flow** → main action → success feedback
- [ ] **Forms**: inline validation, actionable error messages, required fields marked
- [ ] **Accessibility (WCAG 2.1 AA)**: keyboard navigation, focus ring, color contrast ≥ 4.5:1
- [ ] **Responsive design**: tested from 320px → 1440px
- [ ] **State feedback**: loading skeleton, optimistic UI, toast/alerts
- [ ] [Optional] Dark mode, i18n, user preferences

---

## 2. Performance (Core Web Vitals)
- [ ] LCP < 2.5s, INP < 200ms, CLS < 0.1 (on mobile)
- [ ] Optimized images (size, WebP/AVIF, lazy-load), SVG icons
- [ ] Code splitting, caching strategy (HTTP + SW/PWA)
- [ ] Static files via CDN, font-display: swap
- [ ] [Optional] Preload/prefetch critical assets, RUM monitoring enabled

---

## 3. Security
- [ ] HTTPS enforced (HSTS), secure cookies (HttpOnly, Secure, SameSite)
- [ ] Authentication via proven solution (Clerk/Auth0/NextAuth), rate-limited logins
- [ ] Authorization via RBAC/ABAC, enforced on server side
- [ ] OWASP protections: XSS (CSP, escaping), CSRF, SSRF, injection prevention, safe file uploads
- [ ] Secrets managed via `.env` / secret manager
- [ ] [Optional] Audit logs & suspicious activity alerts
- [ ] [Optional] Dependency scanning (Dependabot, Snyk, etc.)

---

## 4. Privacy & Compliance
- [ ] Privacy policy, cookie consent management (GDPR/UK GDPR)
- [ ] Data minimization; PII encrypted (at-rest & in-transit)
- [ ] Data deletion/export flow (DSAR compliant)
- [ ] [Optional] Data retention rules, DPA with subprocessors

---

## 5. Architecture & Backend
- [ ] Clear API layer (REST/GraphQL), service separation, ORM/queries isolated
- [ ] Error modeling (HTTP codes, problem+json), idempotent critical endpoints
- [ ] Rate limiting, request size limits, timeouts, circuit breakers
- [ ] API versioning & migration strategy
- [ ] [Optional] Webhooks/event-driven integration, queues for heavy jobs

---

## 6. Database
- [ ] Proper indexes, unique constraints, foreign keys
- [ ] Backup & restore tested; separate prod/stage/test environments
- [ ] Soft-delete or archive strategy, audit fields (createdAt/updatedAt)
- [ ] [Optional] Read/write separation, connection pooling

---

## 7. Observability
- [ ] Structured logs (trace-id, user-id/anon-id)
- [ ] Metrics: request rate, error rate, latency, uptime monitoring
- [ ] [Optional] Distributed tracing, alert thresholds & runbooks
- [ ] [Optional] User behavior analytics (event schema defined)

---

## 8. SEO & Sharing (for content sites)
- [ ] Title, meta description, hreflang (if multi-language), sitemap.xml, robots.txt
- [ ] Open Graph / Twitter cards, canonical URLs
- [ ] [Optional] Structured data (schema.org)

---

## 9. PWA & Mobile (if required)
- [ ] Web App Manifest + Service Worker
- [ ] [Optional] Offline support, background sync, push notifications

---

## 10. Payments & Billing (if required)
- [ ] Secure payment provider (Stripe, etc.), minimize PCI scope
- [ ] Idempotent webhooks, subscription handling
- [ ] [Optional] VAT/tax handling, refund/cancel flows

---

## 11. Support & Ops
- [ ] Contact channel (support email/form), SLA expectation set
- [ ] [Optional] Status page, incident postmortems
- [ ] [Optional] Help center / FAQ, product tours

---

## 12. Documentation & Runbooks
- [ ] README with setup, `.env` example, architecture diagram
- [ ] Contributing guidelines
- [ ] Runbooks for deploy rollback, key rotation, DB restore
- [ ] [Optional] Changelog, ADR (architecture decision records)

---

## 13. Dev Process
- [ ] Branch strategy, PR review rules, code ownership
- [ ] CI/CD: lint, format, tests, build, deploy automation
- [ ] Separate environments (dev/stage/prod), feature flags
- [ ] Test pyramid: unit, integration, e2e
- [ ] [Optional] Performance tests, visual regression tests

---

## 14. Growth Features
- [ ] Email verification, password reset, notification templates
- [ ] Invite/referral flow, demo data / product tour
- [ ] [Optional] Segmentation, A/B testing, retention metrics

---

## 15. Tech Stack (Next.js/React specific)
- [ ] **Stack**: Next.js (App Router), TypeScript, Tailwind, shadcn/ui
- [ ] Auth: Clerk/NextAuth + server-side route protection
- [ ] DB: Prisma + Postgres (Neon/Supabase) with migration/seed scripts
- [ ] API Routes/Handlers validated with Zod
- [ ] Monitoring: Lighthouse, Core Web Vitals, Sentry/Logtail
- [ ] Optimized `<Image />`, dynamic imports, code-splitting
- [ ] [Optional] i18n (next-intl), sitemap/robots automation, OG image generation

---

**Scale**
- **P2** items: advanced PWA, A/B testing, multi-region, event-driven architecture, deep analytics.
