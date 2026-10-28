- **Verified live reach and pipeline reach are separate**: Published groups, approved memberships, pending requests, and potential member totals are tracked independently so unapproved access is never reported as distribution (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **Group eligibility is identity-specific**: Distribution uses the real profile or LLA Page where that identity can publish. The source reports both profile and Page submissions; Page access is not universally blocked, and membership or submission alone does not prove a live post. (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`)
- **Every post is attributable**: Destination links carry campaign and group identifiers so organic visits and downstream checkout intent can be evaluated by source (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **The status page is operational, not promotional**: The internal surface is marked noindex and shows evidence, current access state, and next actions without presenting pending reach as achieved results (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **Published-state checks must read the actual Published surface**: Removed-queue entries were once misclassified as live and inflated reported reach. A live claim now requires an individual Published-state check; removed, declined, and queued posts remain separate (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **Tracking fetches are not audience clicks**: Facebook can load a tracked link while a post is composed or verified. Events clustered in posting windows, including events for posts still awaiting approval, therefore cannot be reported as organic audience traffic (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **Approval mode determines immediate reach**: Groups with post approval disabled can publish immediately; moderated groups contribute only pipeline reach until an administrator releases the post (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).
- **Membership totals are not impressions or reach**: Group member counts describe possible audience size only. The September posting rounds produced about 245 submissions, but only 56 were reported live across all rounds and just 15 had been verified in the prior 24 hours; pending queues remained a separate pipeline (original session `956703ee-01d7-472a-87c5-9846dbba6053`).
- **Redirect telemetry cannot establish a human-traffic ceiling**: The reported 322 tracked-link loads include posting/verification activity. A 700ms redirect can also outrun pixel loading and undercount genuine visitors, so the earlier five-click floor/~60 ceiling is not a certified audience total. No purchase was traced to a group link; three unattributed site purchases do not establish zero organic sales. (original session `956703ee-01d7-472a-87c5-9846dbba6053`)
- **Source attribution must survive the full funnel**: A group-specific redirect identifies the click source, but AddToCart, checkout, and purchase cannot be called organic when UTM/source data disappears downstream. End-to-end organic measurement was not delivered in the September rounds (original session `956703ee-01d7-472a-87c5-9846dbba6053`).

### See also

- `entities/longevity-life-academy`: client and course
- `projects/lla-course-checkout`: conversion destination
- `projects/lla-funnel-performance-deck`: measurement surface
- `projects/lla-masterclass-sales-rfp`: separate AI acquisition comparison


---

Record: `lla-masterclass-sales-rfp` | knowledge last updated: 2026-10-26T08:44:00+00:00

## LLA Masterclass Sales RFP

LLA Masterclass Sales RFP is Omri's comparison of immediately executable AI-led acquisition ideas for Julie's masterclass through October 27. It excludes email, SMS, call-center work and Meta campaigns from this request. The assistant reported a public comparison hub and recommended actions, not an activated sales program or verified sales result. (original session `5b70164c-5a23-4fe9-bf6b-bc963c9c2035`)

### How it works

Omri requested ten proposals each from Claude, Grok and Perplexity, including realistic cost-per-purchase assumptions, timing, activities and an executive-readable comparison. Pasted Claude proposals are third-party suggestions rather than adopted decisions. (original session `5b70164c-5a23-4fe9-bf6b-bc963c9c2035`)

- **Comparison before activation**: The reported [public RFP hub](https://gitteromri-ux.github.io/masterclass-rfp/) has four tabs; a Grok submission was still missing. Six recommended actions and a projected 24–45 sales were assistant proposals, not authorization or achieved outcomes. (original session `5b70164c-5a23-4fe9-bf6b-bc963c9c2035`)
- **Immediate execution is the selection constraint**: Ideas requiring a fresh Meta learning period or unapproved communication channels do not satisfy this brief. Later discussion also rejected reliance on newsletters, Julie's own profile and other people; no eventual plan was shown activated. (original session `5b70164c-5a23-4fe9-bf6b-bc963c9c2035`) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)

### See also

- `projects/lla-julie-masterclass`: offer being promoted
- `projects/lla-organic-community-blitz`: separate community distribution system


---

Record: `lla-julie-tracking` | knowledge last updated: 2026-10-26T08:44:00+00:00

## Julie Golden CAPI

Julie Golden CAPI is the protected attribution chain linking the Julie masterclass campaign, production purchase page, eTeacher order, payment success, and Meta Purchase. Omri owns its documented freeze through 2026-10-26; the golden record describes an attributed real-customer transaction, not universal certification of every subsequent release. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))

### How it works

Campaign `LGV_EN_PPC_ecomm-02_2026-09-02_#118149` (`52668266203628`) points to the masterclass path on `www.longevitylifeacademy.com`. The page feeds pixel `1440305917310328` and the shared `lla-ac-events` relay at `/api/meta/capi`. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))

- **Stable order identity**: Browser `eventID` equals server `event_id`; Purchase uses the CRM order ID and follows Airwallex success or PayPal capture. ClickID is preserved exactly in `fbc`, `_fbp` is read from the cookie, and CRM-bound buyer identity is hashed before sending. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- **Ad link is part of the contract**: The golden link retains `?preview=zoom-link-sample`, campaign `cid=118149`, set-specific `adGroupID`, and dynamic ad/set attribution tags. The preview query is not one of the documented QA exclusion flags. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)) (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)
- **Protected production boundary**: The freeze covers ad attribution configuration, URL tags, pixel settings, page tracking/payment files, and the relay deployment. Lifting a protected item requires Omri’s literal item-specific freeze-lift sentence; unrelated presentation changes still pass branch preview, approval, and before/after guards. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- **Golden deployment and source**: The relay record names `dpl_DQogoRsNj1XXTpJQmFrRk9zzCCrU`; the page source is `Longevity-Academy/julie-masterclass`, and the golden tag is `tracking-golden-20260928`. The guard checks both code hashes and Meta configuration. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- **Raw events and attributed purchases differ**: The golden purchase record describes three raw browser/server copies deduplicated to one attributed purchase. A later handover records the Business Manager dataset connection being disconnected while duplicate server copies were being investigated; that action is not a documented diagnostic-clearance result. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- **Order truth and ad credit differ**: The checkout’s session/ad field identifies a recorded last-click path, not a matched Meta event. Repeated paid orders remain separate orders even for one buyer; neither accidental duplication nor an upgrade follows from shared identity. Unpaid staged records are not purchases, and CRM-paid status is not processor settlement. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Attribution can lag raw receipt**: The October 26 report first showed four CRM-paid orders and raw Purchase receipts while Meta credit was zero, then four attributed purchases split one to Set 02 and three to Set 04. Eight browser/server Purchase receipts were not eight sales or proof of deduplication. A required preceding attributed AddToCart was not established as a condition for Purchase credit. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Initialize first-party identity before deferred Meta code**: Release `julie-meta-20261015-1`, merged as `a188c6c`, initializes `_fbp` before deferred `fbevents.js`, supplies an anonymous visitor `external_id`, and remembers buyer identity for seven days, clearing it on accepted Purchase. The coverage patch is distinct from changing the protected attribution interface. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- **Diagnostic acceptance has bounded scope**: Production testing with `meta_test=TEST10151` confirmed matching module/cookie fbp, exact-case fbc, an external ID, and accepted PageView/ViewContent receipts. It did not establish Events Manager UI results, traffic-wide match coverage, paid Purchase certification or clearance of the separate Blueprint Set 2 investigation. Omri’s generic “go” is evidenced; the literal item-specific freeze-lift sentence is not. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)
- **Frozen tag and rollback baseline are different**: The 2026-10-17 rollback `cf899f2` restores `a188c6c`, retaining the 2026-10-15 tracking patch. The inspected live tracking hash starts `7dcf7ce9f645`, versus golden-tag `9f5ddfbae39c`; payment-safety also differs from the tag, while attribution is identical. A match to the pre-release production files does not establish frozen-tag compliance. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/cf899f2594e7acb209c0bee27acf99c07d234fdb))
- **PR merge is not the literal freeze lift**: The coverage change used branch `tracking/emq-coverage-20261015` and PR #1, merged under `gitteromri-ux`. Repository process is established; the required item-specific lift sentence remains unestablished. A guard failure establishes a baseline difference, not proof that a purchase was lost. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/a188c6c1bbb4ec79f25de1020597e15aec6d364f))
- **Design diffs and purchase logic are separate**: The inspected payment-safety difference changes Drop-In appearance and save-card defaults; the coverage patch changes first-party identity inputs. Neither unchanged Purchase code nor those diff scopes prove complete delivery, deduplication or attribution on real traffic. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Recovery evidence has bounded scope**: The `projects/lla-julie-checkout-recovery` release reports production-baseline hash matches and PageView/ViewContent firing, while its QA mode disables Meta. The subsequent `projects/lla-julie-checkout-incident` leaves order-to-Meta matching unresolved; form rendering, accepted diagnostic events and matching hashes do not certify paid Purchase coverage. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Community source is an order-level distinction**: Existing checkout payloads send `LandingPageURL` and `QueryString`. Identifying a paid community sale requires its originating `/masterclass-72hours/` path and payment after launch; the shared pixel and a persisted IIBS campaign label alone cannot distinguish it from the normal page. Retention beside the paid order in ActiveCampaign was not verified. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **New-set naming does not rewrite copied tags**: `projects/lla-julie-purchaser-audience` is named with terminal CRM tag `#108814`, but its copied URLs retain source group values. The approved activation is not evidence that the new URLs were aligned or that end-to-end CRM attribution passed. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

