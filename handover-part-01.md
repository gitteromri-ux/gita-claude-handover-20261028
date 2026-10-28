# GiTA complete operational handover to Claude

Prepared for Omri Gitter on 28 October 2026, Asia/Jerusalem. Primary reporting window: 28 September through 28 October 2026, with earlier dependencies and the recovered 24 September transfer preserved as historical context. Public operational transfer published at Omri's request. Credentials and personal email addresses are excluded.

## Read this first

This handover transfers the available working knowledge, decisions, implementation locations, access methods, dated evidence and unresolved work. It does not transfer credentials, grant permissions, launch campaigns, authorize CRM test orders, or certify historical assistant claims as facts. Read the current-state section before the chronological and project archives: older entries are intentionally retained and can be superseded.

Omri's explicit priority on 28 October is French Atelier Capsules ecommerce, plus the Longevity masterclass ecommerce and Blueprint ecommerce campaigns. He intends to reignite Blueprint today. That statement establishes business intent, not approval for this handover task to activate ads or change budgets.

### Evidence vocabulary

- **Fresh read:** Retrieved during this handover on 28 October 2026. A source-code read is not a production browser or payment test.
- **Recorded implementation:** Prior records contain a commit, deployment or tool receipt. Its date and scope matter.
- **Reported historical result:** An earlier assistant or summary says something happened; independent current outcome verification is absent.
- **User-approved:** An explicit user decision is recorded. Approval is scoped to the stated object and action, not neighboring work.
- **Unresolved:** Missing proof, conflicting source versions, unfinished acceptance, blocked access or a requested change without successful readback.
- **Superseded:** Earlier implementation, offer or recommendation kept for history; not the instruction for the next release.

Do not collapse source, deployment, UI rendering, successful API transport, actual paid enrollment, processor settlement, CRM fulfillment and Meta ad attribution into one “works” status. Each needs its own evidence. Likewise, a prepared email is not a sent email, a sent handoff is not an installed automation, and a published social hub is not a published social post.

## Current state at the handover cutoff

### Blueprint prices and the Pages.dev correction

