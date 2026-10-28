| Item | Evidence found | Safe status |
|---|---|---|
| Sandra package-approval message | September 24 original audit says **do not send** the proposed message and supplies a replacement hold message | Draft / proposed correspondence; not sent evidence. Original Sandra audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`) |
| Chris final launch file, JM-U1–U4 | October 27 original session inspected a file called “Launch email for Chris”; Omri described it as the final file sent to Chris | Historical final handoff content established; direct email delivery receipt absent. Original final-file inspection (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`) |
| October 18 12:18 UTC Chris launch-corrections message | Complete copy-paste message in original transcript | Prepared for Omri to send; not a sent Gmail receipt. Original Chris corrections (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) |
| October 18 14:03 UTC Chris IIBS v4 message after speaking with Elaine | Complete final revised message in original transcript | Prepared copy-paste handoff, with import confirmation requested; no confirmed AC import/send. Original final Chris copy (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) |
| October 22 16:00:16 UTC “Re: Updated board deck” to Keren | Gmail message `1a164577ad8481e0`, thread `1a164577ad8481e0`, `SENT` label, recipient `[email redacted for public handover]` | **Confirmed sent** in current Gmail read; included to distinguish genuine sent evidence from Chris drafts, not as a Chris handoff. Evidence: current Gmail receipt. |

### Chronology: what changed and what remains unproven

#### Baseline entering September 28: September 23–24 audit

The original Sandra audit found 36 emails across two scenarios, Regular $49 and VIP $79—not a 60-email, three-scenario package—and found the Blueprint purchaser branch removed from that package. Original September 24 audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

All three checkout-recovery groups returned to the generic Julie `#pricing` section rather than restoring the selected package, session date, stage or existing order; the audit specifically flagged “Choose My Session Date,” “Finish My Booking,” and “Complete My Order” as promises the links did not fulfill. Original September 24 audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

The audit also left the Regular $49 discount mechanism, official CRM product naming, and a second linked $0 VIP Masterclass enrollment for Blueprint buyers unverified; it did not establish a secure abandoned-order recovery token. Original September 24 audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

These are **pre-window baseline defects**, not assertions that every defect still exists on October 28; they explain why a polished package could not honestly be called installation-ready. Original Sandra audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

#### September 28: Golden transaction and freeze

The golden record dates the freeze from September 28, 15:30 IDT through October 26 and records a real customer's $79 Airwallex order at 11:05:01 IDT, credited to ad set `52668330533628` / CRM group `108813`; three raw Purchase copies were reported as one attributed purchase. Customer identity is deliberately omitted here. [Golden record](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

The golden website commit is `42726fcd6a46908a499f2d94bb5cbf2f9558c947`, tag `tracking-golden-20260928`, and relay deployment `dpl_DQogoRsNj1XXTpJQmFrRk9zzCCrU`; these are **frozen historical baselines**, not freshly verified current production deployment IDs. [Golden record](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)

#### October 4–10: duplicate-source investigation and handover gaps

The October 9 handover records an October 4 14:10 Events Manager notice saying the dataset was no longer using CAPI, while later server-event counts continued; its explanation that a second sender went quiet was explicitly an assumption and the second sender was not identified. [October 9 handover](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)

A later handover records a Business Manager dataset connection being disconnected during duplicate-server-copy investigation; no diagnostic-clearance result follows from that action. [Recorded handover amendment](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648)

The October 9 handover had AC access through a cloud-browser API-token-header route despite the broken Pipedream connector, but runtime Vercel logs returned 403, Cloudflare metrics were unread, and no real paid test was completed; its categorical “attribution complete” language must not be generalized beyond its dated observations. [October 9 handover](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md)

October 10's gap register left AC automations/lists/tags/live sequences and send counts uncaptured; it also lacked a full Meta ↔ CRM ↔ processor ↔ refund truth table. [October 10 gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)

#### October 15: identity-coverage patch