### See also

- `projects/lla-julie-masterclass`: protected purchase surface
- `projects/lla-julie-meta-pilot`: acquisition and attribution decisions
- `projects/lla-course-checkout`: separate Blueprint proof boundary
- `projects/lla-julie-checkout-recovery`: isolated payment repair preview
- `projects/lla-julie-community-offer`: separate clone attribution boundary
- `projects/lla-julie-checkout-incident`: rollback and order evidence


---

Record: `lla-julie-purchaser-audience` | knowledge last updated: 2026-10-26T08:44:00+00:00

## Julie Purchaser and Warm-Audience Ad Set

Julie Purchaser and Warm-Audience Ad Set is Omri’s approved acquisition extension for Julie’s masterclass. Set `52673824399628` launched at $99/day with four selected creatives and fifteen paused copies; it combines purchaser-lookalike prospecting with campaign-specific warm retargeting rather than separating their budgets. It is the live Set 02 in later reporting, not the retired similarly named paused set; launch budget is not its maintained budget. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### How it works

The set uses website Purchase optimization, lowest-cost bidding, United States ages 44–65+, and Facebook Feed plus Reels only. Both genders are eligible. Advantage+ Audience, custom-audience expansion and lookalike expansion are reported off; configuration restrictions do not guarantee buyer intent or perfect identity/location matching. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

