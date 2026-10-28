1. Load `meta-ads-best-practices`; inspect the actual `ads_*` schemas if available. For CLI load `meta-ads-cli`. Existing CLI authentication is provisioned; do not run login/auth inspection, print environment variables, extract tokens, request a pasted secret, or inspect credential stores.
2. The observed failure calls for **Meta connector reauthorization**, not account guessing. Parent can show `connect_connector(connector_id="meta_ads", force_reauth=true)` if the tool is available. Authorization must finish separately; do not retry the invalid session in a loop. This subagent did not open an authorization request.
3. After reauthorization, first run the read-only account list and verify exact ID/name/currency/timezone. Choose `act_1358975119724184` for Capsules, `act_1459085242361281` for LLA; inspect `act_1188017096669618` separately only for the old/main FA account.
4. In connector reads, `ad_account_id` is **bare numeric**, whereas CLI `--ad-account-id` is **act_ prefixed** and belongs on the `ads` subcommand. Connector `ads_get_ad_entities` uses `level` values `ad_account`, `campaign`, `adset`, `ad`; request exact IDs, canonical names, campaign_id, configured/effective status, budgets, currency/account timezone, created/updated/start/end times, learning, bid strategy, attribution_spec and promoted_object. Use the full discovered schema, not guessed argument names.
5. With CLI, use `--output json`, `list`/`get` only; run `--help` for supported field/filter/pagination flags. Save response timestamp and stdout/stderr separately. Paginate until exhausted. An empty first page or absent budget field is not proof of no campaigns or zero budget.
6. Reconcile returned account IDs and campaign ancestry before interpreting shared names. Preserve raw cents and a separately calculated USD display. Check campaign-level budget versus ad-set budget before summing. Compare configured status, effective status, learning and schedule separately.
7. Stop at read evidence. Do not use create/update/activate/delete, upload, audiences export, seed download, synthetic events or checkout transactions. Report the proposed future action separately and require fresh specific authority before any activation.

Safe CLI commands:

```bash
meta --output json ads adaccount list
meta --output json ads adaccount get act_1188017096669618
meta --output json ads adaccount get act_1358975119724184
meta --output json ads adaccount get act_1459085242361281
meta --output json ads --ad-account-id act_1358975119724184 campaign list
meta --output json ads --ad-account-id act_1358975119724184 adset list
meta --output json ads --ad-account-id act_1459085242361281 campaign get 52668266203628
meta --output json ads --ad-account-id act_1459085242361281 campaign get 52663511211628
meta --output json ads --ad-account-id act_1459085242361281 adset list
```

The runbook reflects the loaded Meta skills' CLI/connector requirements; commands above are proposed **read-only follow-up**, not successful live reads claimed for this run.

### Local evidence inventory for the parent agent

- `handover-meta-accounts-error.txt`: actual live CLI authentication error; `handover-meta-accounts-raw.json` is intentionally empty because no account JSON was returned.
- `handover-meta-historical-account.json`, `handover-meta-historical-campaigns.json`, `handover-meta-historical-adsets_52663511211628.json`, `handover-meta-historical-adsets_52668266203628.json`: GitHub archived snapshots, NOT October 28 live API results.
- `handover-meta-fa-repository.md`, `handover-meta-julie-blueprint-historical.md`, `handover-meta-repository-timeline.md`: historical repository context. Old pricing, bugs and causal claims must not override later original sessions.
- Original sessions read: `39e18618`, `5f70d990`, `219ddd45`, `20d790c3`, `2b7e0eda`, `e5d1fc33`; wiki pages read include French purchaser recovery/Capsules, Julie Meta pilot/purchaser audience/tracking, Blueprint relaunch.

**Handoff conclusion:** Current live operational status is not verified because Meta authorization is invalid. Account/campaign identity and dated historical configuration are recoverable as above. No activation, budget change, campaign pause, tracking edit, seed export or audience mutation was performed.



# Repository and infrastructure map

## Repositories and infrastructure handover

**Read-only snapshot: 28 October 2026. Window: created, updated or pushed on/after 28 September 2026, plus selected older dependencies and production organization repositories.**

### Evidence boundaries

- **Verified GitHub state** means repository metadata, branch heads, recursive Git trees, latest default-branch commit and available GitHub Pages configuration read during this inventory; the generated register below links each repository and commit.
- **HTTP checked** means a read-only HEAD request followed redirects; a 200 response does not prove current source parity, payment completion, backend correctness or approval.
- **Historical deployment reference** means an earlier handover or wiki names a deployment; no current Cloudflare/Vercel control-plane deployment comparison was performed.
- The TSV lists file and directory paths, object SHAs and sizes, not their contents; binary media, customer exports, environment/secret files and credential values were not opened for this inventory.
- Repository descriptions and filename-derived roles are discovery aids, not approval records; review, preview, mirror and production surfaces remain separate.

