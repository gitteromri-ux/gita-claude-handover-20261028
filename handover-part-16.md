- **Forced-block iPhone 16 Pro Max**: Omri’s final relayed BrowserStack Safari/iOS 27 retest uses `qablock=1`, reaches payment in under ten seconds and opens PayPal’s guest-card form. Fields were left empty and no payment was made. This opt-in flag simulates SDK failure; it does not identify the cause or prevalence of organic failures. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **iPhone 15 control**: The same report, without `qablock`, shows Airwallex fields, Apple Pay and Google Pay with “Pay 49.00 USD.” Earlier organic testing on the 16 Pro Max lacked Airwallex/Apple Pay. Neither rendering result is completed-payment evidence, and two devices do not measure affected-traffic share. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Android charge is a different proof layer**: Omri’s $49 order `8054067` is a real Android payment marked as a test for reporting, not an iPhone/Apple Pay test. Refund completion is not established. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Approved presentation scope

- **Named components only**: Omri initially permitted the two pricing cards, top countdown strip and payment fix, not replacement of other folds from the supplied design. Later explicit requests added the hero-button visibility repair, larger mobile logo and top/mobile Enroll controls opening checkout directly. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Final requested design is white/light blue**: Omri’s final design instruction specifies white Standard, light-blue VIP with neon lighting and dark readable text, unchanged fonts, larger corner dates and plain two-color hero dates without boxes. It removes the VIP follow-up-email and Standard date bullets. The assistant reported deployment, but those designs were later rolled back. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- **Persistent countdown is visitor-relative**: The recovery design displays $49/$77 and $79/$124 with a shared 72-hour clock. Its browser-local window persists across reloads and starts another window after expiry; it is not a fixed global offer deadline. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Concrete benefits without a false course-included promise**: Omri requested short bullets for Julie’s protocol, daily habits, 18 live sessions across 18 weeks, Lingo CGM shipment by lesson 5 and eTeacher platform/community access. The assistant places the course-specific bullets under “$249 credit toward The Longevity Blueprint course” and removes “cash back after you pay”; this is the delivered wording, not established redemption terms or acceptance of that framing. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Visible controls, not screenshots alone**: The final trajectory records hero opacity `1`, a 56px mobile logo and a top-Enroll click opening the modal. The assistant also reports removing SEPA from PayPal options. These final design changes followed the relayed device retests. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)

### See also

- `projects/lla-julie-masterclass`: production purchase destination
- `projects/lla-julie-tracking`: protected attribution contract
- `projects/lla-julie-community-offer`: separate community offer clone
- `projects/lla-julie-checkout-incident`: rollback evidence and order reconciliation


---

Record: `lla-julie-checkout-incident` | knowledge last updated: 2026-10-19T01:21:00+00:00

## Julie Checkout Rollback Audit

Julie Checkout Rollback Audit is Omri’s investigation of the 2026-10-17 sales interruption and recovery after reversing the masterclass page’s payment-init and design changes. The rollback is confirmed; the investigation does not establish whether the changed build caused missed payments. Checkout telemetry, CRM-paid orders, Meta events and processor settlement provide different evidence. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)

### What happened

Omri explicitly ordered rollback after challenging repeated all-device checkout assurances. Production commit `cf899f2`, timestamped 2026-10-17 12:46:18 UTC, restores `a188c6c`, the 2026-10-15 production version. It removes the day’s recovery/design pushes while retaining that version’s merged tracking coverage patch. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/cf899f2594e7acb209c0bee27acf99c07d234fdb))