- **Explicit launch exception**: Omri approved GOLIVE for this purchaser-lookalike/warm configuration. That approval does not broaden the existing live sets or authorize changes to their budgets, targeting or original creatives. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Enriched seed preserves the original**: Seed `52673824207628` retains its original 101 identities and accepted nineteen then two verified additions, zero invalid rows, for 122 submitted distinct buyer emails from 131 reconciled paid-order records. The final two additions map to orders `8056658` and `8056899`. Its original “101” label was deliberately preserved; that label is not the submitted count, and submitted count is not matched-user count or settlement proof. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- **Seed processing and lookalike readiness differ**: Seed additions read ACTIVE/Updating (300), while existing 1% lookalike `52673827176428` remained ACTIVE/Normal (200). Normal does not prove refreshed matching finished. The separate 129-order call-list snapshot had 120 distinct emails and an earlier cutoff. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- **Set 3 only**: Omri’s attachment approval applied to paused Set 03, excluded set 6 and preserved budget/creatives at that action. Subsequent resumed delivery does not broaden the earlier approval or establish who made intervening creative changes. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Seed update is not a pacing guarantee**: Updating an existing customer list and adding a lookalike to targeting are different edits. The former’s documented non-reset behavior does not guarantee unchanged spend speed; the latter is a targeting edit that can restart learning. No observed result establishes specifically slower or better morning delivery. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- **OR, not AND**: Eligibility is membership in the 1% purchaser lookalike OR the defined Julie Checkout-30d/AddToCart-14d pool, with purchaser exclusions. The cart rule includes the Julie page and campaign ID, excluding untagged return visits. Ordinary page visitors are not included. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Warm-pool warning is separate**: The narrow checkout/cart pool was still populating and flagged small; the purchaser lookalike was ready. Event totals are not distinct reachable non-buyers. The broader ready 180-day Julie page-visitor pool and three-way separated audiences were discussed but not implemented in this launch. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Exact selected sources**: Omri chose Ad#17 Five Habits from Set 05 (`52670277632228`), zoom-blue slower v4 from Set 01 (`52673573725028`), Ad#21 Julie cards from Set 03 (`52673304378628`), and card-gold Reels from Set 03 (`52670313921028`). Four are enabled; the other fifteen copies remain paused. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Numeric CRM tag ends the name**: The corrected set name is `ecomm_Adset_02_All_All_CPM_#108814`, with nothing after `#108814`. Nineteen ad names were checked against their source names with no added labels or suffixes. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Name and URL mapping are different interfaces**: The copied URLs retain source `adGroupID` values `108813`, `108815` and `108817`, rather than new set `108814`. Renaming does not align those tags; the reviewed session ends with a request for approval to change the new copies, not a completed repair. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)

