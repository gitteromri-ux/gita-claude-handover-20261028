Historical business mapping: eTeacher Group business `1545475089051742`; French ecommerce dataset/pixel `4075596186030950`, NOT the separate “FA” dataset `4400286150281912`; LLA pixel `1440305917310328`. Do not cross-wire brands or infer business ownership from a similar display name. [French account/pixel inventory](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-ecommerce-handover-2026-10-20.md), [LLA inventory](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/HANDOVER-JULIE-BLUEPRINT-20260930.md)

### Campaign registry: known exact identifiers versus unresolved fields

| Product/campaign | Meta campaign ID | Exact name / recovered campaign label | Last evidence; current status |
|---|---|---|---|
| Julie masterclass | `52668266203628` | `LGV_EN_PPC_ecomm-02_2026-09-02_#118149` | Exact name/ID in historical JSON; October 27 original report confirms activity in its sets. Current campaign status unknown. [Campaign JSON](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/campaigns.json), October 27 (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`) |
| Blueprint | `52663511211628` | `LGV_EN_PPC_ecomm-01_2026-09-02_#118148` | Exact name/ID recovered. Historical campaign ACTIVE is not restart permission or current state. [Campaign JSON](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/campaigns.json) |
| Capsules EN | Full Meta campaign ID not recovered | CRM campaign `#116980`; report display label `EN · CA 50+` | One main buyer-acquisition set `#108761`. Full canonical Meta campaign name unavailable, so the shortened report label is NOT represented as an exact name. Original launch (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`), October 26 report (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) |
| Capsules FR | Full Meta campaign ID not recovered | CRM campaign `#116939`; report display label `FR · US 50+` | Sets `#108758`, `#108757`, excluded `#108756`. Full canonical name unavailable. Original configuration (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`), October 26 report (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) |

**CRM suffixes are not Meta IDs.** Never pass `116980`, `116939`, `108761`, etc. as Graph entity IDs merely because the interface shows a hash label. Reconnect and list the v2 campaigns to recover canonical names and numeric Meta IDs before any subsequent operation.

Historical campaign API timestamps: Julie created `2026-09-24T06:03:57+0000`, updated `2026-09-27T20:00:24+0000`; Blueprint created `2026-09-03T06:13:16+0000`, updated `2026-09-16T08:00:31+0000`. Both snapshot objectives were `OUTCOME_SALES`; neither selected campaign record supplies a campaign-level daily budget. These timestamps are source-object values, NOT fresh verification timestamps. [Campaign JSON](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/campaigns.json)

### Last evidenced configurations: USD, not today's verified state

#### Capsules

| Role / CRM suffix | Meta ad-set ID | Last dated daily budget | Last reported state |
|---|---|---:|---|
| Buyers LLA / `#108761` | `120251212250640546` | USD 149 | ACTIVE, October 26 |
| Francophile / `#108758` | `120251212251230546` | USD 79 | ACTIVE, October 26 |
| Leads LLA / `#108757` | `120251212251670546` | USD 169 | ACTIVE, October 26 |
| Excluded `#108756` | Not recovered | Not current-verified | Left paused in launch record |

The numeric IDs come from original Ads Manager links; the USD 397/day total is the later October 26 configuration, superseding launch USD 169/159/149. These are ad-set budgets, not campaign budgets or enforced spending ceilings; exact current Meta ad-set names and `updated_time` fields remain unavailable. Original launch with IDs (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`), October 26 budget/state report (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

The October 22 launch was reported verified at 14:04 IDT: both campaigns, three sets and 17 selected ads ACTIVE/effectively ACTIVE; five main ads, six Francophile and six lead-lookalike ads, with older ads and excluded set left paused. It is a launch receipt, not today's inventory. Original launch session (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

#### Julie: applied versus requested, October 27

| Exact recovered ad-set name | Meta ID | Last evidenced USD/day | Last evidenced status |
|---|---|---:|---|
| `ecomm_Adset_01_All_All_CPM_#108813` | `52668330533628` | 258 | ACTIVE before latest access failure |
| `ecomm_Adset_02_All_All_CPM_#108814` | `52673824399628` | 564 | ACTIVE before latest access failure |
| `ecomm_Adset_03_All_All_CPM_#108815` | `52668330165828` | 77 retained | PAUSED, reported verified October 27 |
| `ecomm_Adset_04_All_All_CPM_#108816` | `52668330870828` | 999 | ACTIVE before latest access failure |
| `ecomm_Adset_05_All_All_CPM_#108817` | `52668330871228` | 348 | ACTIVE before latest access failure |
| `ecomm_Adset6_0_All_All_CPM_#108818` | `52668330871028` | Not latest-verified | PAUSED |

Names/older IDs are recovered from the historical snapshot; replacement Set 02 name and ID are confirmed in the October 18 original session. Budgets and October 27 status distinctions come from the later original reporting, not the September budget values. [Historical set registry](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/adsets_52668266203628.json), Replacement Set 02 (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`), October 27 changes (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

At 04:24 UTC October 27, Omri requested Set 04 +150, Set 02 −50, Set 03 pause and an ambiguous Set 05 increment. The assistant reported only Set 03 successfully paused; Set 04 remained 999 rather than requested 1,149; Set 02 remained 564 rather than requested 514; Set 05 remained 348. At 05:26 UTC, the original session still said the budget changes were unapplied because fallback access was blocked. Active configured budgets after that reported pause sum to USD 2,169, NOT 2,246 and NOT a subsequently verified campaign-wide pause. Original instructions and outcome (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

**Identity trap:** retired Set 02 `52668268711228` is not replacement live Set 02 `52673824399628`, despite the same CRM suffix/name pattern. Never select by name alone. Replacement set source (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

#### Blueprint historical registry: explicitly September, not current

| Exact snapshot ad-set name | Meta ID | Snapshot USD/day | Snapshot status / updated UTC |
|---|---|---:|---|
| `ecomm Adset 2_All_All_CPM_#108808` (copy) | `52669013718628` | 199 | ACTIVE; 2026-09-29 23:06:21 |
| `ecomm Adset 4_All_All_CPM_#108810` | `52666232368428` | 50 | ACTIVE; 2026-09-29 23:06:02 |
| `ecomm Adset 5_All_All_CPM_#108811` (copy) | `52669048300628` | 155 | ACTIVE; 2026-09-29 23:05:36 |
| `ecomm Adset 2_All_All_CPM_#108808` (original) | `52663512093428` | 160 | PAUSED; 2026-09-28 15:06:14 |
| `ecomm Adset 5_All_All_CPM_#108811` (original) | `52666296222628` | 40 | PAUSED; 2026-09-28 15:06:15 |
| `ecomm Adset 3_All_All_CPM_#108809` | `52664534627228` | 100 | PAUSED; 2026-09-16 19:21:11 |
| `ecomm Adset 1_All_All_CPM_#108807` | `52663511359228` | 1 | PAUSED; 2026-09-16 19:21:12 |

All values above are historical cents converted to USD, from the September 30 archived JSON. Later October reporting mentioned small spend in Blueprint sets but does not establish maintained budgets or today's delivery state. [Blueprint set JSON](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/adsets_52663511211628.json), October original reporting (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### October activity, decisions and rejected paths

- **October 18 Julie warm/lookalike launch:** replacement Set 02 launched at USD 99/day with four selected exact-source ads and fifteen paused copies; US 44–65+, Facebook Feed/Reels, Purchase optimization, lowest cost. Audience membership was purchaser 1% lookalike **OR** Julie checkout 30-day/cart 14-day warm pool, not an intersection or separated budgets. The too-small warning concerned the warm pool, not the ready purchaser lookalike. Ordinary page visitors were not included; the cart rule required Julie page plus campaign ID. Original October 18 session (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **October 20 seed enrichment:** 101 initial distinct identities became 122 from 131 paid-order records; additions accepted is not platform matched-user count or settlement certification. Existing seed `52673824207628`, existing lookalike `52673827176428`; the original “101” label was deliberately retained. Approval attached the lookalike to paused Set 03 only; Set 06 was explicitly excluded. Processing/updating and lookalike readiness were distinct. Original October 20 session (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- **French purchaser integrity:** the reported 232 submitted identities came from an expanded 645-student population, not a rigorously established set of 232 paid/noncancelled buyers. Initial filtered population was 410; unrelated eTeacher buyer padding was rejected. Submission accepted/zero invalid is not proof of paid eligibility, accurate identity resolution or final Meta matching. Historical seed `120251221224670546`, purchaser 1% `120251221226160546`; no seed contents retrieved in this task. Original purchaser investigation (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **October 22 audience decisions:** keep verified purchaser 1% only rather than create a fresh 1–2% band. Two website-visitor 2%/1–2% audiences in the other FA account had failed creation and were not purchaser/checkout audiences. Checkout audience creation returned error 2663, Custom Audience terms not accepted. “Emily in Paris,” “Call My Agent” and French-TV interests were not verified selectable; irrelevant Lupin results were rejected. Original October 22 session (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **French warm versus lookalikes:** a warm-nonbuyer third-set proposal was superseded; the launched third role is lead-lookalike **prospecting**, not actual-lead retargeting. Purchaser/lead sources, exclusions, Advantage+ settings and income/device differences were set-specific. Reporting names such as “CA 50+” are not reliable proof of geography: the detailed approved configuration described US nationwide. Do not infer targeting from old names. Original configuration/launch (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Rejected test path:** October 22 at 22:42 UTC, Omri explicitly rejected the Israel-targeted test approach; the assistant reported the Israel test set paused and never delivered. An earlier test launch approval did not survive this later rejection. Do not recreate it or fire synthetic production Purchases. Original rejection (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Learning is not a forecast:** October 26 reporting distinguishes Set 04 exited learning, Set 05 learning-limited and Sets 01/02/03 learning. Earlier explanations equating edits to universal resets, a guaranteed ten-day exit, or a fixed CPP after learning were challenged/withdrawn; a status field is not causal proof or a countdown. October monitoring (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`), Original learning/transition debate (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Blueprint transition intent:** October 24 discussion favored reusing Julie Set 04 with identical targeting but Blueprint destination/copy and masterclass ads stopped after the event. The assistant proposed incremental additions and a one-hour significant-edit check; this was not an executed migration or proof replacing every ad preserves learning. Today's restart intent adds no activation authorization in this read-only task. Original transition discussion (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Monitoring versus campaigns:** the Capsules hourly reader `9e4332aa-87fb-4950-a05e-c8c3b2da922b` was paused on the stop instruction; the original October 27 message explicitly says no account settings changed and Julie's separate schedules remained scheduled but access-blocked. A paused reporter is not a paused campaign; stale NO DATA is not zero sales. Original stop instruction/result (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Attribution integrity and ecommerce boundaries

Julie new Set 02's name ends in `#108814`, but copied ads retained static source `adGroupID` values `108813`, `108815`, `108817`; the recovered session ends at a request for approval to repair URL mapping, not a completed repair. A rename cannot establish CRM attribution alignment. Original launch/tag discussion (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

Keep separate: paid CRM orders, unique buyers, raw browser/server receipts, deduplicated events, Meta-attributed purchases, recorded last clicks and processor settlement/refunds. October 26 four paid orders totaled USD 226 while eight raw Purchase receipts included browser/server copies; matching four-count Meta/CRM summaries do not themselves reconcile individual orders or certify settlement. Original October 26 reporting (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

Golden Julie attribution preserves pixel `1440305917310328`, exact-case click ID/fbc, fbp, stable event ID (Purchase = CRM order ID), browser/server equality, campaign `cid=118149`, set tags and paid-success triggers. French uses its own pixel and brand fields. Accepted PageView/ViewContent or checkout events do not certify paid Purchase attribution, deduplication, complete enrollment or processor settlement; the original test response's broader inference must not be repeated as proof. [Golden tracking contract](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md), Original test and checkout discussion (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)


French Meta reporting attributed USD 79 on October 24 to Buyers `#108761` and USD 151 on October 25 to Leads `#108757`, not Francophile. Paid-bundle entitlement and website checkout incidents remain separate reconciliation work, not evidence those Meta credits are settled or fully fulfilled. October report (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Exact safe connection/read runbook for the next operator

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