The Pages.dev email destination was freshly read on 28 October. Its text now states regular tuition of $169 × 5 = $845; the JULIE249 / MASTERCLASS-VIP offer is $79 for month 1 plus four $169 payments = $755, a $90 first-month credit; a separate one-payment option remains $799. This replaces the earlier $179 × 5 / $149 × 5 figures quoted in this conversation on 27 October. The full offer was separately authorized in the evening of 27 October and must not be rolled back using the earlier chat answer. [Current Pages.dev offer](https://longevitylifeacademy.pages.dev/?enroll=1&code=MASTERCLASS-VIP).

The branded attendee page also now contains the $79 + four $169 / $755 offer and the November class choices. Its extracted text still includes legacy “$149 a month instead of $179,” a $99 VIP-masterclass value, and an upfront “save $96” statement; extraction can include hidden markup, so this is a content-consistency risk, not a claim that every phrase is visibly rendered. No pricing, copy or checkout code was changed during this handover. [Current branded attendee page](https://www.longevitylifeacademy.com/blueprint-attendees-7q4x/?code=JULIE249).

Recorded approval and implementation sequence:

- **27 October, 19:48 UTC / 21:48 Israel:** Omri explicitly requested Pages.dev pricing, installment, coupon and checkout parity with the attendee offer, for at least the next 48 hours. Original session record: `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`.
- **27 October:** The approved source schedule is associated with commit `ac35c2874e54bcc2b67f14beaff4ed8c900f9962` in `gitteromri-ux/lla-course-checkout`. Later class labels are commit `1eb51fef8d87c807986880f455ad6e27f176d929`; Pacific mobile-label repair is `6c27b2fff1d9bcaeeb8fb8687470ecc87b9b2de0`.
- **27 October, 20:15 and 21:10 UTC:** The displayed first-lesson choices were reconciled to Monday 23 November, 8 PM EST / 5 PM PST, and Wednesday 25 November, noon EST / 9 AM PST. Semester `2395`, classes `170275` and `170277`; do not relabel a semester start as a first lesson.
- **27 October, later review:** The main card showed the $169 strike-through and $79 first month, but the sticky control did not show the same savings comparison. Pacific text was found hidden at 375 px in a branded-page audit; a repair was pushed, with final branded publication/visual confirmation still open in the record.
- **Payment boundary:** No real payment or settlement was established by the price-parity audit. The last recorded request for a marked unpaid production QA order was not shown as approved. Page visits must not create orders.

### Production versus previews

| Surface | Role | Source / status rule |
|---|---|---|
| `longevitylifeacademy.pages.dev` | Maintained Blueprint ecommerce page and checkout; also destination of final post-event course emails | `gitteromri-ux/lla-course-checkout`; newly approved Standard offer, not a VIP preview |
| `www.longevitylifeacademy.com/blueprint-attendees-7q4x/` | Branded attendee course and question/callback experience | `Longevity-Academy/blueprint-attendees-7q4x`; not a directory in the main website repository |
| `gitteromri-ux.github.io/lla-masterclass-attendees/` | Older learning-first attendee clone | Historical $149 × 5 copy is not current pricing authority |
| `gitteromri-ux.github.io/lla-blueprint-vip-preview/` | Blueprint Standard/VIP comparison review | Payments and CRM writes disabled; no selected final VIP variant |
| `lla-blueprint-89-vip-preview.vercel.app` | Earlier VIP review | Older $189 recurring option; not current comparison authority |
| `www.longevitylifeacademy.com/julie-masterclass/` | Julie event registration | Separate production repo and protected Golden tracking chain |
| `www.longevitylifeacademy.com/masterclass-72hours/` | Separate community purchase clone | Preserve originating page and campaign in CRM; do not merge its orders into normal-page attribution without evidence |

These are working locators from the project record, not a claim that every historical endpoint was opened in this audit. Fresh fetches of the two current course surfaces are cited above; the repository inventory separately records which source trees were inspected.

### Email marketing: what the final handoff says versus what is installed

The final “Launch email for Chris” package's JM-U1 through JM-U4 point to Pages.dev with `MASTERCLASS-VIP`. The abandoned-checkout messages instead return to the Julie masterclass pricing section; they are event-ticket recovery, not the same course-conversion journey. The older email gallery and revised JM-X4 include different historical destinations and JULIE249 copy, so filename, package and branch must be named whenever discussing “the emails.” [Final Chris handoff](https://gitteromri-ux.github.io/lla-masterclass-emails-3tier/launch-email-for-chris/).

The previous live ActiveCampaign connector call failed with `TypeError: Invalid URL`. Consequently the handoff's URLs were verified, but Chris's installed production automation destinations were not certified by that check. The email/CRM section below records fresh access attempts and correspondence separately; do not tell Omri that every installed email has been audited unless the actual message bodies and links were retrieved.

### Masterclass Golden tracking and the Blueprint boundary

Julie campaign `52668266203628`, labeled `LGV_EN_PPC_ecomm-02_2026-09-02_#118149`, uses pixel `1440305917310328` and relay `lla-ac-events` at `/api/meta/capi`. The protected production source is `Longevity-Academy/julie-masterclass`, golden tag `tracking-golden-20260928`; the recorded relay deployment is `dpl_DQogoRsNj1XXTpJQmFrRk9zzCCrU`. These are historical contract identifiers, not a claim that the active deployment still matches them.

The documented freeze ran through 26 October and required an item-specific literal lift from Omri for protected tracking, payment, attribution and relay changes. Do not infer that an elapsed date, generic “go,” merged PR, or unrelated design approval clears every protection. Preserve the baseline and verify the intended authority before changing the chain.

Blueprint has not inherited Julie's paid-ad Purchase proof. The recorded challenge concerning CRM campaign `#116622`, roughly 390 AddToCarts and $11,689 spend with zero Meta purchases is an attribution investigation, not proof of zero real sales. The next Blueprint release must establish its own paid-ad click → preserved IDs → CRM order → payment → browser/server Purchase deduplication → attributed ad-set purchase chain.

### French Atelier Capsules

Omri's current focus is the two Capsules ecommerce campaigns, not blended language-course lead generation. His “main account” wording must not cause account-name substitution: recovered implementation evidence puts these campaigns in **French Atelier v2, `act_1358975119724184`**, distinct from the older French Atelier account `act_1188017096669618`. Live Meta authentication failed during this handover, so the Meta section supplies last-evidenced snapshots, not a fresh current-state certification.

Production bundle repair recorded paid order `8061644` for student `11682495`, with extra orders `8061645` and `8061646`; assignment responses support the two missing course assignments. Duplicate student cleanup, actual learner access, native bundle/financial structure, and a complete new paid-feed attribution test remain distinct unresolved issues. Sales were to remain open, not paused as a side effect of diagnosis.

The recurring language-course workbook excludes Capsules. The 19–25 October row-90 correction uses 821 leads, 237 contacted, 19 new registrations, 22 database registrations, 41 total registrations and 17 acquisitions; saved revenue/price/new-revenue results are $40,272.39 / $982.25 / $18,662.82. The weighted CPA/profit “x” cells and delivery to Gal remain separate gaps. These are recorded workbook figures, not a freshly reread spreadsheet in this handover.

### Event production and content

- **Decks:** Julie review, V45, V46 and the closing slide are separate release lines. V46 source/PPTX/order-lock existence does not prove presenter acceptance or that Julie's open tab is refreshed.
- **Runbook:** Team-facing chronological production guide preserves the original scripts. Recording is automatic; do not restore a manual “Courtney starts recording” instruction.
- **Live Q&A:** Frontend `gitteromri-ux.github.io/julie-live-qa/`; backend `julie-live-qa-api.gitter-omri.workers.dev`; Durable Object SQLite state and Workers AI answer drafts. Drafts require review before speaking; successful two-browser testing is not evidence of actual event use.
- **Social:** Executive/faculty, Julie's personal Instagram-only and official LLA Facebook/Instagram packages are distinct. A delivered caption/media hub does not prove actual posting or bio changes.
- **Rosters:** The October 26 signup population, current VIP-only Meshi roster, WhatsApp reminders and CRM Member ID versus StudentId equivalence were not fully resolved in the latest records.

## Instructions for Claude taking over

You are taking over active client operations, not starting a new strategy exercise. Reuse the existing artifacts and protect production. Omri wants direct answers, exact scope, fast execution, source fidelity and a working handoff, not explanations that substitute for action.

### Non-negotiable working rules

- **Read-only by default for this transfer:** No live changes have been authorized by the handover request. Existing scoped authorizations in historical tasks must be read in context rather than applied globally.
- **No secret transfer in documents:** Tokens, API keys, passwords, raw authentication headers and private meeting access tokens stay in their vaults/bindings. Do not paste them into chat, GitHub, logs or this handover.
- **No production QA without consent:** Creating an unpaid order, a test contact, a synthetic conversion or a staged ad is still a write. Opening a page must not create a lead automatically.
- **No fabricated proof:** Distinguish requested, applied, read back, published, tested, paid, settled and attributed. Do not quote a dashboard snapshot as current.
- **No unintended campaign changes:** Never activate Blueprint, change budgets, upload/export customer audiences, edit exclusions or delete duplicates merely because they are listed as next actions.
- **No CRM schema improvisation:** Sandra governs ActiveCampaign object changes; protected fields `214–220` must not be deleted. Narrow field updates are not permission to add lists/tags/fields.
- **Exact raw attribution:** Never lowercase, truncate, hash or regenerate an existing `fbclid`/`fbc`. Preserve original query parameters and match browser/server event identity.
- **Release safety:** Capture the baseline commit, active deployment and protected-file hashes; use a separate branch/preview; verify the full relevant device/checkout path; preserve rollback; publish only the approved scope.
- **Source fidelity:** Use the exact chosen copy, script, slide sequence and approved visual assets. Do not silently replace an accepted version with a similarly named derivative.
- **Reporting grain:** Use exact campaign/ad-set labels, dates, currencies, attribution windows and actual amounts. Revenue, lifetime contract value, first-payment cash, processor settlement and Meta purchase value are not interchangeable.
- **User interaction:** English or Hebrew; no filler, generic reassurance, pill-heavy generic design or unnecessary navigation instructions. Supply direct working links and ready-to-paste text.
- **Urgency:** Omri explicitly defines “fast” as urgent, normally a three-minute request. Keep the literal scope, act immediately, and do not spend the time on ceremonial planning. Do not promise a verification or deadline that the tools cannot support.
- **Longer work:** Give a realistic fixed work window and phase allocations, reserve a buffer, parallelize independent work, provide numeric progress, and audit before calling a deliverable complete. Do not cut scope or ask for extensions.

### Ready-to-paste takeover prompt

```text
Read this complete GiTA handover as my operational context. Start with the current-state and supersession sections, then the email/CRM/Golden tracking, Meta and repository sections. The dated project archive is history, not blanket authorization.

My priorities are the two French Atelier Capsules ecommerce campaigns in the main French account, and Longevity's masterclass and Blueprint ecommerce campaigns. I want to reignite Blueprint today, but first show the exact currently verified account/campaign/ad-set state and the remaining launch blockers without changing anything.

Preserve the Golden CAPI contract, raw click IDs, order-based deduplication, CRM/payment round trip, protected ActiveCampaign fields and existing production assets. Current Standard offer is $79 first month plus four $169 payments, $755 total, using JULIE249 or MASTERCLASS-VIP; upfront is separately $799. Do not adopt a preview VIP price.

Reuse existing sources, branches and artifacts. Distinguish historical claims from fresh readback and outcome proof. Never invent completion, never export credentials, and do not create production QA records, send messages, activate ads or deploy without the applicable scoped approval. Do the work directly with the connected tools rather than telling me to navigate.
```

## Access and continuity

The following is the access surface observed in this session, not a promise that the receiving Claude session automatically inherits every grant. Re-discover tools and list safe credential metadata in that session; do not ask Omri for a key that is already available through an approved connector or vault.

| System | Observed access path | Safe handover rule |
|---|---|---|
| GitHub | Authenticated `gh` and `git`; connector source `github_mcp_direct` | Use `gh repo view`, `gh api`, repository trees/commits/actions. Do not inspect credentials or run login/auth-status checks. Before an authorized commit, inspect repo author/committer identity and only fill missing local config from `gh api user`. |
| Meta Ads | Connector source `meta_ads`; authenticated `meta` CLI | Load `meta-ads-best-practices`; use connector quick reads or `meta-ads-cli` for CLI syntax. Select the exact ad account; auth availability must be tested, not assumed. |
| ActiveCampaign | `activecampaign__pipedream` | Inspect actual tool schemas. An installed connector can still have an account/base-URL configuration failure. Do not bypass missing authorization by scraping secrets from deployed code. |
| Gmail / Calendar | `gcal` tools for both services | Search correspondence with `gcal_search_email({queries:[...]})`, using sender and date filters; a search returns limited results and may require cursor paging. Preserve message IDs, dates, recipients and sent/received status. |
| Google Drive / Docs | `google_drive`, authenticated `gws` CLI | Read help for current commands; preserve original documents and make separate variants when required. |
| Cloudflare | Connected API-key service plus named vault credentials | Prefer service connector reads. For uncovered direct API operations use approved exact host-scoped handles; no raw token. |
| Vercel | Vault credential named `Vercel deploy token (lla-ac-events)`, host `api.vercel.com` | Inspect project/deployment metadata through the approved proxy, never secret environment values. A Vercel preview URL is not proof of production promotion. |
| Browser | Cloud browser available; local authenticated browser unavailable in this session | Do not claim access to the user's logged-in Meta/AC UI. A cloud browser has separate cookies and may be blocked. |
| Other connected services | GA, GTM, Wix, DocuSign, Facebook Pages, Deepgram, fal.ai, Replicate | Connection presence is not authorization for changes. Load the matching skill and discover the current operation schemas before use. |

Safe credential metadata freshly listed: Cloudflare deploy token (LLA), Cloudflare read-only Worker-tail credential, Vercel deploy token for `lla-ac-events`, and BrowserStack Automate hub credential. None of their values is included here. The direct-API pattern, where allowed, is `pplx credentials run <exact-listed-handle> -- <program> <arguments>`; use the returned handle unchanged and obey approval requirements.

### Useful read-only command patterns

```bash
gh repo view OWNER/REPO --json nameWithOwner,url,defaultBranchRef,isPrivate
gh api repos/OWNER/REPO/git/trees/BRANCH?recursive=1
gh api repos/OWNER/REPO/commits?per_page=20
gh run list --repo OWNER/REPO --limit 10
gh api repos/OWNER/REPO/pages
git -C CHECKOUT log -20 --date=iso --name-status
git -C CHECKOUT status --short
meta --help
gws --help
```

These are templates, not commands already run against every repository. Keep API JSON and response timestamps when doing a new audit; do not mistake a successful tree read for a working deployed website.

## Recovered earlier transfer

The original September handover was located, not recreated from memory. Project metadata identifies “GiTA Handoff: Omri full session + memory transfer,” project UUID `23b7f3a7-1551-40fd-85ad-d887f979379f`, created 24 September for the second GiTA Max user; this session retrieved its 42 listed project sessions and downloaded the original `README_HANDOFF.md` and `omri-memory-export-2026-09-24.zip` from the transfer session.

The original README describes a Brain wiki, notes, 25 Computer transcripts and 23 Search/Ask transcripts, with produced assets. Those are the README's inventory statements, not a claim that the September export contains all October work. The original archive is retained as a historical source; the current record and new live reads supersede stale operational conclusions.

The global `session_list(type="computer")` call returned no Computer sessions in this audit, while specific session loading and the earlier project's session listing worked. Therefore this handover does not claim an exhaustive export of every Perplexity conversation in the month. It includes the available project knowledge, dated daily records, recovered transfer material, inspected repositories and targeted original-session/correspondence evidence, with that discovery limitation explicit.

## How the rest of this file is organized

The next sections contain detailed specialist handovers for email/CRM/tracking, Meta and repositories, followed by the date-ordered daily record and every available current project knowledge entry. Project entries carry their recorded update date; the date is a knowledge-record timestamp, not necessarily the implementation or publication date.

A companion TSV lists inspected repository file paths. It is an inventory, not a byte-for-byte source-code export; file roles inferred from names are marked as such. Original source stays at the listed repository/commit, and generated media/releases may live outside the Git tree.



# Email, CRM, backend and Golden attribution

## Email, CRM and attribution handover
### Reporting window: 28 September–28 October 2026

Prepared 28 October 2026. READ-ONLY research: no emails sent, no automations modified, no CRM records created, no deployments or account settings changed. This document intentionally contains no credentials and no customer lists.

### Evidence standard and current decision

**Do not confuse a published email gallery with an installed automation, an email draft with a sent message, a CRM-paid order with settled revenue, or a Meta event receipt with an attributed sale.** These distinctions are essential in this project because the historical records repeatedly establish only one layer of the chain. [Golden tracking record](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md) [October 10 access and data gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)

Evidence labels used below:

- **CURRENT READ:** actually retrieved during this handover on October 28, including repository documents and email-query responses; retrieving an old document does not make its operational assertions current.
- **HISTORICAL ORIGINAL:** original conversation or dated repository handover read during this task.
- **WIKI SYNTHESIS:** curated memory, useful for the current trajectory but weaker than the underlying transaction or delivery receipt.
- **USER-STATED:** Omri's own description, not independently upgraded to a system receipt.
- **OPEN:** not established by the available evidence.

**Current live access finding:** a read-only call to `activecampaign__pipedream_activecampaign_list_campaigns({})` in this handover failed with `TypeError: Invalid URL at program.js:1:18`; consequently this task did not verify installed email bodies, automation status, schedules, send counts, or current AC deals. Evidence: current tool receipt, October 28, 2026.

This reproduces the failure documented in the original October 27 handoff-link inspection, rather than merely repeating a remembered error. Historical source: session `7f86bc26-cac2-4af5-8a69-13e059680d3d`, October 27 at 19:34 UTC. Original handoff inspection (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`)

### People, ownership and correspondence coverage

| Owner | Recorded remit | Boundary / evidence |
|---|---|---|
| Sandra Kwiecien | eTeacher copy approval and ActiveCampaign governance/access | New AC objects require Sandra; protected fields 214–220 must not be deleted without approval. [Checkout source](https://github.com/gitteromri-ux/lla-course-checkout) |
| Sandra / eTeacher, with `[email redacted for public handover]` named in the access handover | AC account URL and API access | October 10 handover names this access route; this is not proof that a credential is currently available to the new operator. [Access gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md) |
| Chris | AC import/deployment, dynamic session dates, Zoom/LMS values and reminders | GitHub updates do not propagate into AC; the October 18 message requests Chris's confirmation before sending. Original Chris handoff (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) |
| Omri | Offer/content approval and protected-release authorization | Freeze exception required an item-specific sentence, not a generic approval. [Freeze contract](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md) |
| Anant / eTeacher | CRM campaign/ad-group identifiers and CRM reporting | Static `adGroupID` belongs to eTeacher CRM attribution; it is not the Meta ad-set ID. [October 9 technical handover](https://github.com/gitteromri-ux/handover-master/blob/main/julie-masterclass-handover-2026-10-09.md) |
| eTeacher finance | Airwallex/PayPal settlement and refund verification | No complete order-to-processor settlement truth table was captured in the October 10 handover. [Data gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md) |

#### What was actually searched now

Gmail searches included date-bounded `Sandra`, `Chris`, and sent-masterclass queries for September 28–October 28, then `from:Sandra`, `to:Sandra`, `from:Chris`, `to:Chris`, `Kwiecien`, `"Launch email for Chris"`, `"LGV"` and `"masterclass"`. Evidence: current `gcal_search_email` receipts, October 28.

**No relevant direct Sandra or eTeacher-Chris correspondence was returned by those searches.** The broad name query returned unrelated September 17 mail from Chris at 10words and TinyLaunch, which was excluded; therefore this is an evidence-coverage gap, not a claim that no correspondence exists. Evidence: current Gmail query results.

The October 10 handover states that the eTeacher work mailbox `[email redacted for public handover]` had never been connected and that Sandra/other stakeholder WhatsApp history had not been accessible; those are dated access limitations, not a fresh test of those channels. [October 10 access gaps](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)

The October 18 original session also explicitly says the actual message to Chris could not be found in Gmail; its suggestion that it might have been sent via WhatsApp was speculation, not delivery evidence. Original October 18 correspondence record (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

#### Sent-status ledger

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