### See also

- `projects/lla-julie-meta-pilot`: parent paid-acquisition experiment
- `projects/lla-julie-tracking`: protected URL attribution interface
- `projects/french-atelier-purchaser-recovery`: separate brand buyer investigation


---

Record: `french-atelier-performance-diagnosis` | knowledge last updated: 2026-10-26T08:44:00+00:00

## French Atelier Performance Diagnosis

French Atelier Performance Diagnosis is the browser-ready operating surface for comparing call-center activity and acquisition performance across reporting periods. (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`)

### How it works

The project turns uploaded rep and weekday exports into side-by-side weekly and monthly diagnosis views linked from the existing French Atelier results dashboard (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`).

- **Period identity must be established before comparison**: The three uploaded exports carried different windows-September, the current week, and July–August-but the filenames and file contents did not identify which was which. Performance decline cannot be calculated or attributed until each export is mapped to its period (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`).
- **Only requested performance drivers belong in the diagnosis**: The corrected view focuses on the named representatives and overall calling rather than adding unsupported headlines or unrelated representatives (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`).
- **Near-identical totals do not establish a shared period**: Two rep exports had similar totals, but that similarity was not a valid basis for treating them as duplicate snapshots when the user stated they covered different dates (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`).

### Key surfaces

- Diagnosis: `https://gitteromri-ux.github.io/french-atelier-june-results/diagnosis/index.html` (original session `cdb8100a-982c-4f57-a758-7c81ccfb4327`)

### See also

- `projects/french-atelier-social-kickstart`: organic campaign system
- `projects/french-atelier-website`: production website
- `projects/french-atelier-weekly-reporting`: recurring corrected workbook


---

Record: `french-atelier-culture-capsules` | knowledge last updated: 2026-10-26T08:44:00+00:00

## French Atelier Culture Capsules

French Atelier Culture Capsules is Omri’s three-theme live culture-learning offer, campaign-gated production ecommerce page and launch library. The production URL is `https://www.frenchatelierlive.com/culture-capsules`; preview/review and launch-library surfaces remain separate. Omri approved the paid launch and checkout repairs; event transport and sandbox enrollment do not certify production ad-attributed purchases or settlement. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### How it works

Fashion & Art, Gastronomy & Wine and Cinema & Music each comprise ten live one-hour Zoom conferences plus Q&A, in English with no French required. The offer is independent of the language courses; the production site and checkout live in `gitteromri-ux/french-atelier`. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/c5f6111c982ae17cfee337a45de80bfa8961bcb6))

