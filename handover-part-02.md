The exact approved launch time lines are “Tuesday, October 27: 7:00 PM ET / 6:00 PM CT / 5:00 PM MT / 4:00 PM PT” and “Saturday, November 14: 1:00 PM ET / 12:00 PM CT / 11:00 AM MT / 10:00 AM PT”; the October 18 instruction uses “14-day refund*” with “*14 days from registration or until your class starts, whichever is later.” These are dated launch instructions, not permission to overwrite a newer refund policy without approval. Original Chris instruction (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

#### Read-only installed-email audit runbook

1. Establish AC account identity and successful read access before calling any installed sequence verified.
2. Export/read each actual automation/campaign's ID, name, status, entry trigger, exclusions, wait conditions, schedule/time zone and message IDs; retain snapshots privately.
3. For each of Regular and VIP, inspect all three abandoned-stage families, onboarding, JM-U1–U4 and JM-X1–X4, comparing actual HTML and plain text against the dated approved source.
4. Resolve each tracked destination without submitting forms; record final host/path, retained UTMs, coupon, package and recovery identity. A generic pricing destination does not pass an order-resume requirement.
5. Verify session-date, Zoom and LMS substitutions against Chris's supplied values; verify November reminders and final-session no-show routing.
6. Independently read send history and campaign reports; distinguish scheduled, active, delivered and failed. Require actual send-event evidence before writing “sent.”
7. Produce a diff for approval; do not import, create fields, activate automations or send test emails during a read-only audit.

This runbook operationalizes the original Chris import-confirmation requirement and Sandra governance boundaries; it was not executed against live AC because the read-only connector failed. Chris handoff (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) [Governance/access record](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)

### AC access and CRM deal-pulling runbook

#### Known account and supported routes

The documented AC API host is `eteachergroup.api-us1.com` with header name `Api-Token`; no header value belongs in this handover. Original evidence: session short ID `5f70d990`, October 25 05:59–06:00 UTC, local transcript lines 7323–7365.

Three access states must remain separate: the currently broken Pipedream connector; the October 9 successful browser/header read route; and the October 18 purchaser audit's project-specific saved-access route, which worked even when a generic Vercel connection did not expose the project. [October 9 access record](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md) October 18 original purchaser audit (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

The October 25 assistant attributed Invalid URL to missing account URL configuration, but the fresh October 28 error establishes only the failure, not its root cause; inspect the connector's nonsecret account-host configuration before asserting a cause. Original source: `5f70d990`, October 25 05:52 UTC; current source: AC list-campaigns error.

#### Retrieval and reconciliation procedure

1. **Read authorization only:** use an already approved AC credential route or restore connector host configuration through the authorized owner; never paste keys into email, this file, public repositories or customer exports.
2. **Define cutoff:** record timezone and inclusive/exclusive timestamps for September 28–October 28, or the specifically requested event/report interval. Do not infer the date from local folder names.
3. **Enumerate deals deterministically:** use the available read API's pagination and a stable ordering; retain raw deal IDs and page/cursor bookkeeping privately, deduplicate by deal ID, and reconcile total counts against the response's total. Do not assume a first page or duplicate-heavy response is complete.
4. **Read the field model:** identify fields by their returned metadata and IDs rather than inventing filter keys; the October 10 register documented IDs `206/216/217/223/224` but did not provide a complete validated semantic map. [Field-model gap](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)
5. **Qualify orders:** require won/paid status plus product/campaign evidence; retain separate categories for internal/test, unpaid, payment-sync exception and unresolved. Read order ID, amount/currency, creation/paid timestamps and contact relationship; do not equate every account-wide deal with Julie.
6. **Attach attribution:** resolve contact field `187` (“Ad ID”), then read that ad's current Meta ad-set mapping; if only a saved mapping exists, label the mapping snapshot's timestamp. Original method: `5f70d990`, October 25 05:59–06:00 UTC.
7. **Keep orders distinct:** count separate paid order IDs as orders; deduplicate people by normalized identity only for a unique-buyer metric, never to erase repeat orders from sales.
8. **Compute CRM CPA separately:** ad-set spend divided by CRM-attributed paid-order count; show Meta-attributed Purchase count alongside, using consistent date windows/time zones and documenting mismatches.
9. **Keep money truth separate:** join processor settlement/refunds only when those records are actually available; AC “won” is not settlement certification.
10. **Output privacy:** aggregate counts, excluded-category counts, timestamps and reconciliation checks; keep customer rows outside this handover.

Pagination, deal-ID deduplication, candidate reconciliation and unique-buyer separation are supported by the October 18 original purchaser audit; no exact undocumented AC REST query/filter syntax is invented here. Purchaser audit (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

### Masterclass backend, enrollment and callback boundaries

#### Backend topology and IDs

- Julie production page: `https://www.longevitylifeacademy.com/julie-masterclass/`, GitHub Pages source `Longevity-Academy/julie-masterclass`, branch `main`; a push to that branch is a deployment, not a harmless documentation operation. [October 9 technical handover](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)
- Earlier personal mirror: `gitteromri-ux/lla-julie-masterclass`; do not assume current lockstep parity merely because the August record described it. [Historical masterclass source map](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-live-masterclass.md)
- Order integration: Cloudflare Worker `eteacher-leads-proxy`; card payment through Airwallex Drop-In and PayPal through a separate eTeacher PayPal path. [October 9 technical handover](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)
- Historical Julie CRM mapping: `MainAbroadCourseId=283`, `AbroadCourseId=1823`, `CampusId=4203`, `LanguageId=101`; these values come from the earlier implementation handover and must be read back before a new enrollment change. [Historical mapping](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-live-masterclass.md)
- Blueprint is a distinct product/site: private `gitteromri-ux/lla-course-checkout`, Pages.dev, historical `ProductID=26`, `MainAbroadCourseId=258`, `AbroadCourseId=1774`, `PreferredCourseId=-1`, `LanguageId=101`; do not copy Julie IDs into Blueprint. [Checkout source](https://github.com/gitteromri-ux/lla-course-checkout)
- November Blueprint mapping: semester `2395`, class `170275` on November 23 at 8 PM EST/5 PM PST, class `170277` November 25 at noon EST/9 AM PST. [November mapping commit](https://github.com/gitteromri-ux/lla-course-checkout/commit/1eb51fef8d87c807986880f455ad6e27f176d929)

#### Checkout, AC event and payment sequence

The approved abandonment integration writes only `LGV_checkout_events`, field `206`, to existing AC contacts; it is not authorized to create new contacts, lists or fields. Regular/VIP segmentation uses `LGV_Product_Event` values `Regular` and `VIP`, while the session-date token is shared. [Historical backend](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-live-masterclass.md) Original package audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

Blueprint's narrow route is `POST /api/ac/event`; order creation uses `AddNewECommerceLeadAndOrder`, payment details use `GetECommerceFirstPaymentDetails`, and PayPal approval is reported through `SetECommercePayment`; read and payment calls must stay in the same environment as order creation. [Maintained checkout source](https://github.com/gitteromri-ux/lla-course-checkout)

Opening a page must not create a CRM order; valid Stage 1 continuation creates the lead/order, and async provisioning can briefly return `OrderId=-1`, requiring a controlled details retry rather than blind duplicate order creation. [No-write-on-visit change](https://github.com/gitteromri-ux/lla-course-checkout/commit/00f3bf9f21b7c6162d2815a0409ce7d1bc048c98) [Checkout hardening](https://github.com/gitteromri-ux/lla-course-checkout/commit/dc1dce2ee5)

The October 27 attendee audit established that `NumberOfPayments` means **remaining** installments: first payment 149 plus `NumberOfPayments=4` and `LeftToPay=596` yields five total payments, whereas 5 yields six total payments. That historical 149 schedule is superseded commercially by the later 79/169 approval, but the installment-field semantics remain a critical implementation check. Original local source: `memory/notes/projects/web_checkout/lla_guest_page_audit_20261027.md`. Attendee audit session (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

#### Enrollment is not a callback

The attendee page's lower-page question/contact/consent form is a sales-callback path, separate from paid enrollment; the reference WhatsApp entry is `https://wa.me/12015023701`. Attendee original session (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

Nine final mocked-backend validation/response cases passed, and an earlier staging submission reached a queue, but final production CRM persistence, sales callback receipt, completed payment, enrollment and Meta Purchase were not established by those checks. Original attendee audit (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

The sandbox returned `provider_unavailable` on both the attendee flow and unchanged Pages.dev reference; production card fields loaded without a real charge. This does not prove production payment failure and must not trigger a needless checkout rebuild. Original attendee audit (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

#### Read-only backend acceptance runbook

1. Inspect maintained source plus actual deployed-version metadata; distinguish old mirror, protected golden tag and current production.
2. Record selected product/course/class/payment-plan IDs and their environment before evaluating price.
3. Check no-write-on-visit and form validation through source/existing logs; do not submit production test leads in a read-only task.
4. For an existing paid order, trace the same StudentId/OrderId through order creation, CRM payment details, processor success, CRM status, class enrollment, AC event update and access delivery.
5. For callback requests, independently trace submission acknowledgment → queue → persistent CRM record → assigned sales owner → callback disposition; a mocked HTTP success is not sufficient.
6. For bundled enrollment, require a linked second registration/read-back rather than inferring entitlement from a coupon or email promise.
7. Record unknowns separately: physical-device behavior, payment completion, enrollment completion, LMS/Zoom access, AC import, email delivery and attribution.

### Golden CAPI, relay rules and deduplication

#### Protected identifiers and files

| Object | Exact historical identifier |
|---|---|
| Ad account | `act_1459085242361281` |
| Julie campaign | `52668266203628`, `LGV_EN_PPC_ecomm-02_2026-09-02_#118149` |
| Dataset/pixel | `1440305917310328` |
| Purchase custom conversion | `1426010666308623` |
| InitiateCheckout custom conversion | `1099790382424644` |
| AddToCart custom conversion | `1417373073897207` |
| Relay | `https://lla-ac-events.vercel.app/api/meta/capi` |
| Vercel project | `lla-ac-events`, `prj_3v7g4Xwve6OmXrcPCVQOWJOiN2SK` |
| Golden deployment | `dpl_DQogoRsNj1XXTpJQmFrRk9zzCCrU` |
| Guard | `projects/julie-tracking-freeze/verify_julie_tracking.py` in `gitteromri-ux/handover-master` |
| Golden configuration | `projects/julie-tracking-freeze/golden.json` |

All identifiers in this table are from the dated golden record, not current account/deployment read-back. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

Protected page files include `index.html`, `assets/julie-meta-tracking.js`, `assets/julie-attribution.js`, `assets/julie-payment-safety.js`, `assets/julie-international-checkout.js` and `assets/julie-premium-routing.js`; protected relay components include `api/ac/event.js`, `api/meta/capi.js`, `lib/julie-capi.js`, `lib/click-id.js`, `lib/blueprint-golden-capi.js`, `lib/blueprint-receipt.js`, and `package.json`. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

#### Exact transport contract

- One pixel only; browser `eventID` equals server `event_id`, and Purchase identity is the CRM order ID, emitted only after Airwallex `SUCCEEDED` or PayPal capture. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)
- Historical identities: `julie_pv_<session>`, `julie_vc_<session>`, `julie_atc_<CRM orderid>`, `julie_ic_<CRM orderid>`, Purchase `<CRM orderid>`; retries must keep identity unchanged. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)
- Preserve exact-case `fbclid` inside `fb.1.<ms>.<fbclid>`; persist `_fbc` plus `julie_fbc_v1`, use actual `_fbp`, and bind buyer identity to the exact CRM StudentId/OrderId before SHA-256 hashing. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)
- Client→relay sends `event_id`, `event_source_url` and `action_source=website`; the relay attaches client IP and user agent, and the historical client retries at most twice on 5xx/429/no response using the same event ID. [October 9 transport record](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)
- Historical QA exclusions: `qa=1`, `llatest=1`, `env=staging` or a non-approved host/path disable live tracking; `meta_test=TEST...` is server-only diagnostic mode, and relay `qa=1` rejection is `qa_excluded`. `preview=zoom-link-sample` is **not** one of those QA flags. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md) [October 9 mode record](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)
- Historical relay preflight signature: OPTIONS 204, `x-lla-release: clickid-exact-20260922`, CORS origin `https://www.longevitylifeacademy.com`; do not treat that old signature as current without reading it again. [Golden source](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

#### Golden ad-tag string

The documented Set 03 string is preserved exactly below, including the historical double ampersand. [October 9 tag contract](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)

```text
cid=118149&adGroupID=108815&utm_source=Facebook&utm_medium=Topic&&utm_campaign={{campaign.id}}&utm_term={{adset.id}}&utm_content={{ad.id}}&creative={{ad.id}}&placement={{placement}}&cq_src=facebook&cq_cmp={{campaign.name}}&cq_con={{ad.name}}&cq_med={{placement}}&cq_net={{site_source_name}}&cq_plt=fp
```

Historical CRM group mapping is Set 01→108813, Set 02→108814, Set 03→108815, Set 04→108816, Set 05→108817, Set 06→108818; October 9 identified Set 03 Ad#12 `52670183445628` and paused Set 05 copies `52670177531628`/`52670187364628` incorrectly retaining 108813. They were not repaired in that handover. [October 9 mismatch evidence](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)

The later new Set 02 is `52673824399628`, distinct from old retargeting Set 02 `52668268711228`; copying an ad preserves static CRM tags even when dynamic Meta macros change, so the new set's name/tag does not prove URL alignment. Purchaser-set review (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

#### Read-only incident runbook

1. Fix the observation window and timezone; collect existing CRM-paid order IDs and exclude documented QA.
2. For each order, compare browser/server event name and event ID, actual value/currency, source URL, click/browser IDs and timestamps.
3. Confirm processor success separately; neither a rendered payment form nor a CRM stage transition proves money was captured.
4. Reconcile raw receipts, deduplicated events, ad-attributed events, orders and unique buyers as five different measures.
5. Read Meta attribution at a later timestamp before classifying an initial discrepancy as permanent loss; never promise a fixed lag guarantee.
6. Compare deployment/files against **both** frozen tag and pre-release production; report which baseline passes.
7. Inspect each participating host/relay, not only one checkout copy; community origin requires order-level `LandingPageURL`/`QueryString` and post-launch timing, not merely a shared pixel or IIBS campaign label.
8. Escalate unresolved failures with existing evidence; do not disconnect datasets, deploy relays, replay Purchase, create QA orders or change ad tags in this read-only task.

These checks address the documented raw-versus-attributed lag, multi-host boundary and community-origin ambiguity; they are recommended operational steps, not a claim that they all passed today. Tracking incident (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) Community attribution record (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

### Open acceptance gates as of October 28

1. **AC connector:** live read failed with Invalid URL today; actual installed bodies, automation configuration, sends and latest deals remain unverified.
2. **Sandra/Chris communication completeness:** no direct relevant mail receipt returned; final copy-paste messages and handoff-document contents are available, but a complete work-mailbox/WhatsApp correspondence archive is not established.
3. **Chris imports:** confirm final IIBS v4, corrected destinations, time zones/refund copy, current no-show branch, dynamic Zoom/LMS values and November reminders.
4. **Offer parity:** Pages.dev approved pricing supersedes the October 27 19:37 read; email text, tracked destinations, branded page rendering, CRM intent and actual payment schedule need their own consistent evidence.
5. **Callbacks:** mocked acceptance and staging queue are not production sales receipt or a completed callback.
6. **Paid enrollment:** current source/screens and diagnostic events do not certify payment→enrollment→LMS/Zoom delivery on physical devices.
7. **Attribution:** Julie's September 28 golden transaction does not certify Blueprint's independent funnel or every later deployment.
8. **Revenue truth:** CRM-paid, processor-settled, refunded, ad-attributed and unique-buyer counts remain distinct until reconciled.
9. **Freeze:** the recorded fixed period ended October 26; no extension is established in this handover, and expiration is not blanket permission to alter protected production.

These gates summarize the dated source limitations and current connector result rather than asserting fresh production defects. [Access/data gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md) Approved offer session (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) Attendee validation record (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) [Golden record](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

### Local source traceability and research limitations

#### Curated pages read

`memory/knowledge/entities/sandra-kwiecien.md`; `projects/lla-masterclass-emails.md`; `projects/lla-julie-invitation-blast.md`; `projects/lla-julie-tracking.md`; `projects/lla-course-checkout.md`; `projects/lla-handoff-pack.md`; relevant lines in `projects/lla-masterclass-attendee-offer.md`, `projects/lla-julie-masterclass.md`, `projects/lla-julie-live-operations.md`; dated learnings October 22–27.

#### Original sessions retrieved/read

- `dd017f79-f19e-40e4-9b16-9092f70b5529`: September 23–24 Sandra/package baseline audit.
- `eb59d6be-403b-4f0d-b4c4-084a56bd88f3`: earlier package-email context, outside main reporting window.
- `5619952e-b572-4412-9ea7-6df3c8e233b1`: school-blast scheduling/handoff context.
- `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`: October 15 identity coverage patch and diagnostics.
- `ad99e93f-fc49-4bda-be84-3501fced7806`: October 18 Chris handoff messages, v4, link/time/refund corrections and community attribution.
- `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`: original purchaser audit artifact and access-route correction.
- `5f70d990`: October 25 AC field-187 attribution method and repeated Invalid URL, using local original transcript; full UUID must be read from its YAML if needed.
- `219ddd45-d288-402e-b1fc-d82739bfd55b`: loaded original incident session; detailed incident synthesis also read in tracking wiki.
- `658b2028-3543-446e-8b94-2c5db8006a50`: loaded original session; broad multi-topic transcript, not by itself a direct Chris delivery receipt.
- `7f86bc26-cac2-4af5-8a69-13e059680d3d`: October 27 final-file destination inspection and old-price read.
- `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`: October 27 offer-parity approval and November mapping.
- `c3a19142-607c-4005-aeda-8c65494e6bd5`: attendee page, callback and payment/enrollment verification boundaries.

#### Important methodological limits

The local memory folder's week bucket is not an event date: original transcript headers and per-message timestamps take precedence. Several source documents are historical snapshots; this handover does not rebrand their old “VERIFIED” labels as October 28 live certification.

No customer list was opened for reproduction, no credential value is included, and no active service was modified. Repository reads used authenticated `gh` read operations only. The actual email coverage gap is explicitly retained rather than filled with invented correspondence or send receipts.



# Meta campaigns, current access and operating history

## Meta campaigns and ecommerce: read-only handover

Prepared 2026-10-28. Scope: French Atelier main/v2 accounts, two Capsules ecommerce campaigns, LLA Julie masterclass and Blueprint ecommerce. No live settings changed; no audience memberships, customer identifiers or seeds exported.

### Current verification result: NOT a fresh campaign status report

**Live Meta access failed.** At the start of this run (2026-10-28 07:45 UTC), `meta --output json ads adaccount list` returned API error 190: “Error validating access token: The session has been invalidated because the user changed their password or Facebook has changed the session for security reasons.” Connector discovery independently reported `meta_ads` DISCONNECTED, and the available tool catalog contained no `ads_*` current-read tools. Therefore today's account operational status, campaign/ad-set configured/effective status, budgets and update timestamps are **unverified**, not zero, paused or unchanged. The error concerns authentication, not a proven disabled ad account. [Meta account-discovery endpoint](https://graph.facebook.com/v25.0/me/adaccounts?fields=id,name,business&limit=25)

The task's **Julie paused** premise and **Blueprint restart intent today, 2026-10-28**, must be carried as owner/task context, not a newly observed API result. No recovered original October 28 session independently verifies a campaign-wide Julie pause. Do not activate Blueprint, resume Julie, change destination URLs, or reuse a historical approval as present authority. This assignment is read-only.

### Account selection: do not confuse French Atelier main with v2

| Account | Exact recovered name / ID | Use and evidence boundary |
|---|---|---|
| French Atelier main/older | `French Atelier`: `act_1188017096669618` | Distinct from v2. Older failed website-visitor lookalikes were found in the other FA account, not proof of a working purchaser audience in v2. [Account inventory](https://github.com/gitteromri-ux/handover-master/blob/main/projects/french-atelier-ecommerce-handover-2026-10-20.md), October 22 original session (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) |
| Capsules operating account | `French Atelier v2`: `act_1358975119724184` | The two Capsules Sales campaigns and three selected launch sets are here; historical reporting currency USD, account reporting timezone Asia/Jerusalem. Original launch/monitoring sessions (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`), October 26–27 monitor (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) |
| LLA | `Longevity Life Academy`: `act_1459085242361281` | Julie and Blueprint ecommerce; historical account JSON has currency `USD`, timezone name `Israel`, account_status `1`. That is a September snapshot, not today's status. [Historical account JSON](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-meta-handover-20260930/data/account.json) |

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

