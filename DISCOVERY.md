# DISCOVERY — Latent Value of `organvm/fetch-familiar-friends`

*Auto-discovery beat, 2026-07-09. Verdict: **REAL VALUE — promote to the ranked value tier.** Not archival.*

## Value thesis (one paragraph)

`fetch-familiar-friends` (DogTale Daily) is mislabeled by its README as a "daily dog/cat
calendar." It is in fact the estate's **most launch-ready monetized consumer web app** and
its **most complete reusable freemium template**. It is already live and serving
(`https://fetch-familiar-friends.netlify.app` → HTTP 200), and it ships a *complete* three-tier
subscription funnel (`free`/`premium`/`luxury` in `SubscriptionContext.FEATURE_GATES`, enforced
through `src/utils/featureGates.js`) backed by real Stripe Edge Functions
(`supabase/functions/{create-checkout-session,stripe-webhook,create-portal-session}`), Supabase
auth + schema/battle/push migrations, a deep gamification engine (24 hooks — quests, battles,
leaderboards, season pass, achievements, virtual pet, friends, collections), an AI-chat service,
and a hardened service layer (rate-limited/retrying `imageApi`, `resilientStorage`,
`breedDataIngestion`, `exportService`) with 23 test files, PWA assets, and an iOS shell. The
latent value is therefore two-sided: (1) **shortest realistic time-to-first-dollar of any
consumer repo in the estate** — the payment funnel is coded end-to-end and only needs *arming*;
and (2) a **drop-in freemium+gamification reference stack** that Commerce siblings which need
exactly this shape — `gamified-coach-interface`, `classroom-rpg-aetheria` — can fork instead of
rebuild. The one honest caveat: the revenue valve is **built but unarmed** (all Stripe keys are
placeholders `pk_test_...` / `price_...`), so the last 10% — the arming — is the whole job, and
it is owner-gated on a payment credential.

## Highest latent value, ranked

1. **A live consumer product one credential away from accepting money.** The funnel exists;
   `.env.example` shows the only gap is real `VITE_STRIPE_*` price IDs + Supabase/Netlify secrets.
   Per FLAME invariant #8 (*arm the atom*), a beat-wired funnel left in permanent dry-run is an
   **unmet** ask, not a closed one. This is the single highest-leverage first move.
2. **A reusable freemium+gamification template.** `FEATURE_GATES` + `featureGates.js`, the
   gamification hooks, `resilientStorage`, and the rate-limited `imageApi` are directly liftable
   into other Commerce consumer apps. Pain-point-becomes-product: extract as a public template.

## Sovereignty note (FLAME invariant #10 — no kill-switches)

Stripe is a processor with stop-power over income and therefore a **lure, not a dependency**.
Before arming, the sovereign path is **MONETA** (self-custodied receive address, no processor in
the path) as the primary rail, with Stripe kept only as an optional secondary. Arming Stripe as
the *sole* rail would violate invariant #10 and should not be done without the MONETA fallback wired.

## Single best concrete first task

**Arm the subscription revenue valve.** Stand up the products + real price IDs on the sovereign
rail (MONETA primary; Stripe optional secondary), set the `VITE_STRIPE_*` / Supabase / Netlify
secrets, and verify **one real end-to-end checkout** against the already-live deploy — converting
DogTale Daily from a placeholder funnel into a payment-accepting product. Everything upstream of
the credential is already built; this task surfaces the single owner atom (the payment credential)
per invariant #4, then wires and proves the flow. *Public, outward-facing, revenue-first — and the
shortest credible path to a real dollar before August 1.*

*No repo stays dark. This one is not dark — it is a lit product waiting for its valve to open.*