- **Readable hero and branded card differentiation**: Omri requested a larger headline with narrower line breaks, a larger subheader, and different card colors. The reported revision uses navy for one capsule, ivory/gold for the all-three best seller, and brand blue for two capsules. (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- **Public launch-pack surface**: The session provides a browser-readable media plan and hub in addition to GitHub source links, so the handoff is not limited to a repository directory. (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- **Dark source identity is separate**: Omri described recent pricing/fold work on another account’s dark Culture Capsule website. Its exact repository was not identified in the search session; the described dark build was not established as the same source as the French Atelier preview. (original session `90701961-41f5-40dc-a674-a33926c9c165`)
- **Earlier preview stays separate**: The balanced `fa-capsules-v3.pplx.app/capsules.html` publication preserves its floating CTA/promo controls and was not the French Atelier production merge. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- **Dark homepage is not dark Capsules**: The retrieved `staging-checkout-ecom-dark` v10 changes the 20-lesson language-course homepage. That source does not establish the final three-package Culture Capsules page Omri requested. (original session `0b5e32e6-fbb9-418f-a0ac-32c046b29743`)
- **Non-default bridge contains a dark-site snapshot**: `gitteromri-ux/fa-capsules-launch` branch `bridge` mirrors the public capsules URL in `bridge/out/capsules-site/`. It includes Fashion & Art, Gastronomy & Wine and Cinema & Music, with dark navy CSS. The mirror log records a syllabus-PDF 404; it is a capture record, not a current live-link test or production-promotion receipt. ([recorded evidence](https://github.com/gitteromri-ux/fa-capsules-launch/blob/bridge/bridge/out/capsules-site/capsules.html)) ([recorded evidence](https://github.com/gitteromri-ux/fa-capsules-launch/blob/bridge/bridge/out/capsules-site/_mirror.log))
- **Balanced lighting belongs to the earlier public preview**: Omri approved moderated brightness, stronger contrast and larger type after rejecting the initial overly bright treatment. Publication and browser checks establish fourteen balanced video backgrounds, autoplay, no tested mobile overflow and three checkout modals opening on that surface; completed payments were not tested. (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- **Programme visibility is separate from source completeness**: The saved page contained eleven sections and thirty conference cards, while two programmes were hidden by default. The separate public review exposes all three programmes and thirty cards; it does not replace the balanced sales page. (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- **Approved faculty design**: Beige background, Manuela Breschi left, Vicky Bourdenecc middle and Shaina Abdellaoui right; matched visible face scale/eye line, upright portraits and short readable credential-led bios. Shaina’s title is “Cinema & Music Instructor,” not graduate; Manuela’s genuine Christian Dior background anchors her copy. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Design-only release boundary**: Omri approved the reviewed teacher presentation, aligned theme cards, larger text, supplied Philippe/Charline films in section five and mobile CSS fixes. The release merged the newer checkout baseline and verified nine protected files byte-for-byte plus unchanged scripts and pricing-through-footer; no payment was submitted. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Three-payment offer with manual promotion**: One capsule is $99 ×3 = $297, two are $178 ×3 = $534, all three $189 ×3 = $567. CAPSULE20 must be entered and Apply pressed; visiting/copying the banner does not activate it. Rounded promotional installments are $79/$142/$151 and totals $237/$426/$453. Staging CRM checks confirm these displayed amounts without completed charges. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- **Per-capsule price leads the cards**: Omri explicitly requires the dominant monthly number to be $99/$89/$63 per capsule; two/all-three show the $99 reference with 10%/36% savings. Package installments and full totals are secondary. The reported final design retains tight spacing, large factual bullets and no pills; enrollment remains “Enroll Online.” (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- **Checkout presentation is not account timezone**: Customer-facing checkout uses EST/GMT/Pacific, not Israel time, and a lock beside secure payment. The approved reviewed publication includes the capsule refund period starting at registration. These presentation changes do not certify completed card/PayPal payments or change Meta’s reporting timezone. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- **Course-priced CRM orders**: Staging comparisons isolated forced `ProductID:25` in the French relay as the cause of the wrong $885 language-course schedule. Stripping it lets the CRM honor the chosen capsule course and payment amounts; the reported deployed relay rejects non-FA courses. The full-course offer remains $89 plus four $199 payments, not a Capsules plan. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Production gateway and brand identity are separate**: The reported relay deployment continues forwarding production CRM orders through `eteacher-leads-proxy.gitter-omri.workers.dev`, while using French Atelier course IDs and tracking identity. Its own direct CRM credentials cover staging; website pricing repair is not evidence of migration to French-only production infrastructure. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Dedicated checkout and attribution system**: `projects/french-atelier-capsules-checkout` owns Golden-derived tracking, buyer-bound order caching and paid bundle enrollment. Dataset `4075596186030950` is distinct from dataset “FA” `4400286150281912`; event receipts do not establish ad credit or settlement. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Failure-safe payment presentation**: Reported fixes cover 320/360/375/390/430px payment layouts and retain “Payment received. Enrollment confirmation pending. Do not pay again.” after simulated CRM-report failure. Pay Later/Venmo and unsupported automatic-monthly PayPal promises were removed; real recurring collection is not established. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Mobile redesign has a protected integration boundary**: Omri requests a larger, stronger hero headline, readable body type, no hero price text, no gold text on imagery and mobile sliders where useful. The mobile-readability v5 commit changes CSS and one hero span, hiding phone hero pricing while preserving tracking/checkout/attribution files. This source change does not establish resolution of the discounted-payment fallback or physical-device payment success. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/73865bb0303c6799a9498e0ced4c30a7ba6ab70f))
- **Website depth is a conversion concern, not checkout evidence**: The reported 28-screen iPhone-emulated walkthrough places the first full pricing cards around screens 13–14; the floating enrollment control shortcuts the long page. Omri explicitly requested website screenshots rather than another checkout sequence. Moving pricing/Enroll into the first screen was an assistant proposal, not an accepted replacement for the no-hero-pricing constraint. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Brand-wide seed and selected launch**: Omri rejected mixed-brand buyer padding and requested purchasers across French Atelier. `projects/french-atelier-purchaser-recovery` owns seed reconciliation and the reported 17-ad, three-set active launch; it is not warm-lead retargeting. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Campaign gate protects full-course presentation**: After sales-team complaints that the cheaper offer competed with full-course sales, Omri approved a client-side filter. Meta click IDs, Facebook/Instagram referrers or qualifying campaign tags admit the offer; returning ad visitors retain access for 30 days. New unqualified visitors see a neutral welcome with course/teacher links. Copied campaign URLs still work: this is not authentication. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/1a5938cc11c98d9697f948871448ff23cc016589)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/aaf9a1710961baf374f5327b0b49eb6d7d7b5f5d)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/8a8a3e61d2a8197443223819a34503ea21507692))
- **Offer versus welcome instrumentation**: Offer pages send `FA_OfferShown` and ViewContent; welcome pages send `FA_WelcomeShown` without ViewContent, alongside PageView. Aggregate counts and simulated-link checks do not identify the landing outcome of each real ad click. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/c0f9527ca0aea657a51d88aaca2217ca4abc1334))
- **Review access is test-only**: The CEO review link uses `?fa_review=capsules&qa=1&env=staging`, is shareable without login and does not take real payments. Its TEST MODE warning is separate from paid-traffic presentation; future email campaigns need explicit gate qualification. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/1a5938cc11c98d9697f948871448ff23cc016589))
- **Dark launch-hub identity**: Omri retained the existing dark hero and requested brighter motion footage, not a light-theme redesign. The reported correction restores dark styling and readable text without changing checkout/tracking. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Selected UGCs remain unchanged**: The three supplied `video-kit/ugc/` MP4s replace assistant-edited UGCs in the hub, mockups and downloads. Original website films and their edits remain a separate collection, not substitutes for or replaced by UGCs. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Launch library, not installed campaigns**: The hub contains twenty-four banner exports in three formats, sixty-four email assets, beauty clips, source films/edits and the selected UGCs. The reported banner rebuild uses Instrument Serif regular/italic headlines, Inter body text, wide photography and structured offer panels. Delivered files do not establish ActiveCampaign installation, sends or user acceptance of the rebuilt banners. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