### Previous full Perplexity handovers found

1. **September full transfer:** `handover-master/HANDOVER.md` is “MASTER HANDOVER · v3: Omri Gitter → Next Perplexity Session,” compiled September 1; its introductory scope claims 43 active task files and 365+ preserved URLs, and the file contains a broad project register rather than only email/LLA work. These are the document’s historical counts, not the new inventory counts. [Original full handover](https://github.com/gitteromri-ux/handover-master/blob/main/HANDOVER.md)
2. **October replacement-operator transfer:** `handover-instinct-grok/MASTER-HANDOVER-2026-10-10.md` explicitly identifies Perplexity Computer as compiler and includes service access, hosting, projects, operating rules, deployment references and gaps. [October master handover](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/MASTER-HANDOVER-2026-10-10.md)
3. **Supporting materials:** `_inventory.md`, `_global-rules.md`, `_source-read-manifest.md`, `_supporting-knowledge.md`, `_today-log.md` and `projects/` are present in `handover-master`; `GAPS.md`, `VERCEL-PROJECTS.md`, setup guides and operator rules are present in the October handover repository. [Master repository](https://github.com/gitteromri-ux/handover-master) [October transfer repository](https://github.com/gitteromri-ux/handover-instinct-grok)
4. **Not a full transcript export:** the October `GAPS.md` says the described September 30 “428-file Claude migration ZIP” location was unknown and raw Perplexity transcripts were only partially represented; do not equate these narrative handovers with a complete conversation archive. [Historical transfer limitations](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)

### Hosting and release architecture

#### GitHub Pages and mirrors

- The main LLA site is `Longevity-Academy/Longevity-Academy.github.io`; Julie production is the separate `Longevity-Academy/julie-masterclass` project; community offer, recovery preview and attendee course offer have separate repositories and paths. Their current Pages source branch/path and build method are recorded in the generated register. [Main LLA site repository](https://github.com/Longevity-Academy/Longevity-Academy.github.io) [Julie production repository](https://github.com/Longevity-Academy/julie-masterclass) [Community offer](https://github.com/Longevity-Academy/masterclass-72hours) [Recovery preview](https://github.com/Longevity-Academy/julie-fix-preview) [Attendee offer](https://github.com/Longevity-Academy/blueprint-attendees-7q4x)
- `gitteromri-ux/lla-site-live` and `julie-masterclass-live` describe themselves as write mirrors intended to sync into the organization repositories and trigger Pages; that description is not proof a sync workflow currently runs, and their source histories must not be confused with organization production HEAD. [Site mirror](https://github.com/gitteromri-ux/lla-site-live) [Julie mirror](https://github.com/gitteromri-ux/julie-masterclass-live)
- Where the register reports **legacy**, GitHub Pages is configured to publish from the stated branch and folder rather than a repository-defined `actions/deploy-pages` workflow; push-to-that-branch is the normal input, while an actual successful live update needs a build/deployment check. [GitHub Pages API record for French Atelier](https://api.github.com/repos/gitteromri-ux/french-atelier/pages) [GitHub Pages API record for LLA](https://api.github.com/repos/Longevity-Academy/Longevity-Academy.github.io/pages)
- **Club Italia branch trap:** the repository default is `master`, while Pages publishes `main`; both branches are inventoried so the older default tree cannot silently replace the published review site. [Club Italia branches](https://github.com/gitteromri-ux/club-italia/branches) [Pages configuration](https://api.github.com/repos/gitteromri-ux/club-italia/pages)

#### Blueprint: Cloudflare Pages, static Worker and CRM Worker

- `gitteromri-ux/lla-course-checkout` is the maintained Blueprint checkout source; `index.html`, `checkout.html`, `assets/`, `dist/`, `worker/`, `tools/` and `capi-relay/` separate browser UI, prepared release bundle, CRM integration, deployment tooling and event relay code. [Checkout repository](https://github.com/gitteromri-ux/lla-course-checkout)
- `wrangler.static.toml` names static Worker **`lla-checkout`** and publishes **`./dist`**, not the repository root; `dist/_worker.js` is separate from the CRM integration implementation at `worker/src/index.js`. [Static Worker configuration](https://github.com/gitteromri-ux/lla-course-checkout/blob/master/wrangler.static.toml) [CRM Worker implementation](https://github.com/gitteromri-ux/lla-course-checkout/blob/master/worker/src/index.js)
- Historical production hosting also names Cloudflare Pages project **`longevitylifeacademy`**, URL `https://longevitylifeacademy.pages.dev/`, and deployment through `wrangler pages deploy dist`; this is a distinct deployment mechanism from `wrangler deploy -c wrangler.static.toml`, and neither command was executed. [Historical hosting matrix](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/MASTER-HANDOVER-2026-10-10.md)
- CRM proxy **`eteacher-leads-proxy`** handles lead/order creation, first-payment detail retrieval and payment-result reporting via `/api/lead/ecomm`, `/api/checkout/details`, `/api/checkout/payments/crm`, with `/staging` prefixes selecting staging; upstream methods are `AddNewECommerceLeadAndOrder`, `GetECommerceFirstPaymentDetails`, and `SetECommercePayment`. [Worker route specification](https://github.com/gitteromri-ux/lla-course-checkout/blob/master/worker/README.md)
- **Important recovered-source correction:** the October gaps document said Worker/relay source was not found; the current verified tree does contain `worker/src/index.js`, `dist/_worker.js`, `capi-relay/api/ac/event.js` and `capi-relay/api/meta/capi.js`, but their presence still does not prove byte-for-byte parity with current deployed services. [Earlier gap](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md) [Current checkout source](https://github.com/gitteromri-ux/lla-course-checkout)

#### Julie masterclass backend and checkout dependencies

- Julie’s browser tracking source explicitly routes to **`https://lla-ac-events.vercel.app/api/meta/capi`**, treats exact production hostname/path as an event boundary, and suppresses QA/staging traffic; tracking behavior cannot be inferred from another LLA checkout. [Julie tracking source](https://github.com/Longevity-Academy/julie-masterclass/blob/main/assets/julie-meta-tracking.js)
- Key protected browser files are `assets/julie-attribution.js`, `assets/julie-meta-tracking.js`, `assets/julie-payment-safety.js` and `assets/julie-international-checkout.js`; attribution capture, funnel events, payment guardrails and country/phone behavior are separate concerns. [Julie source tree](https://github.com/Longevity-Academy/julie-masterclass)
- `julie-payment-safety.js` sets first-payment data and validates returned payment details, initializes Airwallex, and identifies PayPal as a separate eTeacher Smart Buttons path rather than an Airwallex option; no payment was initiated during this inventory. [Payment guardrails](https://github.com/Longevity-Academy/julie-masterclass/blob/main/assets/julie-payment-safety.js)
- Historical project documentation records masterclass CRM mapping `MainAbroadCourseId 283`, `AbroadCourseId 1823`, `CampusId 4203`, `LanguageId 101`; these historical mappings are not asserted as every current Standard/VIP/session combination. [Masterclass integration handover](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-live-masterclass.md)
- Frozen relay snapshot source is preserved under `handover-master/projects/julie-tracking-freeze/relay-golden-dpl_DQogoRsNj1XXTpJQmFrRk9zzCCrU/`, including `api/ac/event.js`, `api/meta/capi.js`, `lib/julie-capi.js`, `lib/blueprint-golden-capi.js`, `lib/blueprint-receipt.js`, `lib/click-id.js` and `package.json`; a golden snapshot is historical source, not a live Vercel deployment assertion. [Tracking freeze record and source snapshot](https://github.com/gitteromri-ux/handover-master/tree/main/projects/julie-tracking-freeze)
- The attendee offer is separate from purchasing a masterclass seat: organization repository `blueprint-attendees-7q4x` contains `attendee-form.js`, `attendee-pricing.js`, `attendee-pricing.css`, `blueprint-timezones.js` and a `blueprint/` checkout tree; personal repository `lla-masterclass-attendees` is another offer/review surface and is not interchangeable solely because assets match. [Organization attendee source](https://github.com/Longevity-Academy/blueprint-attendees-7q4x) [Personal attendee source](https://github.com/gitteromri-ux/lla-masterclass-attendees)

#### French Atelier: independent frontend and shared downstream gateway

- Production website source is `gitteromri-ux/french-atelier`, with distinct marketing lead forms, language-course and Capsules enrollment pages, and `enroll-checkout.html`; `js/fa-checkout-config.js` defines product/course mapping and relay URLs, `js/fa-checkout.js` handles checkout, `js/fa-attribution.js` preserves attribution and `js/fa-meta-tracking.js` implements events. [French Atelier source](https://github.com/gitteromri-ux/french-atelier)
- Browser configuration names **`https://fa-leads-proxy.vercel.app`**, with separate CAPI and AC routes; the preserved relay snapshot lives in `handover-master/projects/french-atelier-golden-relay/`, not a standalone repository called `fa-leads-proxy` in the owner inventory. [Frontend configuration](https://github.com/gitteromri-ux/french-atelier/blob/main/js/fa-checkout-config.js) [Relay source snapshot](https://github.com/gitteromri-ux/handover-master/tree/main/projects/french-atelier-golden-relay)
- `vercel.json` rewrites lead, production/staging ecommerce, checkout-details and payment-report paths into `api/leads.js` or `api/ecomm.js`; `api/meta/capi.js` and `api/ac/event.js` remain separate functions. [Vercel route configuration](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-golden-relay/vercel.json)
- The October 20 handover and preserved relay source use **`FA_PROD_GATEWAY`** to forward production through **`https://eteacher-leads-proxy.gitter-omri.workers.dev`**; direct staging configuration and the production gateway must not be treated as the same credential boundary. [French ecommerce handover](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-ecommerce-handover-2026-10-20.md) [Relay gateway implementation](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-golden-relay/api/ecomm.js)
- **Source/deployment drift warning:** the preserved relay copy still forces ProductID 25, while later wiki history reports removal of forced ProductID for Capsules; no current Vercel source download was performed, so the snapshot must not be redeployed as an assumed current production source. [Preserved ProductID behavior](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-golden-relay/api/ecomm.js) Later operational history (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

#### Live Q&A backend

- `julie-live-qa/config.js` points the frontend to **`https://julie-live-qa-api.gitter-omri.workers.dev`**; its verified default tree contains only `config.js`, `index.html` and `questions.json`, so the backend implementation is not present in that repository tree. [Q&A repository](https://github.com/gitteromri-ux/julie-live-qa) [Backend endpoint configuration](https://github.com/gitteromri-ux/julie-live-qa/blob/main/config.js)
- Prior wiki history describes Cloudflare Durable Object SQLite for shared state and Workers AI Llama 3.3 70B for draft generation; these backend internals remain historical documentation, not a fresh control-plane verification. Recorded Q&A implementation session (original session `6956a2d3-0c30-424c-9be5-52930ff5bd1d`)

### Key file/directory interpretation

| Path family | What it stores / operational caution |
|---|---|
| `index.html`, `*.html`, `css/`, `js/`, `assets/*.js` | Browser pages and client-side behavior; filenames alone do not certify the live version. |
| `assets/`, `img/`, `images/`, `videos/`, `downloads/`, `fonts/` | Media, fonts and downloads; inventory is metadata-only, no binary asset bytes were read. |
| `dist/` | Prepared deployable bundle; can differ from top-level development files. |
| `worker/`, `api/`, `lib/`, `capi-relay/` | Backend/relay source or archived serverless implementation; presence does not establish deployed parity. |
| `.github/workflows/` | Automation definitions; the S09/S10 repository includes numerous media-processing workflows, not just site publication. |
| `tools/`, `scripts/` | Build, render, audit or deployment utilities; nothing executed beyond inventory scripts. |
| `projects/`, `HANDOVER.md`, `README.md`, `rules/`, `evidence/` | Operating documentation and snapshots; timestamps and evidence labels matter. |
| `data/`, `exports/`, `snapshots/`, `*.csv`, `*.xlsx` | Potential business/customer or historical account data; paths only, contents not collected. |
| `.env*`, credential-shaped filenames | Listed as paths if committed, never opened. |

The per-repository directory and key-file listings below derive from verified Git trees; path roles are explicitly classification rather than content review. [Owner repositories](https://github.com/gitteromri-ux) [Production organization](https://github.com/Longevity-Academy)

### Gaps and safety constraints

- Current GitHub trees are complete only where the generated audit reports `truncated=false`; branch aliases at the same commit reuse one verified tree while remaining separate TSV branch rows.
- Repo `pushedAt`, latest default-branch commit time and Pages source are different facts; none is a substitute for deployed asset hashes.
- GitHub Pages API 404 means unavailable/not configured under current access, not proof the project is offline everywhere.
- No Cloudflare or Vercel secret values, customer exports, CRM writes, payment attempts, repository changes or deployments were performed.
- Current Vercel/Cloudflare deployment IDs, backend source parity, private credential ownership, automation activation and order/payment reconciliation remain outside this repository-only proof.
- Older repositories not selected as dependencies remain in `repository-metadata.json`; their trees are not represented as newly inspected.




## Verified per-repository register

File counts include multiple inspected branches where present. A Git tree listing is not a content or live deployment audit. The companion TSV provides every collected path, object SHA, size and source URL.

### Longevity-Academy/Longevity-Academy.github.io

- **Repository:** [Longevity-Academy/Longevity-Academy.github.io](https://github.com/Longevity-Academy/Longevity-Academy.github.io); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `backup-pre-v8-text-changes-20260507-130526`, `main`, `pricing-preview`, `staging`, `v1-backup`, `v44-redesign`.
- **Inventory:** 2,039 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `b4435d50a6dc28d7c6b2c8583f70c924f124405b`; 2026-10-27T10:16:56Z; Revert "Replace unlisted guest page without changing public navigation or URLs".
- **Pages configuration:** https://www.longevitylifeacademy.com/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.build-trigger`, `.gitignore`, `.netlify`, `.nojekyll`, `.well-known`, `200.html`, `CNAME`, `about.html`, `assets`, `biological-age-light.html`, `blog.html`, `blueprint`, `cgm.html`, `checkout`, `enroll-staging.html`, `go`, `guides`, `homepage_backup_20260417_161625.html`, `homepage_backup_20260417_172852.html`, `index-light-backup-apr18.html`, `index-light-broken-attempt.html`, `index-light-correct-base.html`, `index-light-v1-pricing.html`, `index-light.html`, `index-v1.html`, `index-v2.html`, `index.html`, `internal`, `lp`, `pricing-preview.html`, `pricing.html`, `privacy.html`, `refer-a-friend`, `robots.txt`, `screenshots-overhaul`, `sitemap.xml`, `store`, `support`, `teachers`, `terms.html`, `thank-you.html`, `topics`, `vercel.json`.

### Longevity-Academy/blueprint-attendees-7q4x

- **Repository:** [Longevity-Academy/blueprint-attendees-7q4x](https://github.com/Longevity-Academy/blueprint-attendees-7q4x); public/visibility not independently specified.
- **Purpose:** Unlisted attendee offer page for Julie's masterclass (noindex, link-only)
- **Branches inspected:** `main`.
- **Inventory:** 260 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `2991f8732859f956eecff6a41826313f2123f154`; 2026-10-27T22:52:27Z; Keep attendee questions below the full course-inclusions section.
- **Pages configuration:** http://www.longevitylifeacademy.com/blueprint-attendees-7q4x/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `attendee-form.js`, `attendee-pricing.css`, `attendee-pricing.js`, `blueprint`, `blueprint-timezones.js`, `brand-typography.css`, `course-film-player.js`, `exact-attendee-copy.js`, `exact-source-design.css`, `guest-mobile.css`, `guest-mobile.js`, `index.html`, `launch-flow.css`, `launch-flow.js`, `lp`, `offer-mobile.css`, `offer-mobile.js`, `pricing-clarity.css`, `pricing-replica.css`, `pricing-space.css`, `robots.txt`.

### Longevity-Academy/julie-fix-preview

- **Repository:** [Longevity-Academy/julie-fix-preview](https://github.com/Longevity-Academy/julie-fix-preview); public/visibility not independently specified.
- **Purpose:** Julie masterclass preview: SDK retry fix + v9 pricing cards and 72h strip. Production untouched.
- **Branches inspected:** `main`.
- **Inventory:** 116 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `8df6b8640000f6345f8df79af2338064a5e91bb7`; 2026-10-18T20:53:09Z; Revert "Preview = production cf899f2 (15 Oct build) + phone robustness CSS block (font-scaling safe). noindex. Tracking/checkout files untouched.".
- **Pages configuration:** http://www.longevitylifeacademy.com/julie-fix-preview/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `index.html`, `privacy.html`, `support`.

### Longevity-Academy/julie-masterclass

- **Repository:** [Longevity-Academy/julie-masterclass](https://github.com/Longevity-Academy/julie-masterclass); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `backup/20260927-1708-tracking`, `backup/20260927-julie-before-promotion`, `backup/20260927-julie-tracking`, `backup/20260928-0035-capi-timing`, `change/20260929-hero-desktop`, `change/20260930-checkout-continue`, `change/20260930-desktop-pricing-compact`, `change/20260930-pricing-copy`, `change/20260930-remove-backup`, `change/20261001-hero-pricing-polish`, `change/20261001-phone-readability`, `change/20261001-vip-hero-colors`, `change/20261009-mobile-compact-checkout`, `change/20261014-36off`, `change/20261014-mobile`, `design/pay-button-logo-2x`, `fix/julie-attribution-20260927`, `fix/julie-capi-timing-20260928`, `fix/julie-tracking-20260927`, `fix/julie-tracking-current-20260927`, `fix/mobile-header-20260928`, `main`.
- **Inventory:** 2,448 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `1ef760dc70224e97fe39b6cb13ccc1dba2e6fae2`; 2026-10-26T10:02:01Z; Preserve generic promo label and private guest invitation.
- **Pages configuration:** http://www.longevitylifeacademy.com/julie-masterclass/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `index-v50-backup.html`, `index.html`, `privacy.html`, `support`.

### Longevity-Academy/lla-checkout-live

- **Repository:** [Longevity-Academy/lla-checkout-live](https://github.com/Longevity-Academy/lla-checkout-live); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 190 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `9d955d3735012a647d8913264f2aaa4909e22989`; 2026-09-09T14:28:56Z; LLA checkout live build (master 242f022).
- **Pages configuration:** ; build type ``; source `{}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `checkout.html`, `index.html`.

### Longevity-Academy/masterclass-72hours

- **Repository:** [Longevity-Academy/masterclass-72hours](https://github.com/Longevity-Academy/masterclass-72hours); public/visibility not independently specified.
- **Purpose:** Julie masterclass 72-hour community-offer LP (email blast). Separate duplicate; production julie-masterclass untouched.
- **Branches inspected:** `main`, `phone-guard`.
- **Inventory:** 234 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `a68b6edaf2e238abf1871171c6c83fb543ec0eaf`; 2026-10-18T14:07:40Z; Set universal 72h campaign clock: Oct18 17:00 Israel to Oct21 17:00; never restart; resume catch-up.
- **Pages configuration:** http://www.longevitylifeacademy.com/masterclass-72hours/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `index.html`, `privacy.html`, `support`.

### gitteromri-ux/club-italia

- **Repository:** [gitteromri-ux/club-italia](https://github.com/gitteromri-ux/club-italia); public/visibility not independently specified.
- **Purpose:** Club Italia by eTeacher: live-online Italian language school (structural parity with FrenchAtelierLive)
- **Branches inspected:** `main`, `master`, `v17-redesign`.
- **Inventory:** 902 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `9c8f4201e92c7de4e2bfcc96a8ccd33d29135435`; 2026-09-10T10:15:11Z; Club Italia v1: full FrenchAtelierLive-parity site (24 core + 11 courses + 11 blog + 11 syllabus PDFs).
- **Pages configuration:** https://gitteromri-ux.github.io/club-italia/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `.nudge`, `AGENT_B_REPORT.md`, `AGENT_SECONDARY_REPORT.md`, `BIAGIO_BUILD_REPORT.md`, `FA_PORT_REPORT.md`, `README.md`, `REAL_ASSETS_REPORT.md`, `V4_REBUILD_REPORT.md`, `__pycache__`, `_brand.py`, `_build_biagio_v2.py`, `_build_home.py`, `_build_new_pages.py`, `_build_secondary.py`, `_ci_build.py`, `_ci_build2.py`, `_ci_build3.py`, `_fa_port_build.py`, `_home17_build.py`, `_page_deepen.py`, `_page_events.py`, `_page_map.py`, `_page_rest.py`, `_partials`, `_sales_build.py`, `_v17_build.py`, `_v18_build.py`, `_v18_pages.py`, `_v18_reskin.py`, `_v19_build.py`, `_v19_legacy.py`, `_v20_build.py`, `_v21_course.py`, `_v21_fix.py`, `_v21_home.py`, `_v21_map.py`, `_v3_build.py`, `_v3_tier2.py`, `_v4`, `_v8_build.py`, `about.html`, `assets`, `biagio.html`, `blog.html`, `build.py`, `build2.py`, `build3.py`, `build_agent_c.py`, `build_agent_c2.py`, `build_agent_c3.py`, `build_fa.py`, `build_fa_courses.py`, `build_fa_indexes.py`, `build_svgs.py`, `build_tools`, `build_zoom_luxury.py`, `capsules.html`, `certifications.html`, `community.html`, `contact.html`, `courses.html`, `css`, `culture.html`, `curriculum.html`, `eteacher.html`, `events.html`, `fa`, `faq.html`, `gen_placeholders.py`, `how-it-works.html`, `index.html`, `js`, `map.html`, `method.html`, `pages`, `pdf`, `pricing.html`, `privacy.html`, `rasterize.py`, `research`, `sample-class.html`, `teachers.html`, `terms.html`, `tts_scripts`, `zoom-luxury-findings.md`.

### gitteromri-ux/club-italia-preview

- **Repository:** [gitteromri-ux/club-italia-preview](https://github.com/gitteromri-ux/club-italia-preview); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 410 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `e1b9a8bb8bf0bf7c446ddc03815a68bd5fde8248`; 2026-10-11T21:11:43Z; v26.
- **Pages configuration:** https://gitteromri-ux.github.io/club-italia-preview/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `.nudge`, `AGENT_B_REPORT.md`, `AGENT_SECONDARY_REPORT.md`, `BIAGIO_BUILD_REPORT.md`, `FA_PORT_REPORT.md`, `README.md`, `REAL_ASSETS_REPORT.md`, `V4_REBUILD_REPORT.md`, `__pycache__`, `_brand.py`, `_build_biagio_v2.py`, `_build_home.py`, `_build_new_pages.py`, `_build_secondary.py`, `_ci_build.py`, `_ci_build2.py`, `_ci_build3.py`, `_fa_port_build.py`, `_home17_build.py`, `_page_deepen.py`, `_page_events.py`, `_page_map.py`, `_page_rest.py`, `_partials`, `_sales_build.py`, `_v17_build.py`, `_v18_build.py`, `_v18_pages.py`, `_v18_reskin.py`, `_v19_build.py`, `_v19_legacy.py`, `_v20_build.py`, `_v21_course.py`, `_v21_fix.py`, `_v21_home.py`, `_v21_map.py`, `_v3_build.py`, `_v3_tier2.py`, `_v4`, `_v8_build.py`, `about.html`, `assets`, `biagio.html`, `blog.html`, `build.py`, `build2.py`, `build3.py`, `build_agent_c.py`, `build_agent_c2.py`, `build_agent_c3.py`, `build_fa.py`, `build_fa_courses.py`, `build_fa_indexes.py`, `build_svgs.py`, `build_tools`, `build_zoom_luxury.py`, `capsules.html`, `certifications.html`, `community.html`, `contact.html`, `courses.html`, `css`, `culture.html`, `curriculum.html`, `eteacher.html`, `events.html`, `fa`, `faq.html`, `gen_placeholders.py`, `how-it-works.html`, `index.html`, `js`, `map.html`, `method.html`, `pages`, `pdf`, `pricing.html`, `privacy.html`, `rasterize.py`, `research`, `sample-class.html`, `teachers.html`, `terms.html`, `tts_scripts`, `zoom-luxury-findings.md`.

### gitteromri-ux/cultural-capsules-pack3

- **Repository:** [gitteromri-ux/cultural-capsules-pack3](https://github.com/gitteromri-ux/cultural-capsules-pack3); public/visibility not independently specified.
- **Purpose:** French Atelier: Cultural Capsules Pack 3: Cinema & Music (10 decks)
- **Branches inspected:** `main`.
- **Inventory:** 294 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `3636e7fbbc4e9e783f93a679cbb1fb276a24ca0a`; 2026-10-08T10:06:35Z; Audit pass: abbreviation-safe sentence cuts, 8 hand-written short blocks, hook captions clear of illustration; 262 slides checked.
- **Pages configuration:** https://gitteromri-ux.github.io/cultural-capsules-pack3/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `Cultural_Capsules_Visual_Canvas_His_vs_Ours.pdf`, `README.md`, `decks`, `index.html`, `preview`.

### gitteromri-ux/fa-capsules-launch

- **Repository:** [gitteromri-ux/fa-capsules-launch](https://github.com/gitteromri-ux/fa-capsules-launch); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `bridge`, `main`.
- **Inventory:** 1,361 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `708a86f3be5754d475291d5665022d53be09a329`; 2026-10-22T08:02:37Z; Video kit: New to upload, 22 October section with the three new UGC cuts.
- **Pages configuration:** https://gitteromri-ux.github.io/fa-capsules-launch/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.github`, `.nojekyll`, `README.md`, `ad-board`, `app.js`, `banners`, `bridge`, `catalog.json`, `downloads`, `emails`, `index.html`, `media`, `meta-banners`, `styles.css`, `video-kit`, `website`.

### gitteromri-ux/fa-capsules-review-public

- **Repository:** [gitteromri-ux/fa-capsules-review-public](https://github.com/gitteromri-ux/fa-capsules-review-public); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 352 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `39451a8b1d51745c9d8b1af3502739b3738eedd2`; 2026-10-19T08:44:25Z; Publish Culture Capsules review with visible programmes and revised design.
- **Pages configuration:** https://gitteromri-ux.github.io/fa-capsules-review-public/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.nojekyll`, `.vercelignore`, `_ext`, `about.html`, `acadomia.html`, `assets`, `blog`, `blog.html`, `capsules.html`, `cdn-cgi`, `contact.html`, `courses`, `courses.html`, `css`, `culture.html`, `downloads`, `faq.html`, `how-it-works.html`, `index.html`, `js`, `juliane.html`, `map.html`, `method.html`, `pricing.html`, `privacy.html`, `teachers.html`, `terms.html`, `vercel.json`.

### gitteromri-ux/final-versions

- **Repository:** [gitteromri-ux/final-versions](https://github.com/gitteromri-ux/final-versions); public/visibility not independently specified.
- **Purpose:** Julie Masterclass UGC Ads · FINAL VERSIONS
- **Branches inspected:** `claude/audits-2026-10-01`, `claude/ugc-fixes`, `main`.
- **Inventory:** 529 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `7b93fa71165ab690486476fb31c517ceb28b50a9`; 2026-10-01T13:24:16Z; deploy 2026-10-01T13:24Z: 2 videos.
- **Pages configuration:** https://gitteromri-ux.github.io/final-versions/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.nojekyll`, `AUDIT.md`, `BRIEF.md`, `HANDOVER-TO-CLAUDE.md`, `META-UPLOAD-SPEC.md`, `NOTE-formats-caption-highlight-bug.md`, `PRESS-SOURCES.md`, `REPORT-durations.md`, `REPORT-formats.md`, `REPORT-site.md`, `RESPONSE-v10.md`, `RESPONSE-v11.md`, `RESPONSE-v12.md`, `_shot_index_desktop.jpg`, `_shot_index_mobile.jpg`, `_shot_video_mobile.jpg`, `ad1-man42__16x9__60.html`, `ad1-man42__1x1__60.html`, `ad1-man42__4x5__60.html`, `ad1-man42__9x16__45.html`, `ad1-man42__9x16__60.html`, `ad1-man42__9x16__75.html`, `ad2-woman42__16x9__60.html`, `ad2-woman42__1x1__60.html`, `ad2-woman42__4x5__60.html`, `ad2-woman42__9x16__45.html`, `ad2-woman42__9x16__60.html`, `ad2-woman42__9x16__75.html`, `ad3-woman51__16x9__60.html`, `ad3-woman51__1x1__60.html`, `ad3-woman51__4x5__60.html`, `ad3-woman51__9x16__45.html`, `ad3-woman51__9x16__60.html`, `ad3-woman51__9x16__75.html`, `ad5-woman46__1x1__75.html`, `ad5-woman46__9x16__75.html`, `audit`, `audit_frames`, `audits`, `build_site.py`, `claude-fixes`, `claude_audit_docx.txt`, `deploy.sh`, `index.html`, `manifest.json`, `posters`, `site-audit`, `videos`.

### gitteromri-ux/french-atelier

- **Repository:** [gitteromri-ux/french-atelier](https://github.com/gitteromri-ux/french-atelier); public/visibility not independently specified.
- **Purpose:** The French Atelier by Acadomia: world-class French e-learning website
- **Branches inspected:** `main`, `review/teachers-7-grid`, `staging-capsules-light`, `staging-checkout`, `staging-checkout-ecom-dark`.
- **Inventory:** 2,504 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `e4b79e052b3960d65b79720a96df197b47305ff8`; 2026-10-26T10:11:50Z; Student reuse keyed on the same verified buyer identity as the order signature.
- **Pages configuration:** https://www.frenchatelierlive.com/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.nojekyll`, `.vercelignore`, `CNAME`, `_apply_nav.py`, `_audit_assets.py`, `_nav_fix.py`, `_nav_fix2.py`, `_nav_transform.py`, `_nocache.py`, `_partials`, `_restructure.py`, `about.html`, `acadomia.html`, `assets`, `blog`, `blog.html`, `capsules.html`, `checkout.html`, `contact.html`, `courses`, `courses.html`, `crush_assets.sh`, `crush_images.py`, `css`, `culture-capsules-enroll.html`, `culture-capsules.html`, `culture.html`, `data`, `docs`, `downloads`, `enroll-checkout.html`, `faq.html`, `french-course-enroll.html`, `how-it-works.html`, `index.html`, `js`, `juliane.html`, `map.html`, `method.html`, `pricing.html`, `privacy.html`, `qa_clusters.js`, `qa_rail.js`, `recompress_hq.py`, `robots.txt`, `sitemap.xml`, `teachers.html`, `terms.html`, `vercel.json`.

### gitteromri-ux/french-atelier-acq-drip

- **Repository:** [gitteromri-ux/french-atelier-acq-drip](https://github.com/gitteromri-ux/french-atelier-acq-drip); public/visibility not independently specified.
- **Purpose:** French Atelier - ACQ Drip Series Stage 3: 12 emails, 12 landing pages, quiz, promo claim page, 36 exact-size images
- **Branches inspected:** `main`.
- **Inventory:** 72 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `2828c47615a0fea96291ae069a69b8064a976c79`; 2026-08-05T14:34:48Z; Match email chrome to last-delivery onboarding spec: 700px main, 768px breakpoint, dual hero imgs, ref CTA wrapper.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-acq-drip/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `emails`, `index.html`, `landing-pages`, `promo`, `quiz`.

### gitteromri-ux/french-atelier-capsules

- **Repository:** [gitteromri-ux/french-atelier-capsules](https://github.com/gitteromri-ux/french-atelier-capsules); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 128 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `24fe6c02d6cdacb291159d72afd5d62bd1cab952`; 2026-10-23T01:40:42Z; Preview: reword comment in slider JS.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-capsules/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `assets`, `culture-capsules-mobile-preview-20261023`, `index.html`.

### gitteromri-ux/french-atelier-jv-deck

- **Repository:** [gitteromri-ux/french-atelier-jv-deck](https://github.com/gitteromri-ux/french-atelier-jv-deck); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 73 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `67a0c2921c283ae3fe17e2a39e586bf888935487`; 2026-10-07T08:10:12Z; Capsule labels readable; 3 large readable emails.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-jv-deck/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `French-Atelier-Initiatives-Oct-2026.pptx`, `README.md`, `img`, `index.html`, `media`.

### gitteromri-ux/french-atelier-lifecycle-emails