- **Rollback verification is bounded**: The post-rollback check confirmed the original deferred Airwallex script, removal of the new cards/promo strip and an unpaid $49 payment screen. The QA created order `8054071`; no real iPhone payment was completed by that check. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- **Logs are not an exhaustive paid-order register**: At 16:54 Israel, Fort Myers telemetry contains a payment-report preflight without its corresponding POST, despite observability sampling set to 1. The audit withdrew its “zero paid” counts for the overnight and changed-build windows. Missing worker entries cannot establish no payment; a preflight is not itself settlement evidence. (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- **User-reported recovery and verified cause differ**: Omri reports five sales after approximately 16:00 Israel, following rollback. That report prompted further investigation, but the timing alone does not establish the failure mechanism. (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- **Form rendering does not certify Safari payments**: Chromium with an iPhone user agent rendered payment fields; it is not real iPhone Safari or an Apple Pay capture. The exact-build real-device comparison has no completed result in the reviewed evidence. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- **Production identity and sales are separate checks**: The 2026-10-18 record reports production still at `cf899f2` and fourteen fetched files matching that commit. Omri’s later thirteen-sale correction is not proof of unchanged files, and a code comparison is not completed-payment or attribution certification. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

### Order reconciliation

The 2026-10-17 19:28 Israel CRM read reports six paid orders totaling $324, including Omri’s $49 test. Excluding that test leaves five CRM-paid orders totaling $275 across three buyer contacts. These are CRM statuses, not a processor settlement/refund ledger. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

| CRM order | Israel paid time | Amount | Classification |
|---|---|---|---|
| `8054067` | 15:13 | $49 | Omri’s paid test |
| `8054074` | 16:12 | $49 | First Standard order, buyer A |
| `8054075` | 16:26 | $79 | VIP order, buyer B |
| `8054078` | 16:34 | $49 | Further Standard order, buyer A |
| `8054080` | 16:54 | $49 | First Standard order, buyer C |
| `8054109` | 19:10 | $49 | Further Standard order, buyer C |

All table entries derive from the same CRM read. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **Repeat purchases are not automatically accidental charges**: Further orders carry last-click email links `jm-a2-1` and `jm-a2-3`. The records do not distinguish extra tickets from accidental repurchase; buyer intent and refund necessity are unresolved. They remain separate paid-order records, not new unique people. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Meta counts are not order-level matches**: The latest scheduled read reports five Meta purchases and $275 value for the 2026-10-17 reporting day, versus the six-order CRM read including the test. Equal aggregate customer-order value does not identify matched events, exclude the test or prove tracking loss/clearance. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **QA disposition is separate from reporting exclusion**: Unpaid probes `8054068` and `8054071` and paid test `8054067` are excluded from commercial interpretation. Refund/cleanup completion is not established. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Card-route telemetry omits other payment paths**: On 2026-10-18 Omri corrected the assistant’s ten logged payments to thirteen CRM sales. The assistant acknowledged its card-route log misses PayPal captures; the thirteen is user-reported, not a new processor reconciliation. The earlier original-five report of twelve Meta/claimed CRM purchases has a different cutoff and scope. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### See also

- `projects/lla-julie-checkout-recovery`: reverted payment recovery build
- `projects/lla-julie-tracking`: frozen tag versus rollback baseline
- `projects/lla-julie-meta-pilot`: campaign configuration and event reports
- `projects/lla-julie-masterclass`: production commerce surface


---

Record: `lla-growth-engine` | knowledge last updated: 2026-10-19T01:21:00+00:00

## LLA Growth Engine

LLA Growth Engine is the full-funnel ecommerce recovery and remarketing system for Longevity Life Academy (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) ([recorded evidence](https://github.com/gitteromri-ux/lla-growth-engine)).

### How it works

The public hub combines the checkout journey with lifecycle recovery, 15 retargeting banners, a seven-day cross-channel touchpoint map, social assets, benchmarks, and a channel scoreboard (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) ([recorded evidence](https://github.com/gitteromri-ux/lla-growth-engine)). Its email layer now spans 20 messages across five funnels ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/4b42bd61a14be5db54bb5b7cc7b6bb28d5f48430)).

- **Numbers-first executive presentation**: The hub leads with touchpoint counts and channel scorecards, then limits explanations to one line so the system can be understood quickly in a CEO review ([recorded evidence](https://github.com/gitteromri-ux/lla-growth-engine)).
- **Segmented recovery rather than one generic sequence**: The email layer uses three abandoned-cart paths, consolidated onboarding, and a delayed no-show path rather than treating every contact as the same incomplete checkout ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/4b42bd61a14be5db54bb5b7cc7b6bb28d5f48430)).
- **One verified offer truth across channels**: Email, Meta, Instagram, and checkout assets must use the same currently verified course structure, price, terms, destination, and LLA-by-eTeacher positioning; conflicting historical price references are not launch inputs (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`).
- **Master-hub integration**: The Growth Engine remains its own specialist surface while the `longevity-assets` delivery hub embeds it beside checkout, films, banners, PR, and strategy materials for one-link review (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)).
- **Hybrid acquisition, distinct funnels**: Omri’s `projects/lla-october-board-update` maintains low-volume traditional lead generation while prioritizing ecommerce and routing abandoned-cart prospects to sales. Blueprint’s direct-sales relaunch is separate from converting Julie’s paying masterclass community into course buyers; masterclass learnings inform the direct funnel rather than replacing it. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

### Key surfaces

- Repo: `gitteromri-ux/lla-growth-engine` ([recorded evidence](https://github.com/gitteromri-ux/lla-growth-engine))
- Hub: `https://gitteromri-ux.github.io/lla-growth-engine/` (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`)

### See also

- `projects/lla-course-checkout`: transaction funnel
- `projects/lla-ad-banner-campaign`: paid-media creative system
- `entities/longevity-life-academy`: client and offer
- `projects/lla-delta-force`: go-live activation
- `projects/lla-masterclass-emails`: lifecycle email layer
- `projects/lla-funnel-performance-deck`: measured campaign economics


---

Record: `lla-promo-email-funnel` | knowledge last updated: 2026-10-15T05:34:00+00:00

## LLA Promo Email Funnel

LLA Promo Email Funnel is the Longevity Life Academy email-campaign funnel with promo emails, gated founder LPs, and eTeacher CRM routing for campaign-specific leads (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`) ([recorded evidence](https://github.com/gitteromri-ux/lla-promo-emails)).

### How it works

The funnel uses the `lla-promo-emails` repo as the preview/build surface for two LPs and four promo emails, then deploys the LPs under `www.longevitylifeacademy.com/lp/` with a secret campaign token and CRM wiring into eTeacher (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`) ([recorded evidence](https://github.com/gitteromri-ux/lla-promo-emails)).

- **Gated campaign URLs**: The founder LPs live at `/lp/founders-voucher/?k=lgv-aug26` and `/lp/founders-invitation/?k=lgv-aug26`; users without the token see a not-found screen, and the pages are marked `noindex,nofollow` (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`).
- **Homepage-parity form fields**: The LP forms must match the LLA homepage form’s phone placeholder/display, 50-state + DC dropdown labels, two-letter state values, and submit-time phone normalization so CRM comparisons are field-for-field (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`).
- **URL-driven campaign routing**: LP submissions retain ProductID `26`, read the current send’s `cid` from the landing-page URL, and fall back to `117648` when no valid ID is present. The parser tolerates the malformed second-`?` email-link shape, while standard `&cid=117648` links remain preferred (original session `5637bddf-a99b-43f1-b41c-351c97a1002f`).
- **AI-tell avoidance**: Promo emails and LP copy must migrate from approved Rosen/IIBS/eTeacher/French Atelier patterns rather than inventing a new structure, and must avoid AI-looking phrasing, em dashes, footnote/citation artifacts, and generic phrases like “unlock,” “elevate,” or “journey” (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`).

### See also

- `entities/longevity-life-academy`: client funnel
- `concepts/github-pages-delivery`: preview surface
- `projects/lla-pr-campaign`: campaign credibility
- `projects/lla-masterclass-emails`: lifecycle extension
- `projects/lla-employee-referral`: internal referral campaign entry


---

Record: `lla-pr-campaign` | knowledge last updated: 2026-10-15T05:34:00+00:00

## LLA PR Campaign

LLA PR Campaign is Omri’s press-release and press-kit distribution work for Longevity Life Academy/eTeacher Group, using GitHub Pages as the controlled press-kit surface and PR portals as external placements (original session `403edc06-11f9-46e4-881b-aa422bec23b2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)).

### How it works

The campaign packages three approved article angles and distributes them across owned and third-party outlets with Harel Tayeb as the public-facing CEO/media contact (original session `403edc06-11f9-46e4-881b-aa422bec23b2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)).

- **Three-angle article rotation**: The campaign separates the flagship “wealthy protocol” story, the `$8T` longevity-market business story, and the consumer “built on your numbers” story, then alternates those angles across outlets so coverage is not one repeated release (original session `403edc06-11f9-46e4-881b-aa422bec23b2`).
- **Owned press kit as control plane**: `gitteromri-ux/lla-pr-kit` holds the article pages, logos, and copy-ready press material, giving Omri a permanent GitHub Pages source even when PR portals moderate or block submissions ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/6fe3fccca554d02eacd09f21a6c28f5922a4165a)).
- **Compliance scrub for US-market positioning**: The PR kit removed Israel/Hebrew University references and replaced banned “AI micro-learning” phrasing with adaptive-learning language, while keeping Harel Tayeb as the public contact and Omri back-office only ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/6fe3fccca554d02eacd09f21a6c28f5922a4165a)) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/f13375a8ffe4b236e70e4d8c3fc03773efc63184)) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/ded574ee23e5fac1c64fca59fde31711a9f8ab28)).
- **Outlet status must be link-first**: The user rejected vague progress updates and required a reader-friendly chart with live URLs, article angle, and short coverage explanation for each outlet (original session `403edc06-11f9-46e4-881b-aa422bec23b2`).
- **Promise taxonomy for paid PR**: The campaign now separates hard guaranteed direct links from likely syndication and list-name reach before any CEO/board promise is made. That taxonomy drove the `promises.html` page and pricing ledger in `lla-pr-kit` (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `a704b693-d53d-45da-8a69-6007963f913f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/45fe370)).
- **Slide numbers as canonical IDs**: The locked submission map is Bloomberg→Slide 14, AP→Slide 9, Business Insider→Slide 11, Yahoo→Slide 2, MarketWatch→Slide 7, and USA Today→Slide 14; future work must identify articles by Omri’s deck slide numbers, not assistant-invented A-labels (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `e26c1102-615f-4caf-9487-b06bd468fbad`).
- **Five-article polishing gate**: Before vendor submission, all five articles must pass a body-prose audit, end with About eTeacher Group boilerplate, avoid banned “sixth online school” language unless it already appears in approved deck copy, and keep Julie Gibson Clark course-role details vague unless the user explicitly approves specificity (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) ([recorded evidence](https://github.com/gitteromri-ux/lla-final-5-articles)) (original session `d65c9925-abe9-4a9e-8b74-826c97a8d9fa`).
- **Checkout truth over vendor marketing pages**: PRNow package claims must be verified inside the logged-in checkout before prices, per-outlet availability, or bundle mechanics are promised to Harel/CEO-facing stakeholders. The session’s final account check contradicted earlier marketing-page-based claims about separate Yahoo/MarketWatch/Business Insider buys (original session `e26c1102-615f-4caf-9487-b06bd468fbad`).
- **Image gate before paid submission**: PR submissions should not be sent until the LLA logo, Julie image, and Harel image are present and attached where the distributor supports them; AP and USA Today being submitted without the requested images became a material execution error (original session `e26c1102-615f-4caf-9487-b06bd468fbad`) (original session `d65c9925-abe9-4a9e-8b74-826c97a8d9fa`).
- **Disclosure is a separate acceptance gate**: A guaranteed direct URL can still be unacceptable when the outlet visibly labels it paid, sponsored, partner, contributor, or third-party content. The campaign must verify the rendered page-not text extraction alone-before purchasing for a CEO-facing deck (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).
- **No silent account actions**: Retracting a release, cancelling distribution, or topping up the PRNow credit wallet requires explicit permission. Yahoo Finance was retracted and resubmitted only after direct approval to restore Harel’s featured image (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).
- **Credit purchase and package invoice are distinct records**: PRNOW showed a $399 credit top-up on 2026-07-23 and a later 149-credit Advanced-package deduction. The available $149 package invoice does not document the original $399 card purchase; account Billing and the package-invoice route did not return that credit-purchase receipt (original session `595352b8-3a75-4932-956f-68633a201347`).
- **Account identity is not a duplicate charge**: The extended reconciliation names one confirmed purchase login, `[email redacted for public handover]`, despite the account displaying Harel/eTeacher. The reported wallet arithmetic is 498 credits bought, 367 spent, and 131 remaining; package invoices document credit use rather than extra card charges. Two R6LYD3K attachment filenames share a release identifier, not proven identical contents (original session `595352b8-3a75-4932-956f-68633a201347`).
- **Zero-label alternatives trade prestige for price**: The researched clean-page options ranged from small outlets around `$85–$500` to Grit Daily/IBTimes around `$800–$1,600`; recognizable large-logo placement with a clean page was not found below roughly `$2,000` (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).

### Key surfaces

- Press kit repo: `gitteromri-ux/lla-pr-kit` ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit))
- Press kit site: `https://gitteromri-ux.github.io/lla-pr-kit/` (original session `403edc06-11f9-46e4-881b-aa422bec23b2`)
- Outlet-promises/pricing page: `https://gitteromri-ux.github.io/lla-pr-kit/promises.html` (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/45fe370))
- Final five article mockups: `https://gitteromri-ux.github.io/lla-final-5-articles/` ([recorded evidence](https://github.com/gitteromri-ux/lla-final-5-articles))
- PR coverage deck: `https://gitteromri-ux.github.io/lla-chapter1-pr-coverage/` ([recorded evidence](https://github.com/gitteromri-ux/lla-chapter1-pr-coverage))
- Live/queued outlet set from the campaign session included PR.com, PRUrgent, PRFree, PRLog, IssueWire, 1888PressRelease, EIN Presswire, and MarketPressRelease (original session `403edc06-11f9-46e4-881b-aa422bec23b2`).

### See also

- `entities/longevity-life-academy`: client surface
- `entities/harel-tayeb`: public media contact
- `entities/omri-gitter`: back-office operator
- `concepts/github-pages-delivery`: owned delivery surface
- `concepts/pr-placement-guarantees`: promise taxonomy
- `projects/lla-ad-banner-campaign`: campaign deck chapters


---

Record: `lla-master-delivery-hub` | knowledge last updated: 2026-10-15T05:34:00+00:00

## LLA Master Delivery Hub

LLA Master Delivery Hub is the public `longevity-assets` GitHub Pages surface that consolidates Longevity Life Academy films, ecommerce, banners, PR coverage, and strategy materials into one client-facing handoff (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)).

### How it works

The hub embeds or links the Julie and Courtney film releases, Growth Engine, promo funnel, checkout status, banner galleries, PR coverage, and strategy decks in business-review order (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)).

- **Neutral client-facing identity**: The final surface uses `longevity-assets` instead of `lla-ceo-delivery` so the URL does not expose an internal audience label (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`).
- **One-link executive handoff**: The hub replaces a scattered set of project URLs with one public page while preserving the specialist repositories as source surfaces (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)).
- **Film version lines remain independent**: The explicit public 90-second handoff pairs Julie V24 with Courtney v18; every surface must label talent and version together rather than imply their numbers are comparable (original session `f573e739-cd35-4b06-a95b-417ae188a9d5`) ([recorded evidence](https://github.com/gitteromri-ux/lla-90s-final/releases/tag/v90s)).
- **Live media needs browser-safe packaging**: Film assets use inline playback, mobile hardening, and faststart; GitHub Actions provides the dependable render/upload route when direct release uploads fail (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)).
- **Hub and final-film surfaces have different roles**: `longevity-assets` remains the broad executive hub, while `lla-90s-final` is the narrowly authorized Julie V24/Courtney v18 film handoff and `lla-ceo-delivery` redirects into the hub ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets)) (original session `f573e739-cd35-4b06-a95b-417ae188a9d5`) ([recorded evidence](https://github.com/gitteromri-ux/lla-90s-final/releases/tag/v90s)).

### Key surfaces

- Hub repo: `https://github.com/gitteromri-ux/longevity-assets` ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets))
- Public hub: `https://gitteromri-ux.github.io/longevity-assets/` (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`)
- Redirect repo: `https://github.com/gitteromri-ux/lla-ceo-delivery` ([recorded evidence](https://github.com/gitteromri-ux/longevity-assets))
- Final-film page: `https://gitteromri-ux.github.io/lla-90s-final/` (original session `f573e739-cd35-4b06-a95b-417ae188a9d5`)

### See also

- `projects/lla-growth-engine`: ecommerce system
- `projects/lla-julie-masterclass-video`: Julie film releases
- `projects/lla-s09-s10-video-delivery`: Courtney film releases
- `entities/longevity-life-academy`: client surface
- `projects/lla-handoff-pack`: technical transfer surface


---

Record: `direct-ecommerce-school-pilot` | knowledge last updated: 2026-10-15T05:34:00+00:00

## Direct Ecommerce School Pilot

Direct Ecommerce School Pilot is Omri’s planning discussion for an unnamed new school’s $1,200 direct-checkout offer, with $10,000 over two weeks and no call-center path. French Atelier’s lead-generation campaign is a comparator in the brief, not the stated identity of the new school (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`).

### How it works

The pilot is ecommerce-only and starts without historical buyer data. The business KPI is paid purchase, while expected volume is below seven purchases, making the campaign optimization event the central unresolved decision (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`).

The $1,200 school test is a separate endeavor from Omri’s Culture Capsules website and its ten-day media proposal; capsule pricing, forecast, and staging status do not replace this pilot’s stated constraints (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`) (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`).

- **Fixed constraints before campaign architecture**: The price, 14-day duration, $10,000 budget, direct-checkout path, absent buyer history, and low expected purchase count must remain fixed when evaluating options (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`).
- **No approved Meta architecture yet**: Purchase, Traffic/LPV, Initiate Checkout, Leads, and split-campaign recommendations were all raised and rejected; none is an accepted project decision (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`).
- **Proxy-event risk is material**: Sparse purchase volume limits learning, while higher-volume proxy events risk optimizing toward page loaders, checkout abandoners, or form-fillers instead of buyers (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`).

### See also

- `entities/gita-agency`: acquisition owner
- `projects/french-atelier-culture-capsules`: distinct culture-learning product


---

Record: `lla-ugc-video-ads` | knowledge last updated: 2026-09-24T11:23:00+00:00

## LLA UGC Video Ads

LLA UGC Video Ads is the branded testimonial-style production system for short presenter-led Longevity Blueprint ads. Each film combines an established LLA opener and closer with one continuous presenter take and source-faithful course messaging (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).

### How it works

The initial brief calls for two 45-second films-one woman and one man in their 40s-using the approved Courtney/Julie opener and Courtney closing sequence around roughly 30 seconds of presenter speech (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).

- **Authenticity is the primary acceptance gate**: The presenter must look and sound natural, stay visually continuous across the full monologue, and recommend the Academy without cynical performance or invented personal results. Captions, music, or transitions cannot rescue rejected presenter footage (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).
- **Course claims stay grounded**: Scripts center the six pillars, a protocol tailored to the learner’s biology and biomarkers, 18 live online sessions over 18 weeks, leading longevity faculty, practical habits, and healthspan rather than unsupported testimonial outcomes (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).
- **Brand framing reuses approved film assets**: The opener and closer come directly from the final Courtney or Julie videos, with seamless joins and no overlapping faces or discontinuous presenter identity (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).
- **Generation fallback does not lower the quality bar**: Higgsfield’s preferred models were blocked by a plan restriction, so Artlist generated the first presenter footage. The user rejected its naturalness and continuity; replacement footage remained required rather than treating a cosmetic edit as final (original session `6bd41a15-276c-4caf-a759-be7a6d39ae94`).

### See also

- `projects/lla-s09-s10-video-delivery`: Courtney source package
- `projects/lla-julie-masterclass-video`: Julie branded film
- `concepts/video-quality-qa`: release acceptance standard
- `entities/longevity-life-academy`: campaign owner


---

Record: `lla-funnel-performance-deck` | knowledge last updated: 2026-09-23T06:45:00+00:00

## LLA Funnel Performance Deck

LLA Funnel Performance Deck is the public review of Longevity Life Academy’s direct-ecommerce campaign performance. It measures the path from impressions to landing-page views, checkout actions, and purchases; compares ad sets and age bands on spend-normalized efficiency; and connects observed results to explicit media decisions (original session `87b45a62-5f06-4086-897f-c60ad76faf52`) ([recorded evidence](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14)) (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`).

### How it works

The deck consolidates daily Meta delivery, funnel depth, audience segmentation, creative concentration, and return scenarios into a browser-ready operating surface. Its reviewed window now extends through 2026-09-15, with daily and age-band views added to the campaign-level totals (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`) ([recorded evidence](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14/commit/fbbbce7)) ([recorded evidence](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14/commit/b4b0ef8)).

- **Landing-page views remain the stable media denominator**: Spend, impressions, clicks, landing-page views, checkout events, and purchases are kept as separate stages so traffic efficiency is not confused with on-site conversion (original session `87b45a62-5f06-4086-897f-c60ad76faf52`) (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`).
- **Normalize unequal budgets before comparing performance**: Reach, impressions, clicks, and landing-page views are compared per dollar because raw totals otherwise overstate the larger budget’s advantage (original session `87b45a62-5f06-4086-897f-c60ad76faf52`).
- **Age bands require downstream evidence**: The age view compares spend and landing-page efficiency with AddToCart and purchase behavior; high-spend segments with no downstream action can be capped while converting segments retain room (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`) (original session `5608d58e-c5f5-447c-9bac-d0dd37c3cd5e`).
- **Creative concentration is visible**: The report identifies when one Julie video carries most useful delivery, making a close variant and broader creative testing more defensible than indiscriminate spend increases (original session `87b45a62-5f06-4086-897f-c60ad76faf52`) (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`).
- **Campaign edits require delivery-state verification**: An ad-set edit can leave child ads paused even when targeting values are correct, so the measurement workflow checks both configuration and actual delivery state (original session `5608d58e-c5f5-447c-9bac-d0dd37c3cd5e`).
- **Public GitHub Pages handoff**: The maintained source publishes an anonymous, no-login decision deck from the funnel-analysis repository ([recorded evidence](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14)).
- **Attributed totals are not automatically net customers**: Production QA can contaminate Meta reporting, and view-through activity cannot be reassigned to another ad set without event-level evidence. The deck must label verified tests, verified customer actions, and unresolved events separately rather than using gross ATC totals as commercial proof (original session `a43dd532-6960-481c-a712-882a6081a8e5`) (original session `23822628-c1d7-4345-acf3-6b6e6c078cb9`).
- **Delivery, matching, and attribution require separate evidence**: A website event reaching CAPI and appearing in Meta Test Events proves transport, not credit to a specific campaign or ad set. Ad-set recovery requires a qualifying ad interaction and the resulting conversion in that ad set’s report (original session `653edf1a-2b37-4695-ac45-302de528ddef`).

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/lla-funnel-analysis-sep14` ([recorded evidence](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14))

### See also

- `projects/lla-course-checkout`: measured transaction funnel
- `projects/lla-julie-masterclass`: parallel ecommerce offer
- `projects/lla-growth-engine`: recovery and remarketing
- `entities/longevity-life-academy`: client and campaign


---

Record: `french-atelier-social-kickstart` | knowledge last updated: 2026-09-23T06:45:00+00:00

## French Atelier Organic Social Kickstart

French Atelier Organic Social Kickstart is the September–October 2026 organic-social plan and browser-ready deck for the French Atelier account ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart)).

### How it works

The project packages the social calendar, raw organic-video library, email ideas, real-time marketing opportunities, and a dedicated slide view in one GitHub-hosted delivery surface ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/b3a55a8786)) (original session `d805b6d0-524a-41f9-a2ac-51ac493d688f`).

- **Separate campaign surface**: The organic-social plan lives in `gitteromri-ux/french-atelier-social-kickstart`, separate from the production website repository, so campaign planning cannot destabilize the live site ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart)).
- **Deck and calendar share one source**: The repository includes both the full plan/calendar and `deck.html`; null-guarded injectors keep the slide view rendering when optional content is absent ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/b3a55a8786)).
- **Brand punctuation is enforced in the source**: An audit commit removes em dashes from the campaign surface rather than leaving manual cleanup to presentation time ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/3750793311)).
- **Raw source media is the authority**: The deck uses the original uploaded Drive videos, excludes paid spokesperson and burned-overlay variants, and organizes 26 unique clips across five organic formats without duplication (original session `d805b6d0-524a-41f9-a2ac-51ac493d688f`).
- **Portrait video keeps its native composition**: Philippe and Charline clips use 9:16 framing and click-to-load posters so faces and bodies remain naturally positioned in presentation mockups (original session `d805b6d0-524a-41f9-a2ac-51ac493d688f`).
- **Calendar dates are computed, not assumed**: A full audit corrected the September–October Monday/Wednesday/Friday dates, monthly counts, and specific poster pairings while preserving the 23-post cadence (original session `d805b6d0-524a-41f9-a2ac-51ac493d688f`).
- **The deck behaves like a client-facing media surface**: Email ideas render as real inbox-style creative, Culture Capsules use syllabus-grounded topics, the Mapstr module is interactive, and only the active slide loads video, protecting mobile performance (original session `c987ea76-2449-449d-8e18-3f4ecc5a5510`).
- **Social exports are delivery assets, not deck-only previews**: The repository carries 32 Instagram-compliant video transcodes and 32 portrait posters for the 33-post publishing system ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/24aef6a0b33cfede0067e759edc422f604641afc)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/901b235)).
- **Source-faithful compression is mandatory**: Presentation shortening preserves the approved concepts, real emails, real syllabus topics, and source media rather than replacing them with invented summaries (original session `c987ea76-2449-449d-8e18-3f4ecc5a5510`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/f47c0c8)).
- **Publishing uses one authoritative 33-topic checklist**: An asset existing or playing is not enough. A delivery counts only when the topic, exact source media, approved copy, link, channel, Israel-local schedule, and saved record all match and the scheduled post is reopened successfully (original session `e8f5f9c1-bcbf-4c9c-82df-68cc1a03c4de`).
- **Missing source media blocks substitution**: Twenty-one topics were reported scheduled on both Instagram and Facebook, while twelve remained blocked because ten exact videos were not found and two homophone sets were unverified. Wrong-topic uploads are not accepted as completion (original session `e8f5f9c1-bcbf-4c9c-82df-68cc1a03c4de`).
- **Comment-to-DM is a tested capability, not a label**: No working public-comment-to-private-message rule was created. Saved replies and ordinary inbox rules do not satisfy the requirement (original session `e8f5f9c1-bcbf-4c9c-82df-68cc1a03c4de`).

### See also

- `projects/french-atelier-website`: production website surface
- `projects/french-atelier-performance-diagnosis`: performance reporting surface
- `entities/gita-agency`: delivery agency


---

Record: `lla-privacy-policy` | knowledge last updated: 2026-09-16T12:10:00+00:00

## LLA Privacy Policy

LLA Privacy Policy is the maintained legal-information surface for Longevity Life Academy’s web and checkout ecosystem, including explicit treatment of health and wellness data (original session `81158e72-b547-461a-b594-762d9a5c7a5f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-privacy-policy)).

### How it works

The project preserves the existing policy baseline while extending it for information collected through longevity education, assessments, lead forms, and ecommerce interactions (original session `81158e72-b547-461a-b594-762d9a5c7a5f`).

- **Health and wellness data is named explicitly**: The policy treats assessment and longevity-related information as a distinct data category rather than hiding it inside generic form-data language (original session `81158e72-b547-461a-b594-762d9a5c7a5f`).
- **Original legal text remains intact**: New language is additive and source-faithful so the policy does not silently replace previously approved obligations (original session `81158e72-b547-461a-b594-762d9a5c7a5f`).
- **One policy supports multiple LLA surfaces**: The maintained repository provides the legal baseline that checkout and campaign pages can link to instead of carrying divergent copies (original session `81158e72-b547-461a-b594-762d9a5c7a5f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-privacy-policy)).
- **Legal review remains a release gate for substantive claims**: Collection purpose, sensitive-data wording, retention, sharing, and jurisdictional scope require confirmation before policy language is treated as final legal advice (original session `81158e72-b547-461a-b594-762d9a5c7a5f`).

### See also

- `entities/longevity-life-academy`: policy owner
- `projects/lla-course-checkout`: ecommerce collection surface


---

Record: `abraham-tlv-gm-plan` | knowledge last updated: 2026-09-16T12:10:00+00:00

## Abraham Tel Aviv GM Plan

Abraham Tel Aviv GM Plan is a Hebrew, CEO-facing operating plan for the hostel’s general-manager agenda, delivered as a public browser-ready deck and maintained in `gitteromri-ux/abraham-tlv-gm` (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`) (original session `44859035-df25-47a4-bd36-f12b628efdb6`) ([recorded evidence](https://github.com/gitteromri-ux/abraham-tlv-gm/commit/57446de352e3b8e549b1801426b8dda176cd0460)).

### How it works