### Surfaces

- Production: `https://www.frenchatelierlive.com/culture-capsules`, with separate payment page `enroll-checkout.html`; old enrollment URL redirects preserving attribution parameters. Internal no-charge walkthrough uses `?env=staging`. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- CEO purchasing entry: `https://www.frenchatelierlive.com/culture-capsules?utm_source=facebook&cq_src=facebook`. The GitHub review mirror is not a purchase handoff: Omri encountered a payment-page 404 there. Production page availability is not a completed-payment test. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- Earlier source/preview: `staging-capsules-light`, `docs/capsules-launch/` and `https://fa-capsules-v3.pplx.app/capsules.html`; these are not the canonical production launch URL. (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Separate public review: `https://gitteromri-ux.github.io/fa-capsules-review-public/`. (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- Launch library: `https://gitteromri-ux.github.io/fa-capsules-launch/?v=dd1841f`; supplied kit: `https://gitteromri-ux.github.io/fa-capsules-launch/video-kit/`. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- Ad selection board: `https://gitteromri-ux.github.io/fa-capsules-launch/ad-board/`; separate from the production offer and Meta activation. (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`)

### See also

- `projects/french-atelier-weekly-reporting`: separate language-course reporting
- `projects/french-atelier-website`: production site and source
- `projects/direct-ecommerce-school-pilot`: separate school acquisition test
- `projects/french-atelier-purchaser-recovery`: CRM buyers and launch audiences
- `projects/french-atelier-capsules-checkout`: payment entitlement and attribution


---

Record: `lla-julie-overnight-guardrails` | knowledge last updated: 2026-10-24T23:33:00+00:00

## Julie Masterclass Overnight Guardrails

Omri's stored overnight rules control Julie masterclass ad-set budgets through no-sale cuts, efficient-sale raises and dry-spend alerts. Actions are **reductions by a dollar amount**, not reductions to that amount. The verified automation is bounded to 2026-10-25 before 07:00 Asia/Jerusalem; storing the rules does not authorize perpetual nightly execution. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### How it works

The rules apply to campaign `ecomm-02` (`52668266203628`) in Longevity account `1459085242361281`. A sale counts for a set when Meta reports it or a CRM order carries that set's number; an unattributed CRM order does not cancel a set's cut. A qualifying sale before the cut cancels that cut for the night. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

| Set | Meta ad-set ID | No-sale spend trigger | Subtract from current daily budget |
|---|---|---:|---:|
| 04 · `#108816` | `52668330870828` | ≥$155 | $99 |
| 05 · `#108817` | `52668330871228` | ≥$145 | $49 |
| 02 · `#108814` | `52673824399628` | ≥$145 | $40 |
| 01 · `#108813` | `52668330533628` | >$149 | $30 |
| 03 · `#108815` | `52668330165828` | >$149 | $30 |

For example, Set 04 at a $999 budget becomes $900. Set 03 has the same cut as Set 01. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

- **Efficient-sale raise**: Any live set receives +$70 once when it has two sales at aggregate spend/sales ≤$100, or three at ≤$125. One sale or higher CPP produces no raise. Each cut and each raise can fire at most once per set per night. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Dry-hour alert**: Notify when Set 04 or Set 05 spends more than $50 in the last full hour with no sale in that hour. Quiet checks suppress notification; an alert is not itself a budget cut. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Narrow mutation scope**: Permission covers these budget deltas for the bounded night, not pausing sets or changing targeting, bids, ads or tracking. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Saved execution**: Automation `658668c7-5f7a-453d-9a44-7cb520aebdfa` was created with a 20-minute recurrence, local start `2026-10-25T01:50:00` and local end `2026-10-25T07:00:00`, then corrected to the decrements above. Its returned next wake is `2026-10-24T22:50:00Z`; an actual wake reports a Set 04 dry-hour alert and no budget mutation. This proves a saved definition and one wake, not all-night punctual execution. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Control telemetry is not settlement**: The saved prompt treats a successful `payments/crm` response as a paid-order signal and requires a set number to cancel a cut. This operational sales proxy is not processor settlement or browser/server Meta deduplication. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### See also

- `projects/lla-julie-meta-pilot`: parent acquisition campaign
- `projects/lla-blueprint-relaunch`: separate post-event acquisition plan


---

Record: `lla-julie-communications-plan` | knowledge last updated: 2026-10-24T10:14:00+00:00

## LLA Julie Communications Plan

LLA Julie Communications Plan is the public GitHub Pages briefing used to align Julie Gibson Clark on LLA campaign initiatives and her specific asks. The expanded preview places masterclass context before the campaign materials and collects Julie’s two requested actions at the end (original session `f43ebdba-3055-4d95-98f5-8baed7b8b701`) (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`).

### How it works

The plan uses a context introduction, numbered chapters, direct links, and one final request block to turn the masterclass and campaign materials into one reviewable handoff (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`).

- **Context before materials**: The introduction explains the proposed live masterclass and collaborative deck preparation before chapters covering videos, selected banners, the masterclass site, syllabus, mockups, PR, and animations (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`).
- **Requests belong at the end**: Omri rejected asks in each chapter. The final block requests two available dates and preliminary syllabus comments, keeping campaign materials separate from Julie’s actions (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`).
- **Public clickable handoff**: The surface remains anonymous and browser-ready, with direct initiative links rather than a document that depends on PDF annotations (original session `f43ebdba-3055-4d95-98f5-8baed7b8b701`) (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`).
- **Syllabus and speaker deck are separate artifacts**: The briefing's v4-preview syllabus and the curated `projects/lla-julie-masterclass-deck` have separate source scopes. The speaker review follows Version C and explicit overrides, including testing/disclosure content and the integrated day protocol; its publication does not certify parity of every public syllabus surface. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Executive distribution has its own brief**: `projects/lla-julie-executive-social` separates Harel, management/board and faculty voices for the masterclass. Its nine reported drafts ended in an unresolved risk audit, not an approved extension of Julie's teaching syllabus. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/lla-julie-communications-plan` ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-communications-plan))
- V1: `https://gitteromri-ux.github.io/lla-julie-communications-plan/` (original session `f43ebdba-3055-4d95-98f5-8baed7b8b701`)

### See also

- `entities/julie-gibson-clark`: plan recipient
- `projects/lla-ad-banner-campaign`: banner deliverables
- `projects/lla-julie-masterclass-video`: video system
- `projects/lla-julie-masterclass`: standalone masterclass launch
- `projects/lla-julie-masterclass-deck`: syllabus-based speaker presentation
- `projects/lla-julie-executive-social`: executive and faculty promotion


---

Record: `french-atelier-website` | knowledge last updated: 2026-10-24T10:14:00+00:00

## French Atelier Website