Release `julie-meta-20261015-1`, branch `tracking/emq-coverage-20261015`, PR #1 and merge `a188c6c1bbb4ec79f25de1020597e15aec6d364f` initialize first-party `_fbp` before deferred `fbevents.js`, add anonymous `external_id`, and retain remembered buyer identity for seven days until an accepted Purchase. Original patch session (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) [PR #1](https://github.com/Longevity-Academy/julie-masterclass/pull/1)

The original 07:05 UTC response reports accepted server-only PageView/ViewContent diagnostics under `meta_test=TEST10151`, but that is not proof of Events Manager UI inspection, traffic-wide coverage, paid Purchase success or Blueprint attribution closure. Original patch session (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)

The wiki distinguishes Omri's generic “go” from the required literal item-specific freeze lift; repository approval/merge alone does not establish that missing sentence. Tracking synthesis and source trail (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

#### October 17–18: rollback and email launch handoffs

Rollback `cf899f2594e7acb209c0bee27acf99c07d234fdb` restored `a188c6c`, retaining the October 15 tracking patch; the tracked live hash prefix `7dcf7ce9f645` differed from the frozen-tag prefix `9f5ddfbae39c`, while attribution code matched and payment-safety also differed. This is a baseline distinction, not proof of lost sales. [Rollback](https://github.com/Longevity-Academy/julie-masterclass/commit/cf899f2594e7acb209c0bee27acf99c07d234fdb) Original incident record (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

On October 18 at 12:18 UTC, Chris's prepared message required every launch link/image/button to open `/masterclass-72hours/` at the hero, preserve UTMs, remove section anchors, show all four US time zones and apply the corrected refund footnote; it asked for AC confirmation **before sending**. Original launch message (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

At 14:03 UTC, the final revised message begins “After speaking with Elaine,” and identifies the dedicated IIBS v4 tab, four segments and approved content-only changes, explicitly preserving Rosen and Longevity and warning that GitHub is not an automatic AC update. Original final Chris message (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

At 14:09 UTC, the original session records the community offer's fixed window as October 18 17:00 Israel through October 21 17:00 Israel; that dated campaign window must not be silently represented as a fresh rolling 72-hour promotion on October 28. Original timer record (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

#### October 18: CRM extraction precedent

The original purchaser review records 18,941 initial deal rows, followed by a duplicate-safe ordered audit of 3,022 unique won deals across 31 pages; 116 price candidates reconciled to 109 included paid orders and seven internal/test orders, producing 101 unique buyers. These are historical extraction-quality controls, not current totals or a customer list. Purchaser-audience session (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

The artifact distinguishes accepted upload rows from matched Meta users and leaves a CRM-unpaid payment-sync exception outside the seed; processor settlement/refunds were not certified. Local original artifact: `memory/sessions/2026-10-12_2026-10-18/2b7e0eda/ai_outputs/Julie-Masterclass-paused-ad-set-review.md`. Purchaser-audience session (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

#### October 22–28: no-shows, reporting and offer parity

The October 28 lifecycle wiki records a revised four-message no-show branch: JM-X1–X3 for October 27 absentees who may attend November 14, and JM-X4 for November 14 absentees with 30-day LMS recording access—not an invitation to a nonexistent later session. [No-show revision](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/ebbe0a3c62c68ff2468c10ce32e0262b322cec02)

The follow-up revision removes “no replay,” unsupported $200-credit wording and stale enrollment-footer language; its replacement footer is “You received this as a masterclass registrant.” Chris remains responsible for actual Zoom/LMS values and November preparation/day-before/two-hour reminders; installed versions and sends remain OPEN. [Corrected no-show copy](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/18b89c487feac5389fb2d07a48844a2c4103cffd)

On October 25, the original reporting dialogue corrected an initial confusion between an eTeacher payment-log envelope and ActiveCampaign CRM data: AC deals carry order/amount/status and contact field 187 carries the Ad ID; Meta mapping can then resolve the ad set without waiting for Meta's credited Purchase count. Original session identifier verified from the transcript header: `5f70d990-447e-43ce-9ade-7e29fbae7c02`, transcript lines 7270–7370.

The October 26 tracking synthesis records four CRM-paid orders with raw Purchase receipts while Meta initially showed zero credit, then four attributed purchases split one to Set 02 and three to Set 04; eight raw browser/server receipts were not eight sales and did not themselves prove deduplication. Incident/reporting record (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

At October 27 19:34 UTC, the final Chris file's JM-U1–U4 destination was verified at document level as Pages.dev with `MASTERCLASS-VIP`; Regular/VIP abandonment sequences still returned to Julie pricing, while live AC inspection failed with Invalid URL. Final-file inspection (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`)

At October 27 19:37 UTC, that session read old Pages.dev copy of $179×5 regular, $149×5 promo and $799 upfront; the later approved parity work supersedes those figures with $169×5 regular ($845), $79 plus four $169 installments ($755) for `MASTERCLASS-VIP`/`JULIE249`, and $799 upfront. Original old-price read (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`) Approved parity session (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

The parent research track reports a fresh October 28 Pages.dev fetch consistent with the revised schedule and notes that extracted branded-attendee content still contains legacy 149/179 text; treat that as a text-parity flag, not visual proof of what a buyer sees or a completed charge. The authorization is recorded at October 27 19:48 UTC in session `25a94f9a`; source changes include `ac35c2874e54bcc2b67f14beaff4ed8c900f9962`. [Offer-alignment commit](https://github.com/gitteromri-ux/lla-course-checkout/commit/ac35c2874e54bcc2b67f14beaff4ed8c900f9962)

### Email surfaces, mappings and exact handoff requirements

| Surface / repository | Use | State and limitation |
|---|---|---|
| `gitteromri-ux/lla-masterclass-emails-3tier` | Regular/VIP lifecycle versions | September 24 package audit; field names and CTA shortcomings described above. [Gallery](https://gitteromri-ux.github.io/lla-masterclass-emails-3tier/) |
| `gitteromri-ux/lla-masterclass-emails` | Maintained lifecycle/no-show gallery | Review URL carries `?v=18b89c4`; source publication is not an installed AC version. [No-show review](https://gitteromri-ux.github.io/lla-masterclass-emails/?v=18b89c4) |
| `gitteromri-ux/julie-masterclass-blast` | School/LLA one-time acquisition invitation | One original circulated URL, not a new `/v2` handoff. [Gallery](https://gitteromri-ux.github.io/julie-masterclass-blast/) |
| IIBS v4, commit `6df81d9a9298cbd38a93d20533474560856cb791` | Alumni, active students, non-completers, leads | Seven IIBS files; copy-only approved change; Rosen/LLA unchanged. [Direct IIBS v4 tab](https://gitteromri-ux.github.io/julie-masterclass-blast/?v=6df81d9-iibs-v4#iibs-v4) |
| JM-U1–U4 | Post-event Blueprint promotion | Final handoff leads to Pages.dev, not normal Julie event purchase. [Exact JM-U1 destination](https://longevitylifeacademy.pages.dev/?enroll=1&code=MASTERCLASS-VIP&utm_source=activecampaign&utm_medium=email&utm_campaign=lgv_onboarding&utm_content=jm-u1) |
| JM-A1 / A2 / A3 families | Name Details / Course Details / No Payment recovery | Both Regular/VIP historically return to masterclass pricing; secure resume of an existing order not established. Original recovery audit (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`) |
| Community invitations | 36%-off, 72-hour school offer | `/masterclass-72hours/`, hero arrival, UTMs retained, no `#pricing`; no claim that offer remains active today. [Destination](https://www.longevitylifeacademy.com/masterclass-72hours/) |
| Attendee course/questions page | Blueprint signup and separate sales callback | Branded route `/blueprint-attendees-7q4x/?code=JULIE249`; not the Julie event checkout. [Attendee page](https://www.longevitylifeacademy.com/blueprint-attendees-7q4x/?code=JULIE249) |

The preserved personalization tokens include `%FIRSTNAME%`, `%LGVMASTERCLASSSESSIONDATE%` and `%LGVMASTERCLASSZOOMLINK%`; preview sample values must never replace production tags or become guessed Zoom/LMS URLs. [Historical lifecycle implementation](https://github.com/gitteromri-ux/handover-master/blob/main/projects/lla-masterclass-emails.md)

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

