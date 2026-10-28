# Immediate operator takeover: connections, infrastructure and acceptance

Updated 28 October 2026. This is the first document the receiving Claude should read, followed by the complete handover parts. Omri is transferring operations immediately for a tool RFP; do not ask him to repeat the history or refer him back to the previous assistant.

## Mandatory: independently retrieve the past month of Meta history

**This handover does NOT include a complete one-month Meta Ads history. Claude must retrieve and check it directly before making campaign decisions or changes.** The existing record contains partial dated snapshots and recovered instructions, not a complete Meta activity/change log or daily performance export.

Cover 28 September–28 October 2026 for French Atelier Capsules in its recorded operating account and for Longevity's masterclass and Blueprint campaigns. Check campaign/ad-set/ad changes, budget and status changes, targeting, creatives, destination URLs and daily performance. Record the account timezone, exact date boundaries and attribution settings; reconcile the results against this handover. Missing entries are not evidence that nothing changed. If authorization or retention prevents a complete check, report the precise gap and do not claim full-month verification.

## What transfers and what does not

The linked files contain the recovered operational knowledge, historical decisions, account and project identities, source map, connection procedures, email handoffs and known failure boundaries. They do not contain secret credentials, inherit connector permissions, or magically repair invalid authentication. A receiving agent must use its own available connected session/vault grants.

Live-access failure is a documented state to take over, not a reason to discard the handover. Historical API snapshots remain dated. Do not call the transfer an exhaustive original-transcript export or every live service verified: neither was achieved.

## Receiving Claude's first actions

1. Read this addendum and `handover-part-01.md`, then all remaining handover parts in sequence. Use the index's raw text links; opening the index alone is not ingestion of its linked content.
2. Discover available tools for GitHub, Meta, ActiveCampaign, Gmail, Drive, Cloudflare and Vercel. The source IDs and commands below are the recorded entry points, not guaranteed schemas in a new session.
3. Run read-only account/source checks using existing grants. Do not create production contacts/orders, activate campaigns, upload customer audiences, change deployments or send messages.
4. Report operational readiness per service as connected and read-verified, authorization blocked, configuration failed, or historical-only. Preserve returned timestamps, IDs and exact error messages.
5. Prioritize the two Capsules ecommerce campaigns, the Julie masterclass ecommerce campaign and Blueprint ecommerce restart preparation. Do not blend lead-generation reporting into these scopes.
6. Use the repository TSV to locate exact files and branches. Private upstream repositories may need authenticated `gh`, but their architecture and recovered operational content are embedded in this public handover.

## Connection matrix and concrete entry points

### GitHub

Recorded owner `gitteromri-ux`; production organization `Longevity-Academy`. Authenticated `gh` and `git` were available to the originating Perplexity session. Prefer those CLIs to connector writes. Test a known repository read, not `gh auth status`, credential inspection or login.

```bash
gh repo view gitteromri-ux/lla-course-checkout --json nameWithOwner,defaultBranchRef,isPrivate,url
gh api repos/Longevity-Academy/julie-masterclass/commits?per_page=1
gh api repos/Longevity-Academy/julie-masterclass/pages
gh run list --repo Longevity-Academy/julie-masterclass --limit 5
```

Do not infer source parity from a successful repository read. A later authorized commit must preserve existing author/committer configuration; check it before writing. Personal mirrors, production organization repos, GitHub Pages branch selection and Cloudflare `dist/` deployment selection are documented separately.

### Meta Ads

Recorded connector source `meta_ads`; authenticated CLI name `meta`. Load `meta-ads-best-practices`, and `meta-ads-cli` before CLI work. The originating session's live read failed with authentication error 190; discovery independently reported DISCONNECTED.

Receiving-session recovery: discover `Meta Ads`, use the canonical returned connector ID, and request reauthorization through `connect_connector` only when required. Wait for authorization completion before dependent reads. Never obtain a token from source files or ask for one in ordinary chat.

```bash
meta --output json ads adaccount list
meta --output json ads --ad-account-id act_1358975119724184 campaign list
meta --output json ads --ad-account-id act_1358975119724184 adset list
meta --output json ads --ad-account-id act_1459085242361281 campaign list
meta --output json ads --ad-account-id act_1459085242361281 adset list
```

- Capsules operating account: `French Atelier v2`, `act_1358975119724184`; older distinct French account `act_1188017096669618`.
- Longevity account: `act_1459085242361281`.
- Julie campaign: `52668266203628`, `LGV_EN_PPC_ecomm-02_2026-09-02_#118149`.
- Blueprint campaign: `52663511211628`, `LGV_EN_PPC_ecomm-01_2026-09-02_#118148`.
- Capsules sets: `120251212250640546` / CRM `108761`; `120251212251230546` / CRM `108758`; `120251212251670546` / CRM `108757`.
- Full Capsules Meta campaign IDs must be obtained from returned ancestry. CRM campaign labels `116980` and `116939` are not Graph campaign IDs.
- LLA pixel: `1440305917310328`; Capsules ecommerce pixel: `4075596186030950`. Do not substitute the separate FA dataset `4400286150281912`.

The last recorded Julie action paused Set 03 only; requested budget changes were not applied. This is not a current campaign-wide pause receipt. The historical tables in the main document provide exact dates and amounts.

### ActiveCampaign and CRM deals

Recorded connector source `activecampaign__pipedream`; account API host `eteachergroup.api-us1.com`; authentication header name `Api-Token`. Header value is intentionally excluded. The actual list-campaigns call returned `TypeError: Invalid URL`; the source evidence does not independently establish the root cause.

Discover the connector and inspect the real schemas for campaign listing, deal search/get, contact get and relevant field reads. Inspect the nonsecret base/account URL configuration through supported connection setup; reconnect if needed. A historical browser/header route and project-specific saved-access route existed, but do not extract secrets from Vercel or source code to recreate them.

For direct HTTPS API operations not covered by a functioning connector, load `custom-credentials`, list credentials first, use an exact approved host-scoped handle, and obey its approval policy. Never invent an AC handle or reuse a credential for another host.

Deal retrieval contract:

1. Read the actual field model and supported pagination/order/filter parameters.
2. Paginate to completion with stable order; deduplicate by deal ID and reconcile returned totals.
3. Qualify by product/campaign and paid/won status; separate test/internal, unpaid, sync exceptions and unresolved records.
4. Retain order ID, contact relationship, amount/currency and relevant timestamps privately.
5. Contact field `187` is the recorded Ad ID lookup. Resolve its Meta ad-set ancestry using current reads or label the saved mapping date.
6. Paid order count, unique buyers, processor settlement, refunds and attributed Meta purchases are separate metrics.
7. Keep customer exports private. This public handover intentionally excludes raw customer lists.

Sandra governs new ActiveCampaign objects. Protected fields `214–220` cannot be deleted without approval. Existing-contact abandonment writes use `LGV_checkout_events`, field `206`; Regular/VIP segmentation uses `LGV_Product_Event`. Do not add fields, lists or contacts as an improvised connector repair.

### Vercel

Historical team: GITTER / slug `gitter1`; team ID `team_QsIIEvdvnmtyD40s3mcnka6k`. The recovered project inventory is dated **10 October**, not a fresh control-plane listing.

| Project | Recorded project ID | Operational role |
|---|---|---|
| `lla-ac-events` | `prj_3v7g4Xwve6OmXrcPCVQOWJOiN2SK` | LLA AC event relay and Meta CAPI |
| `fa-leads-proxy` | `prj_byAoWWUN5aXdGDrGRb7PJ25hINlI` | French lead/ecommerce relay, AC and Meta routes |
| `fa-staging-checkout` | `prj_xluo8z01uYC5bnbHzgWZpxVozk6I` | Staging checkout, not production |
| `fa-staging-light` | `prj_VL9P72MT1ZQ5nsb6rdbITX90BzED` | Staging page, not production |

Recorded live browser route for LLA CAPI is `https://lla-ac-events.vercel.app/api/meta/capi`; the historical team inventory also lists `https://lla-ac-events-gitter1.vercel.app`. Verify actual project aliases and the browser's configured endpoint before choosing an alias. French browser source points to `https://fa-leads-proxy.vercel.app`.

The originating session listed a vault credential named `Vercel deploy token (lla-ac-events)` for `api.vercel.com`; the value is not transferred. In the receiving session, load `custom-credentials`, call `list_credentials`, and use only the exact allowed handle returned. If absent or approval-required, establish that specific access via the secure flow.

Read project/deployment/alias metadata with the intended team scope. Compare the production deployment, ready state, aliases, source commit and golden baseline. Do not read or print secret environment values. Historical Vercel runtime-log reads returned 403; this does not establish that current project metadata access is also unavailable.

### Cloudflare

Recorded connector source `cloudflare_api_key__pipedream`. The originating vault listed an LLA Cloudflare deploy credential and a separate read-only Worker-tail credential; exact permissions and handles must be re-listed, not inferred from their names.

- Pages project `longevitylifeacademy`: `https://longevitylifeacademy.pages.dev/`.
- Static Worker `lla-checkout`: `wrangler.static.toml` publishes `dist/`.
- CRM integration Worker `eteacher-leads-proxy`: `https://eteacher-leads-proxy.gitter-omri.workers.dev`.
- Q&A backend `julie-live-qa-api`: `https://julie-live-qa-api.gitter-omri.workers.dev`.
- Repository `gitteromri-ux/lla-course-checkout` has `worker/src/index.js`, `dist/_worker.js` and `capi-relay/`; these are distinct components.

Read account/project/worker/deployment metadata through supported connector tools first. Use approved direct API credentials only for uncovered operations. Do not print Worker secrets, republish an old snapshot, or confuse a Pages deploy with a Worker deploy. The preserved French relay still contains an older forced ProductID behavior; later operational history says it changed, so source snapshot is not safe to redeploy as current.

### Gmail, Drive and stakeholder history

Recorded Gmail/Calendar tool source is `gcal`; Drive source is `google_drive`, with authenticated `gws` CLI. Use current schemas and pagination. Direct Sandra/eTeacher-Chris emails did not appear in the connected-mailbox queries; the eTeacher work mailbox and WhatsApp were historical access gaps.

The document therefore preserves the exact recovered Chris handoff requirements and original transcript evidence, while distinguishing prepared copy, user-described delivery, confirmed sent receipts and installed AC changes. Do not replace that distinction with “everything sent.” The final email-package source does not automatically update installed ActiveCampaign messages.

## Immutable tracking and commerce contract

- Preserve the raw case-sensitive `fbclid` and derived `fbc`; use `_fbp` consistently.
- Browser event ID equals server event ID. Purchase identity is order-bound and fires on successful Airwallex payment or PayPal capture, not mere page load or order creation.
- Preserve campaign/ad-group URL parameters across page, order, payment and return. Static CRM ad-group labels are not Meta ad-set IDs.
- Keep QA/staging test events out of production reporting. No synthetic Purchase or new production QA order without scoped approval.
- Treat the September Julie golden transaction as a bounded baseline. It does not certify Blueprint or French Capsules.
- The historical protected period ended October 26; expiration is not blanket approval to alter protected production. Use the user's actual scoped authorization.
- Keep paid primary order, extra-course assignment, learner access and native bundle financial relationships separate in Capsules.
- Keep the current Standard price $79 + four $169 = $755 separate from preview VIP alternatives, old $149 pricing, and upfront $799.

## Specific readiness gates the receiving operator owns

| Gate | Evidence currently available | Required next proof |
|---|---|---|
| Meta live state | Historical IDs/configuration; fresh auth failure | Successful exact-account campaign/ad-set read with timestamps |
| ActiveCampaign installed emails | Final source packages, mappings and historical handoffs | Actual production message bodies/links plus automation/send state |
| CRM current sales | Historical extraction method and attribution fields | Fresh paginated paid-order reconciliation |
| Vercel/Cloudflare current release | Source and historical project/deployment map | Control-plane production deployment read and source comparison |
| Blueprint restart | Offer parity record and owner intent | Current campaign configuration plus separate attribution/payment acceptance; explicit activation approval |
| Capsules fulfillment | Recorded assignment responses | Buyer entitlement/access and order/payment reconciliation |
| Complete communication history | Recovered transcripts and sent-status ledger | Any missing mailbox/WhatsApp records from authorized source |

These gates do not require the previous assistant. They tell the receiving operator exactly where knowledge ends and live verification begins.


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

- **Repository:** [gitteromri-ux/french-atelier-lifecycle-emails](https://github.com/gitteromri-ux/french-atelier-lifecycle-emails); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `master`.
- **Inventory:** 137 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `118f6d4b0e6e781b864a8d53b2109ffbb904d009`; 2026-10-07T08:20:37Z; Fix: restore class attributes in Capsules tier, FA logo URL, hero image per stage.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-lifecycle-emails/; build type `legacy`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `FACTS.md`, `README.md`, `assets`, `emails`, `index.html`, `journeys.html`, `launch-email-for-chris`.

### gitteromri-ux/french-atelier-onboarding

- **Repository:** [gitteromri-ux/french-atelier-onboarding](https://github.com/gitteromri-ux/french-atelier-onboarding); private.
- **Purpose:** French Atelier by Acadomia: complete onboarding & nurture package (8 emails, 2 landing pages, WhatsApp, 2 Typeform quizzes, hero imagery, mockups). Brand-aligned with Caitlin design system.
- **Branches inspected:** `main`.
- **Inventory:** 106 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `7637c5990a3349e0e900684fa5440ee199c76b51`; 2026-10-13T14:57:52Z; LP trial CTA anchors to the live pricing page advisor form (#talk-to-advisor).
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `00_MASTER_INDEX.md`, `README.md`, `assets`, `build_emails.py`, `emails`, `images`, `images_old_backup`, `images_v2`, `index.html`, `landing-pages`, `landing-pages-delivery.html`, `lp-images.html`, `mockups`, `scripts`, `typeform`, `whatsapp`.

### gitteromri-ux/french-atelier-social-kickstart

- **Repository:** [gitteromri-ux/french-atelier-social-kickstart](https://github.com/gitteromri-ux/french-atelier-social-kickstart); public/visibility not independently specified.
- **Purpose:** French Atelier · Organic Social Kickstart · Sept and Oct 2026
- **Branches inspected:** `main`.
- **Inventory:** 355 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `dcdaae20c720b32e81b919f777a7a32c30582aec`; 2026-09-16T21:57:20Z; Add 4:5 RTM images for Sprout drafts.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-social-kickstart/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.nojekyll`, `README.md`, `audit`, `audit.html`, `brand`, `capsules`, `css`, `deck.html`, `emails`, `emails_real`, `heroes`, `ig_posters`, `ig_rtm`, `index.html`, `js`, `manual.html`, `posters`, `rtm`, `sprout`, `videos`, `videos_web`.

### gitteromri-ux/french-atelier-wa-ret-acq

- **Repository:** [gitteromri-ux/french-atelier-wa-ret-acq](https://github.com/gitteromri-ux/french-atelier-wa-ret-acq); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 33 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `b18cd33ceae742c838abf089c4e967a25933b415`; 2026-08-06T10:32:45Z; Clarity pass: explicit-subject headers, brand line in every WA body, clearer LP H1s.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-wa-ret-acq/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `index.html`, `landing-pages`, `whatsapp`.

### gitteromri-ux/french-atelier-website

- **Repository:** [gitteromri-ux/french-atelier-website](https://github.com/gitteromri-ux/french-atelier-website); public/visibility not independently specified.
- **Purpose:** French Atelier: full website mockup (CEO review June 2026)
- **Branches inspected:** `claude/frenchatelierlive-audit-ngzmjo`, `main`.
- **Inventory:** 33 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `30c7323ded30eadda4ac85857ec6857765be1167`; 2026-10-13T14:57:31Z; Fix: Reserve-your-seat CTA now points to www.frenchatelierlive.com/pricing.html.
- **Pages configuration:** https://gitteromri-ux.github.io/french-atelier-website/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `README.md`, `_headers`, `audit`, `favicon.svg`, `images`, `index.html`, `robots.txt`, `style.css`, `videos`.

### gitteromri-ux/gita-machine

- **Repository:** [gitteromri-ux/gita-machine](https://github.com/gitteromri-ux/gita-machine); public/visibility not independently specified.
- **Purpose:** Gita Machine: organic reach at machine scale
- **Branches inspected:** `main`.
- **Inventory:** 6 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `115a147ad44e5143384257173f3a98465411e8d9`; 2026-09-17T17:31:31Z; Gita Machine v1.
- **Pages configuration:** https://gitteromri-ux.github.io/gita-machine/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `app.css`, `app.js`, `data`, `favicon.svg`, `index.html`.

### gitteromri-ux/hana

- **Repository:** [gitteromri-ux/hana](https://github.com/gitteromri-ux/hana); public/visibility not independently specified.
- **Purpose:** Hana: a professional 108-item Enneagram assessment with full type and wing analysis
- **Branches inspected:** `gh-pages`, `master`.
- **Inventory:** 30 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `d58096e05b627363106ebc84572048d2a663fd45`; 2026-07-23T14:54:52Z; Update site branding and content.
- **Pages configuration:** https://gitteromri-ux.github.io/hana/; build type `legacy`; source `{'branch': 'gh-pages', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.oxlintrc.json`, `404.html`, `README.md`, `assets`, `compat-7w8-4w3`, `favicon.svg`, `icons.svg`, `index.html`, `package-lock.json`, `package.json`, `public`, `src`, `tsconfig.app.json`, `tsconfig.json`, `tsconfig.node.json`, `vite.config.ts`.

### gitteromri-ux/handover-instinct-grok

- **Repository:** [gitteromri-ux/handover-instinct-grok](https://github.com/gitteromri-ux/handover-instinct-grok); public/visibility not independently specified.
- **Purpose:** Private master handover 2026-10-10 for Instinct / Grok Bot (Omri Gitter / Gita Agency)
- **Branches inspected:** `main`.
- **Inventory:** 32 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `06d883b7aab88f3cf1e85052c326fb413db6d8ac`; 2026-10-11T09:34:33Z; GROKBOT: Meta read-only token (3c).
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `GAPS.md`, `GROKBOT.md`, `INSTINCT.md`, `MASTER-HANDOVER-2026-10-10.md`, `README.md`, `SETUP-GUIDE.md`, `SIMPLE-SETUP.md`, `VERCEL-PROJECTS.md`, `_global-rules.md`, `_today-log.md`, `julie-masterclass-handover-2026-10-09.md`, `projects`, `rules`, `snapshots`.

### gitteromri-ux/handover-master

- **Repository:** [gitteromri-ux/handover-master](https://github.com/gitteromri-ux/handover-master); public/visibility not independently specified.
- **Purpose:** MASTER HANDOVER: every active project, link, rule, and asset. Compiled 2026-09-01 for cross-subscription continuity.
- **Branches inspected:** `audit/julie-cpm-rule-20260929`, `log/approved-browser-repair-20260926`, `main`, `recovery/w46b-p2-log`.
- **Inventory:** 322 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `3a13ed815cbbd67e52742282ef94395c46fc7b34`; 2026-10-20T13:20:15Z; French Atelier e-commerce launch: full handover 2026-10-20.
- **Pages configuration:** https://gitteromri-ux.github.io/handover-master/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `HANDOVER.md`, `_global-rules.md`, `_inventory.md`, `_source-read-manifest.md`, `_supporting-knowledge.md`, `_today-log.md`, `data`, `julie-masterclass-handover-2026-10-09.md`, `projects`.

### gitteromri-ux/harel-brief

- **Repository:** [gitteromri-ux/harel-brief](https://github.com/gitteromri-ux/harel-brief); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 2 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `a0ead739af4121e621a024b9ba85c4db257434fa`; 2026-10-26T12:22:51Z; Update all: corrected sign-ups 26 Oct 14:21.
- **Pages configuration:** https://gitteromri-ux.github.io/harel-brief/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `index.html`.

### gitteromri-ux/harel-weekly-oct26

- **Repository:** [gitteromri-ux/harel-weekly-oct26](https://github.com/gitteromri-ux/harel-weekly-oct26); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 2 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `06498dd26b63d8b206f1b9cdcd7acdc883ebd79d`; 2026-10-26T12:23:08Z; Remove links section.
- **Pages configuration:** https://gitteromri-ux.github.io/harel-weekly-oct26/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `index.html`.

### gitteromri-ux/iching-reading

- **Repository:** [gitteromri-ux/iching-reading](https://github.com/gitteromri-ux/iching-reading); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `master`.
- **Inventory:** 2 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `b04c62a1c955aa86477fc0fd1d692bd96b23bb9f`; 2026-10-19T17:47:20Z; full reading tab 2.
- **Pages configuration:** https://gitteromri-ux.github.io/iching-reading/; build type `workflow`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `index.html`, `tab2.html`.

### gitteromri-ux/in-venture-programme

- **Repository:** [gitteromri-ux/in-venture-programme](https://github.com/gitteromri-ux/in-venture-programme); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 6 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `a5ae388c79453e1be0d363917b4b5e19125fb51e`; 2026-08-09T11:22:49Z; Enable typing in all grey boxes with autosave.
- **Pages configuration:** https://gitteromri-ux.github.io/in-venture-programme/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `IN_Venture_Interview_ForceManagement.docx`, `IN_Venture_Partner_Interview-2.docx`, `index.html`, `interview-1.html`, `interview-force-management.html`, `plan.html`.

### gitteromri-ux/in-venture-website

- **Repository:** [gitteromri-ux/in-venture-website](https://github.com/gitteromri-ux/in-venture-website); public/visibility not independently specified.
- **Purpose:** IN Venture premium website rebuild by Gita Agency
- **Branches inspected:** `main`, `master`.
- **Inventory:** 96 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `7ff5f33b02a79a9c99daa80448070e108fd2e63b`; 2026-09-01T10:23:57Z; Premium design overhaul v2: Playfair Display, brand-true dark keynote system, all 6 original pages.
- **Pages configuration:** https://gitteromri-ux.github.io/in-venture-website/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `README.md`, `about.html`, `contact.html`, `css`, `firm.html`, `img`, `index.html`, `insights.html`, `js`, `legal.html`, `portfolio.html`, `position.html`, `quantum-computing.html`, `roadmaps.html`, `team.html`, `value-creation.html`.

### gitteromri-ux/julie-500-launch-plan

- **Repository:** [gitteromri-ux/julie-500-launch-plan](https://github.com/gitteromri-ux/julie-500-launch-plan); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `backup/20260927-1027-ceo-chart`, `main`.
- **Inventory:** 39 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `dc04f88879c475a910cba6e294aca0fde36897d9`; 2026-10-19T23:12:38Z; eTeacher growth plan v12: redesign with image and video assets, same numbers.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-500-launch-plan/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `acquisition-plan.html`, `assets`, `daily-log.js`, `eteacher-growth-plan.html`, `index.html`, `research.md`, `versions`.

### gitteromri-ux/julie-ads

- **Repository:** [gitteromri-ux/julie-ads](https://github.com/gitteromri-ux/julie-ads); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 72 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `c2de4eb03173c39baaf2e2a93e97c2f729cd7361`; 2026-10-16T14:57:34Z; fresh-oct16 v3: 10-12s music-driven cuts.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-ads/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `brand.md`, `directions`, `download`, `fresh-oct16`, `index.html`, `png`, `reels`, `reels-concepts`.

### gitteromri-ux/julie-ceo-daily

- **Repository:** [gitteromri-ux/julie-ceo-daily](https://github.com/gitteromri-ux/julie-ceo-daily); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 26 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `fa98649634e8d393db3fe4e6934de88cc2f1fa26`; 2026-10-26T12:24:11Z; Corrected CRM sign-ups across all tabs (bookstore removed).
- **Pages configuration:** https://gitteromri-ux.github.io/julie-ceo-daily/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `chart-2026-10-17.html`, `chart-fr.html`, `index.html`, `qa-checkout-2026-10-25`.

### gitteromri-ux/julie-ceo-launch-report

- **Repository:** [gitteromri-ux/julie-ceo-launch-report](https://github.com/gitteromri-ux/julie-ceo-launch-report); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 114 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `5e3c4dec9434373dc63ab7a05b0cad1664075ece`; 2026-10-22T16:03:09Z; Audience slide 1: headline trimmed.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-ceo-launch-report/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `README.md`, `assets`, `audience-2026-10-22`, `board-audience-2026-10-22`, `board-deck-2026-10-06`, `ceo-morning-briefing-2026-10-05.md`, `executive-summary-2026-10-05.md`, `index.html`, `today.html`, `weekly-2026-10-06`.

### gitteromri-ux/julie-daily

- **Repository:** [gitteromri-ux/julie-daily](https://github.com/gitteromri-ux/julie-daily); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 1 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `f6b8fb06d101c86e3cea259f8e1b6eb8efd4609b`; 2026-10-11T14:07:17Z; tighter mobile table.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-daily/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `index.html`.

### gitteromri-ux/julie-groups-uplift

- **Repository:** [gitteromri-ux/julie-groups-uplift](https://github.com/gitteromri-ux/julie-groups-uplift); private.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `master`.
- **Inventory:** 22 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `a9ba890d94d4993d14d76931a8948719f892a168`; 2026-09-30T12:40:16Z; v2: 115 groups / 6.42M, scheduler, post format (link line 2 + share cards), 38 partners.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `build.py`, `build2.py`, `groups.json`, `index.html`, `links.csv`, `lla-go`, `research`, `share-cards`.

### gitteromri-ux/julie-launch-review-20260923

- **Repository:** [gitteromri-ux/julie-launch-review-20260923](https://github.com/gitteromri-ux/julie-launch-review-20260923); private.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `review`.
- **Inventory:** 312 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `ddd0838015f5a8f3c43c76c072a4eb2908fe3bf7`; 2026-09-24T11:09:13Z; AC relay: write LGV_Masterclass_Session_Date as YYYY-MM-DD (field is now a Date field; Chris 2026-09-24); deployed to lla-ac-events.vercel.app dpl_EPnkKzboNGiXLhYUwap9fcxoFWj8.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `Chris-Agreements-Acceptance-Checklist.md`, `DELIVERY-2026-09-24.md`, `FULL-SCOPE-STATUS-2026-09-24.md`, `Julie-Launch-Control-Register.md`, `README.md`, `Sandra-Chris-Targeted-Email-Amendments.md`, `ac-product-test-results.json`, `blueprint-verification`, `build-delivery.cjs`, `build-private-preview.cjs`, `candidate-source`, `cf_pages_deploy.py`, `checkout-browser-results.json`, `checkout-failure-path-results.json`, `crm-price-test-results.json`, `email-revision`, `julie-payment-verification`, `offline-fixture.js`, `patches`, `private-preview-mobile.png`, `private-preview-verification.json`, `review-home.html`, `test-ac-product-contract.cjs`, `test-checkout-browser.cjs`, `test-checkout-failure-paths.cjs`, `test-crm-price-contract.cjs`, `test-private-preview.cjs`.

### gitteromri-ux/julie-live-qa

- **Repository:** [gitteromri-ux/julie-live-qa](https://github.com/gitteromri-ux/julie-live-qa); public/visibility not independently specified.
- **Purpose:** Julie Masterclass live moderator Q&A desk
- **Branches inspected:** `main`.
- **Inventory:** 3 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `9d15e1b2d0e9643c849a69d599d4da2a76ca6263`; 2026-10-26T13:29:40Z; Keep queue syncing during speaker timer.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-live-qa/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `config.js`, `index.html`, `questions.json`.

### gitteromri-ux/julie-masterclass-3tier

- **Repository:** [gitteromri-ux/julie-masterclass-3tier](https://github.com/gitteromri-ux/julie-masterclass-3tier); private.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `master`.
- **Inventory:** 78 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `eb64ca514c44279281c516ca2c3a8081040f82d2`; 2026-09-17T09:25:14Z; 3-tier pricing + full checkout + floater fix + Oct/Nov dates.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `assets`, `index.html`, `vercel.json`.

### gitteromri-ux/julie-masterclass-blast

- **Repository:** [gitteromri-ux/julie-masterclass-blast](https://github.com/gitteromri-ux/julie-masterclass-blast); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `master`.
- **Inventory:** 69 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `6df81d9a9298cbd38a93d20533474560856cb791`; 2026-10-18T13:56:18Z; Approved IIBS v4 copy for every segment; dedicated direct-access gallery; preserve all launch corrections.
- **Pages configuration:** https://gitteromri-ux.github.io/julie-masterclass-blast/; build type `legacy`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `assets`, `iibs`, `index.html`, `lla`, `rosen`, `text`.

### gitteromri-ux/julie-masterclass-live

- **Repository:** [gitteromri-ux/julie-masterclass-live](https://github.com/gitteromri-ux/julie-masterclass-live); private.
- **Purpose:** Write mirror of Longevity-Academy/julie-masterclass: push here, the org repo syncs and deploys GitHub Pages
- **Branches inspected:** `backup/20260927-1708-tracking`, `backup/20260927-julie-before-promotion`, `backup/20260927-julie-tracking`, `backup/20260928-0035-capi-timing`, `change/20260929-hero-desktop`, `change/20260930-checkout-continue`, `change/20260930-desktop-pricing-compact`, `change/20260930-pricing-copy`, `change/20260930-remove-backup`, `change/20261001-hero-pricing-polish`, `change/20261001-phone-readability`, `change/20261001-vip-hero-colors`, `change/20261009-mobile-compact-checkout`, `fix/julie-attribution-20260927`, `fix/julie-capi-timing-20260928`, `fix/julie-tracking-20260927`, `fix/julie-tracking-current-20260927`, `fix/mobile-header-20260928`, `main`.
- **Inventory:** 2,101 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `058c1f0e33e96d9140e23b4ed0f1c8eb91608d0e`; 2026-10-09T14:41:29Z; Pay button min-height 52px (matches the site's 52-56px controls). Appearance rule only..
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `assets`, `index-v50-backup.html`, `index.html`, `privacy.html`, `support`.

### gitteromri-ux/julie-masterclass-social-posts

- **Repository:** [gitteromri-ux/julie-masterclass-social-posts](https://github.com/gitteromri-ux/julie-masterclass-social-posts); private.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 1 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `9e5bf059bb2d6b50b65dd0f6e46080f079259137`; 2026-10-22T09:27:59Z; Three voices x three platforms: CEO, management, faculty.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `README.md`.

### gitteromri-ux/kerenor-adoption-en

- **Repository:** [gitteromri-ux/kerenor-adoption-en](https://github.com/gitteromri-ux/kerenor-adoption-en); public/visibility not independently specified.
- **Purpose:** Keren Or Farm: English adoption page with 33 animal profiles
- **Branches inspected:** `master`.
- **Inventory:** 341 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `9c50ea4dc5c24e6ca078572b1008021a5229849b`; 2026-07-14T10:08:51Z; Packages: neon glowing CTAs, bonus grid + badges (VIP), monthly pricing, bold key phrases.
- **Pages configuration:** https://gitteromri-ux.github.io/kerenor-adoption-en/; build type `legacy`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `README.md`, `adopt`, `animals`, `build.py`, `download_assets.py`, `download_images.py`, `gallery_map.json`, `images`, `index.html`, `photo_counts.json`, `reveal.js`, `source_data.json`, `source_text.txt`, `style.css`, `translations.json`.

### gitteromri-ux/latest-meta-ads

- **Repository:** [gitteromri-ux/latest-meta-ads](https://github.com/gitteromri-ux/latest-meta-ads); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 11 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `ef0150aab65731eb3ad9c9da13f1db1458f81efa`; 2026-10-20T17:53:09Z; remove empty page.
- **Pages configuration:** https://gitteromri-ux.github.io/latest-meta-ads/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `index.html`, `videos`.

### gitteromri-ux/lawsuit

- **Repository:** [gitteromri-ux/lawsuit](https://github.com/gitteromri-ux/lawsuit); public/visibility not independently specified.
- **Purpose:** Service performance audit: documented ETA, scope, status-accuracy and compute-waste findings across Gita Agency engagements (Jun-Aug 2026)
- **Branches inspected:** `main`.
- **Inventory:** 543 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `150f5e181a334b12ac0dc96da39713efa0eaa7fa`; 2026-10-26T10:29:37Z; CLAIM-0461: guest signup falsely reported verified while redemption field hidden.
- **Pages configuration:** https://gitteromri-ux.github.io/lawsuit/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.github`, `.nojekyll`, `EXTRACTION_SPEC.md`, `NOTICE.md`, `README.md`, `assets`, `build.py`, `cases`, `counter.html`, `data`, `evidence`, `index.html`, `scripts`, `source`.

### gitteromri-ux/lla-blueprint-vip-preview

- **Repository:** [gitteromri-ux/lla-blueprint-vip-preview](https://github.com/gitteromri-ux/lla-blueprint-vip-preview); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 20 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `4b11700532f06305a26d5265ace50d230d484059`; 2026-10-23T07:07:40Z; VIP card navy, Standard white, 3D kept.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-blueprint-vip-preview/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `.vercel`, `129`, `checkout.html`, `compare`, `index.html`, `options`, `privacy.html`, `relaunch.css`, `relaunch.js`.

### gitteromri-ux/lla-course-checkout

- **Repository:** [gitteromri-ux/lla-course-checkout](https://github.com/gitteromri-ux/lla-course-checkout); private.
- **Purpose:** Longevity Life Academy e-commerce landing page + 3-step self-service checkout
- **Branches inspected:** `add-agency-credit-footer`, `backup/20260927-1232-hero-wallet`, `backup/20260927-before-video`, `backup/20260927-blueprint-tracking`, `backup/20260928-attribution-before`, `backup/master-stale-base-2026-09-09`, `design/luxury-transform-v1`, `fbc-fix-20260924`, `fix/blueprint-attribution-20260928`, `fix/blueprint-receipts-20260928`, `fix/dates-and-emq`, `fix/hero-wallet-20260927`, `fix/mobile-sheet-20260923`, `fix/support-20261007`, `main`, `master`, `r1-mobile-fix`, `v58-offer-pillars-logo-syllabus`.
- **Inventory:** 17,646 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `6c27b2fff1d9bcaeeb8fb8687470ecc87b9b2de0`; 2026-10-27T22:37:39Z; Show Pacific time on mobile enrollment class cards.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `.well-known`, `ECOM_RESTRUCTURE_V3_NOTES.md`, `FUNNEL_BRIEF.md`, `HANDOVER.md`, `LIGHT_REDESIGN_V2_NOTES.md`, `PDP_REBUILD_REPORT.md`, `ROUND14_CHECKLIST.md`, `_check_institution.mjs`, `_check_kicker.mjs`, `_check_nav.mjs`, `_check_overflow.py`, `_dbg.py`, `_dtfull.py`, `_ecom_restructure.py`, `_edit_content.py`, `_edit_graphics.py`, `_facshot.py`, `_find_svg.py`, `_fl.py`, `_gap.py`, `_h.py`, `_h2.py`, `_headers`, `_hero_shot.mjs`, `_heroshot.py`, `_mob.py`, `_mobfull.py`, `_ref.py`, `_sec.py`, `_shoot5.py`, `_shoot_checkpoint.py`, `_shoot_mobile.py`, `_shoot_nav.py`, `_shot_early.mjs`, `_shot_hero_check.py`, `_shot_leadgen.py`, `_shot_learn2.py`, `_shot_learn3.py`, `_shot_mech.py`, `_shot_mobile_hero.py`, `_shot_qa.mjs`, `_shot_section.py`, `_v13.py`, `assets`, `capi-relay`, `checkout.html`, `dist`, `hero-wallet-20260927`, `index.html`, `index.html.bak-v10`, `index.html.bak-v11`, `index.html.bak-v12`, `index.html.bak-v13`, `index.html.bak-v5`, `index.html.bak-v8`, `privacy.html`, `robots.txt`, `sedQBzbHm`, `sedk1N5uX`, `shots-checkout`, `shots-d`, `shots-ecom`, `shots-light`, `shots-m`, `shots-mobile`, `shots-nav`, `shots-pdp`, `shots-redesign`, `shots-v4`, `shots-v5`, `shots-v6`, `shots-v7`, `sitemap.xml`, `tools`, `tracking-receipts-20260928`, `tracking-recovery-20260927`, `v08041829.html`, `v08042158.html`, `v08042313.html`, `v08042315.html`, `v08042335.html`, `v08042347.html`, `v08050020.html`, `v08050033.html`, `v08050056.html`, `v08101020.html`, `video-repair-20260927`, `worker`, `wrangler.static.toml`.

### gitteromri-ux/lla-gal-september-2026

- **Repository:** [gitteromri-ux/lla-gal-september-2026](https://github.com/gitteromri-ux/lla-gal-september-2026); public/visibility not independently specified.
- **Purpose:** LLA GAL board report September 2026 (Excel + PDF + sources)
- **Branches inspected:** `main`.
- **Inventory:** 10 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `4461984edb9b29931712dec7d6c207f77500c913`; 2026-10-12T09:33:30Z; Restore three-effort view (Leads camp · LLA/ATC camp · Blueprint e-comm) with spend split and results, as in 3f29b1e.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-gal-september-2026/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `Longevity-GAL-September-2026.pdf`, `Longevity-GAL-September-2026.xlsx`, `README.md`, `build_gal.py`, `index.html`, `make_html.py`, `sources`.

### gitteromri-ux/lla-growth-engine

- **Repository:** [gitteromri-ux/lla-growth-engine](https://github.com/gitteromri-ux/lla-growth-engine); public/visibility not independently specified.
- **Purpose:** LLA Growth Engine: full-funnel ecommerce marketing system for The Longevity Blueprint
- **Branches inspected:** `main`.
- **Inventory:** 46 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `34ad31fc0227b6a95a84406edbe3ef90a00e3a3a`; 2026-08-04T21:57:07Z; Logo legibility on dark grounds.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-growth-engine/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `.nojekyll`, `app.js`, `assets`, `build`, `index.html`, `styles.css`.

### gitteromri-ux/lla-handoff-pack

- **Repository:** [gitteromri-ux/lla-handoff-pack](https://github.com/gitteromri-ux/lla-handoff-pack); public/visibility not independently specified.
- **Purpose:** Longevity Life Academy - ecommerce and Meta media handoff pack
- **Branches inspected:** `master`.
- **Inventory:** 2 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `abbae0ed1467c402c5f77d1f4068c05ac42af3c5`; 2026-09-02T05:38:44Z; Type sizing: no text below 15px on mobile.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-handoff-pack/; build type `legacy`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `index.html`.

### gitteromri-ux/lla-julie-masterclass

- **Repository:** [gitteromri-ux/lla-julie-masterclass](https://github.com/gitteromri-ux/lla-julie-masterclass); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 74 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `a32c435e94dab8778e330b9d6fbfd209f15e5dff`; 2026-09-02T11:01:14Z; Remove reveal fade from Julie and Press sheads/slider.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-julie-masterclass/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `assets`, `index.html`.

### gitteromri-ux/lla-julie-ugc-ads

- **Repository:** [gitteromri-ux/lla-julie-ugc-ads](https://github.com/gitteromri-ux/lla-julie-ugc-ads); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `bridge`, `master`.
- **Inventory:** 420 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `e65bc5eddb88fab30c2bc3a099e6e213a9c8d086`; 2026-10-19T09:39:26Z; Blueprint UGC: two presenters, 9:16 and 1:1, kit page.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-julie-ugc-ads/; build type `legacy`; source `{'branch': 'master', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.github`, `ad1-man42.html`, `ad2-woman42.html`, `ads.json`, `blueprint`, `bridge`, `build_site.py`, `claude-fixes`, `ending`, `film-full-masterclass-edit.html`, `gen`, `hookbuild`, `index.html`, `lla-logo.png`, `posters`, `v34`, `videos`.

### gitteromri-ux/lla-marketing-dashboard

- **Repository:** [gitteromri-ux/lla-marketing-dashboard](https://github.com/gitteromri-ux/lla-marketing-dashboard); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 116 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `19bce8be45b499a63b02e4d0c3545fcd97b31052`; 2026-10-07T04:28:12Z; slides: full-sentence UGC hooks + current Meta status (7 Oct).
- **Pages configuration:** https://gitteromri-ux.github.io/lla-marketing-dashboard/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `ad_thumb_urls.json`, `adsets.html`, `app.js`, `assets`, `campaign.js`, `campaign_live.json`, `creatives_live.json`, `data.js`, `index.html`, `julie-banners`, `masterclass-adsets.html`, `styles.css`.

### gitteromri-ux/lla-masterclass-assets

- **Repository:** [gitteromri-ux/lla-masterclass-assets](https://github.com/gitteromri-ux/lla-masterclass-assets); public/visibility not independently specified.
- **Purpose:** Longevity Life Academy Masterclass: final creative assets
- **Branches inspected:** `main`.
- **Inventory:** 172 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `ff002be9e921bad44c0ecfe6bb73bcef0c8ed8af`; 2026-10-27T09:59:37Z; final hierarchy, tonight only, 3 bullets, tag list.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-masterclass-assets/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `README.md`, `boards`, `extracted`, `full-film-v3`, `index.html`, `julie-film-masterclass-edit.html`, `julie-film-v4`, `masterclass-fold-mockup-final.png`, `originals-fold-mockup.jpg`, `originals-phones-mockup.jpg`, `parts`, `phones-mockup-final.png`, `previous-mockups`, `sizes`, `social-share`, `video`, `zoom-40-ppl-logos.jpg`, `zoom-meeting-ui-chat.jpg`.

### gitteromri-ux/lla-masterclass-attendees

- **Repository:** [gitteromri-ux/lla-masterclass-attendees](https://github.com/gitteromri-ux/lla-masterclass-attendees); public/visibility not independently specified.
- **Purpose:** Longevity Blueprint offer page for Julie Masterclass attendees (link-only, noindex). Clone of pages.dev funnel; production untouched.
- **Branches inspected:** `main`.
- **Inventory:** 251 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `5717b29896387d8ba3227f6178b4fec55c8f62cf`; 2026-10-27T05:50:22Z; Version source assets so returning attendees receive the final design.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-masterclass-attendees/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.well-known`, `attendee-form.js`, `attendee-layout.css`, `blueprint`, `exact-attendee-copy.js`, `exact-source-design.css`, `index.html`, `learning-first.css`, `learning-first.js`, `lp`, `robots.txt`.

### gitteromri-ux/lla-masterclass-emails

- **Repository:** [gitteromri-ux/lla-masterclass-emails](https://github.com/gitteromri-ux/lla-masterclass-emails); public/visibility not independently specified.
- **Purpose:** LLA Julie Masterclass lifecycle emails
- **Branches inspected:** `main`.
- **Inventory:** 47 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `18b89c487feac5389fb2d07a48844a2c4103cffd`; 2026-10-22T12:45:53Z; No-show: remove all no-replay claims (X1, X3).
- **Pages configuration:** https://gitteromri-ux.github.io/lla-masterclass-emails/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `assets`, `emails`, `index.html`, `preview.html`.

### gitteromri-ux/lla-masterclass-emails-3tier

- **Repository:** [gitteromri-ux/lla-masterclass-emails-3tier](https://github.com/gitteromri-ux/lla-masterclass-emails-3tier); public/visibility not independently specified.
- **Purpose:** LLA Julie Masterclass lifecycle emails, 3-tier edition (Standard 9 / VIP 9 / Full Course + VIP free)
- **Branches inspected:** `main`.
- **Inventory:** 109 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `098fbb448ee3233d9ab60f619989889cd7d9003a`; 2026-09-24T13:25:51Z; journeys: segment highlight offset uses sticky bar height.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-masterclass-emails-3tier/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `FACTS.md`, `assets`, `emails`, `index.html`, `journeys.html`, `launch-email-for-chris`.

### gitteromri-ux/lla-masterclass-syllabus

- **Repository:** [gitteromri-ux/lla-masterclass-syllabus](https://github.com/gitteromri-ux/lla-masterclass-syllabus); public/visibility not independently specified.
- **Purpose:** The Longevity Masterclass one-hour syllabus, prepared for Julie Gibson Clark
- **Branches inspected:** `main`.
- **Inventory:** 1,995 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `ae91763f703e1edd012826af40f276046f0c272e`; 2026-10-27T22:42:31Z; n25 fork: headlines re-composited opaque last, real asphalt texture, clock brighter; z20/y33.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-masterclass-syllabus/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitignore`, `backup-deck`, `deck`, `deck-review`, `deck2`, `index.html`, `masterclass-deck`, `refs`, `script`, `slide-canvas`.

### gitteromri-ux/lla-s09-s10-downloads

- **Repository:** [gitteromri-ux/lla-s09-s10-downloads](https://github.com/gitteromri-ux/lla-s09-s10-downloads); public/visibility not independently specified.
- **Purpose:** LLA Scripts 09/10: Courtney editing brief + full-frame video masters
- **Branches inspected:** `claude/birthday-video-max-jtr8vj`, `claude/design-video-file-access-0y4n0e`, `claude/next-video-teachers-edit-x6rpsj`, `claude/render-assemble-film-5h8s11`, `claude/rtl-support-no-plugins-6qzkin`, `claude/video-0717-background-replace-qm11te`, `claude/video-0717-set-replacement-d3h6xo`, `fix-releases-src`, `main`, `site`, `upload-julie-cards`, `upload-julie-raws`, `v17-final`.
- **Inventory:** 1,867 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `6b178bbc77cfdf49e262010218413d3ad695b9b6`; 2026-08-07T08:45:03Z; V23 editor line audit.
- **Pages configuration:** https://gitteromri-ux.github.io/lla-s09-s10-downloads/; build type `legacy`; source `{'branch': 'site', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.gitattributes`, `.github`, `.gitignore`, `.nojekyll`, `.pipeline`, `Courtney_FRONT_4K_part1.mp4`, `Courtney_FRONT_4K_part2.mp4`, `Courtney_FRONT_4K_part3.mp4`, `Courtney_FRONT_4K_v3_part1.mp4`, `Courtney_FRONT_4K_v3_part2.mp4`, `Courtney_FRONT_4K_v3_part3.mp4`, `Courtney_FRONT_ENHANCED_part1.mp4`, `Courtney_FRONT_MASTER_v2.mp4`, `Courtney_FRONT_PRO.mp4`, `Courtney_FRONT_ULTRA.mp4`, `Courtney_SIDE_4K_part1.mp4`, `Courtney_SIDE_4K_part2.mp4`, `Courtney_SIDE_4K_part3.mp4`, `Courtney_SIDE_4K_v3_part1.mp4`, `Courtney_SIDE_4K_v3_part2.mp4`, `Courtney_SIDE_4K_v3_part3.mp4`, `Courtney_SIDE_MASTER_v2.mp4`, `Courtney_SIDE_PRO.mp4`, `Courtney_SIDE_ULTRA.mp4`, `DOR_30_FINAL_720p.mp4`, `DOR_30_FINAL_with_max.mp4`, `DOR_30_MASTER_1080p.mp4`, `DOR_30_V2_MASTER_1080p.mp4`, `JULIE_LLA_V17_60S.mp4`, `JULIE_LLA_V17_90S.mp4`, `JULIE_LLA_V17_FULL.mp4`, `JULIE_V17_60S_STORYBOARD.pdf`, `JULIE_V17_90S_STORYBOARD.pdf`, `JULIE_V17_STORYBOARD_FULL.pdf`, `JULIE_V18_60S_STORYBOARD.pdf`, `JULIE_V18_90S_STORYBOARD.pdf`, `JULIE_V18_STORYBOARD_FULL.pdf`, `JULIE_V22_90S_STORYBOARD.pdf`, `JULIE_V22_STORYBOARD_FULL.pdf`, `JULIE_V23_90S_STORYBOARD.pdf`, `JULIE_V23_STORYBOARD_FULL.pdf`, `LLA_Editing_Brief_S09_S10.md`, `README.md`, `RUNBOOK_FIX_V2.md`, `RUNBOOK_OPTION_B.md`, `analysis`, `assets`, `deliverables`, `files`, `finalcut`, `host`, `index.html`, `julie-v23-sources`, `max_photos`, `otro`, `production`, `rtl-demo.html`, `scripts`, `viewer.html`.

### gitteromri-ux/lla-site-live

- **Repository:** [gitteromri-ux/lla-site-live](https://github.com/gitteromri-ux/lla-site-live); private.
- **Purpose:** Write mirror of Longevity-Academy/Longevity-Academy.github.io: push here, the org repo syncs and deploys GitHub Pages
- **Branches inspected:** `backup-pre-v8-text-changes-20260507-130526`, `main`, `pricing-preview`, `staging`, `v1-backup`, `v44-redesign`.
- **Inventory:** 2,039 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `d60cb6964bee967ee446af96438379a6f8e5972d`; 2026-10-07T14:32:39Z; Blog: 'In the press' fold ported 1:1 from /blueprint/ (5 cards: AP News/Harel, Supplements motion, Five Habits motion, Yahoo Finance/Julie, Visible Edge motion); Harel framed with full head; mobile stacked.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.build-trigger`, `.gitignore`, `.netlify`, `.nojekyll`, `.well-known`, `200.html`, `CNAME`, `about.html`, `assets`, `biological-age-light.html`, `blog.html`, `blueprint`, `cgm.html`, `checkout`, `enroll-staging.html`, `go`, `guides`, `homepage_backup_20260417_161625.html`, `homepage_backup_20260417_172852.html`, `index-light-backup-apr18.html`, `index-light-broken-attempt.html`, `index-light-correct-base.html`, `index-light-v1-pricing.html`, `index-light.html`, `index-v1.html`, `index-v2.html`, `index.html`, `internal`, `lp`, `pricing-preview.html`, `pricing.html`, `privacy.html`, `refer-a-friend`, `robots.txt`, `screenshots-overhaul`, `sitemap.xml`, `store`, `support`, `teachers`, `terms.html`, `thank-you.html`, `topics`, `vercel.json`.

### gitteromri-ux/longevity-assets

- **Repository:** [gitteromri-ux/longevity-assets](https://github.com/gitteromri-ux/longevity-assets); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`.
- **Inventory:** 6 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `d4e6a3a81877d51f58efd8206fee6bcf8c8b4f1c`; 2026-08-05T06:56:53Z; films: 90 second cut first; creative: Julie campaign banner set; wording cleanup.
- **Pages configuration:** https://gitteromri-ux.github.io/longevity-assets/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `index.html`, `thumbs`.

### gitteromri-ux/longevity-life-academy

- **Repository:** [gitteromri-ux/longevity-life-academy](https://github.com/gitteromri-ux/longevity-life-academy); public/visibility not independently specified.
- **Purpose:** Longevity Life Academy by eTeacher Group
- **Branches inspected:** `claude/live-set-mobile-optimize-kqlipi`, `gh-pages`, `main`.
- **Inventory:** 255 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `12841230edc48cd05df7b8fa3eedba375263537c`; 2026-08-06T12:02:06Z; storyboard cover fix.
- **Pages configuration:** https://gitteromri-ux.github.io/longevity-life-academy/; build type `legacy`; source `{'branch': 'gh-pages', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.netlify`, `200.html`, `assets`, `biological-age-light.html`, `disclaimer.html`, `homepage_backup_20260417_161625.html`, `homepage_backup_20260417_172852.html`, `index-light-backup-apr18.html`, `index-light-broken-attempt.html`, `index-light-correct-base.html`, `index-light-v1-pricing.html`, `index-light.html`, `index.html`, `lp`, `privacy.html`, `robots.txt`, `sitemap.xml`, `terms.html`, `topics`, `vercel.json`.

### gitteromri-ux/masterclass-rfp

- **Repository:** [gitteromri-ux/masterclass-rfp](https://github.com/gitteromri-ux/masterclass-rfp); public/visibility not independently specified.
- **Purpose:** Masterclass sales sprint RFP: Claude vs Grok vs Perplexity
- **Branches inspected:** `main`.
- **Inventory:** 1 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `fd86d4c8f530e3ff6c99dd321f2050a0d57a6987`; 2026-10-25T14:17:04Z; Anchor offset under sticky nav.
- **Pages configuration:** https://gitteromri-ux.github.io/masterclass-rfp/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `index.html`.

### gitteromri-ux/personalix

- **Repository:** [gitteromri-ux/personalix](https://github.com/gitteromri-ux/personalix); public/visibility not independently specified.
- **Purpose:** Personalix: Candidate first. Designed for people. AI-powered, human-first recruitment platform.
- **Branches inspected:** `main`.
- **Inventory:** 7 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `e4d090fa49ac2e92038c132a5a8ca7580ce13d33`; 2026-07-23T11:16:22Z; Per-card brand colors: distinct on-brand accent (bg tint, border, glow, icon chip, ticks, badges) for every card across all folds: no more monotone navy.
- **Pages configuration:** https://gitteromri-ux.github.io/personalix/; build type `legacy`; source `{'branch': 'main', 'path': '/'}`. This is configuration, not a new payment/UI test.
- **Top-level contents:** `.nojekyll`, `README.md`, `assets`, `index.html`.

### gitteromri-ux/serious-claims

- **Repository:** [gitteromri-ux/serious-claims](https://github.com/gitteromri-ux/serious-claims); private.
- **Purpose:** Documented cases: deliveries that did not match Omri's written request (evidence log)
- **Branches inspected:** `main`.
- **Inventory:** 4 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `5b5ee70c5365cd5d38cacd47fe6cb52a0b718ec5`; 2026-09-30T14:12:46Z; Case 003 addendum: skills not deployed, Omri's 17:12 statement.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `README.md`, `cases`.

### gitteromri-ux/ugc-prod

- **Repository:** [gitteromri-ux/ugc-prod](https://github.com/gitteromri-ux/ugc-prod); public/visibility not independently specified.
- **Purpose:** No repository description; use paths and project register.
- **Branches inspected:** `main`, `recovery/w46b-p2`.
- **Inventory:** 72 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `6ca4c05be212c63bb84c4b1cb90a4934b468617d`; 2026-10-01T14:21:19Z; Public Claude handover: recover Zoom assets, exact part-one original, exports and audit; correct missing-file claims.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `HANDOVER-TO-CLAUDE.md`, `ORIGINAL-SHA256.txt`, `PART2-RECOVERY.md`, `README.md`, `SHA256SUMS.txt`, `fonts`, `music`, `recovered-from-exports`, `reference-exports`, `refs`, `restore_originals.py`, `restore_part2.py`, `src`.

### gitteromri-ux/ziv-book-cover-directions

- **Repository:** [gitteromri-ux/ziv-book-cover-directions](https://github.com/gitteromri-ux/ziv-book-cover-directions); private.
- **Purpose:** כך נפלנו כך נקום: 10 split-screen cover background directions (private review)
- **Branches inspected:** `main`.
- **Inventory:** 37 file rows; recursive tree truncated: false.
- **Default-branch latest commit:** `1b9931864b67236dd29dd58610fbd89a1e3f6e43`; 2026-09-28T11:05:39Z; v5: real photographs only (Tkuma, Be'eri, Nova/Re'im shelter × Shokeda/Ruhama anemones), CC-licensed, credits included.
- **Pages configuration:** Not returned in collected evidence; hosting may be elsewhere.
- **Top-level contents:** `.gitignore`, `CREDITS.md`, `README.md`, `aluf.png`, `bg`, `cover.html`, `covers`, `directions.json`, `fonts`, `index.html`, `photo-sources.json`, `prompts.json`, `render.js`, `thumbs`.


## Complete discovered repository metadata register

Older repositories without collected trees are included here to avoid silently omitting other subjects. Their latest pushed timestamps are discovery metadata, not a new content audit.

| Repository | Latest pushed UTC | Tree collected | Description |
|---|---|---|---|
| [Longevity-Academy/Longevity-Academy.github.io](https://github.com/Longevity-Academy/Longevity-Academy.github.io) | 2026-10-27T10:16:58Z | yes |  |
| [Longevity-Academy/blueprint-attendees-7q4x](https://github.com/Longevity-Academy/blueprint-attendees-7q4x) | 2026-10-27T22:52:28Z | yes | Unlisted attendee offer page for Julie's masterclass (noindex, link-only) |
| [Longevity-Academy/french-atelier-paris](https://github.com/Longevity-Academy/french-atelier-paris) | 2026-06-24T21:56:29Z | no | French Atelier: Win a Flight to Paris |
| [Longevity-Academy/julie-fix-preview](https://github.com/Longevity-Academy/julie-fix-preview) | 2026-10-18T20:53:25Z | yes | Julie masterclass preview: SDK retry fix + v9 pricing cards and 72h strip. Production untouched. |
| [Longevity-Academy/julie-masterclass](https://github.com/Longevity-Academy/julie-masterclass) | 2026-10-26T10:02:02Z | yes |  |
| [Longevity-Academy/lla-checkout-live](https://github.com/Longevity-Academy/lla-checkout-live) | 2026-09-09T14:29:07Z | yes |  |
| [Longevity-Academy/longevity-pillars-mece-preview](https://github.com/Longevity-Academy/longevity-pillars-mece-preview) | 2026-04-30T11:46:43Z | no | Preview: Six Pillars MECE update with clinical subheaders |
| [Longevity-Academy/longevity-v61-preview](https://github.com/Longevity-Academy/longevity-v61-preview) | 2026-05-07T08:38:47Z | no | v61 hero preview - One Academy. Every Pillar of Longevity. |
| [Longevity-Academy/longevity-v62-preview](https://github.com/Longevity-Academy/longevity-v62-preview) | 2026-05-07T08:38:49Z | no | v62 hero preview - Be There. Fully. For a Long Time. |
| [Longevity-Academy/longevity-v63-preview](https://github.com/Longevity-Academy/longevity-v63-preview) | 2026-05-07T08:38:51Z | no | v63 hero preview - Still Going Strong. For Them. |
| [Longevity-Academy/longevity-v64-preview](https://github.com/Longevity-Academy/longevity-v64-preview) | 2026-05-07T08:38:54Z | no | v64 hero preview - Live Younger. For Longer. |
| [Longevity-Academy/longevity-v65-preview](https://github.com/Longevity-Academy/longevity-v65-preview) | 2026-05-07T08:38:56Z | no | v65 hero preview - Shared Life. Shared Health. |
| [Longevity-Academy/longevity-v66-preview](https://github.com/Longevity-Academy/longevity-v66-preview) | 2026-05-07T08:38:58Z | no | Longevity Life Academy: Version 7 (cells hero) |
| [Longevity-Academy/longevity-v8-preview](https://github.com/Longevity-Academy/longevity-v8-preview) | 2026-05-07T08:38:44Z | no | v8 preview: fold reorder + hero/pillars text edits per CEO spec |
| [Longevity-Academy/longevity-v9-preview](https://github.com/Longevity-Academy/longevity-v9-preview) | 2026-05-05T19:29:51Z | no | v9 preview snapshot: exact clone of v8 lock-in (b5a56ce) |
| [Longevity-Academy/masterclass-72hours](https://github.com/Longevity-Academy/masterclass-72hours) | 2026-10-18T14:07:41Z | yes | Julie masterclass 72-hour community-offer LP (email blast). Separate duplicate; production julie-masterclass untouched. |
| [gitteromri-ux/Longevity](https://github.com/gitteromri-ux/Longevity) | 2026-04-10T15:38:55Z | no |  |
| [gitteromri-ux/Longevity-light](https://github.com/gitteromri-ux/Longevity-light) | 2026-04-13T10:41:49Z | no |  |
| [gitteromri-ux/abraham-tel-aviv-gm](https://github.com/gitteromri-ux/abraham-tel-aviv-gm) | 2026-09-15T06:48:29Z | no | Abraham Tel Aviv · GM 100-day plan · Fall 2026 |
| [gitteromri-ux/abraham-tlv-gm](https://github.com/gitteromri-ux/abraham-tlv-gm) | 2026-09-16T12:24:58Z | no | Abraham Tel Aviv GM · Autumn 2026 plan |
| [gitteromri-ux/abraham-tlv-gm-v2](https://github.com/gitteromri-ux/abraham-tlv-gm-v2) | 2026-09-16T12:36:51Z | no | Abraham Tel Aviv GM · Autumn 2026 |
| [gitteromri-ux/amy-squishy](https://github.com/gitteromri-ux/amy-squishy) | 2026-06-08T14:13:19Z | no | איימי סקווישי: מבחר הסקווישי הגדול בישראל |
| [gitteromri-ux/amy-squishy-new](https://github.com/gitteromri-ux/amy-squishy-new) | 2026-06-10T16:34:03Z | no |  |
| [gitteromri-ux/apt-furniture-deck](https://github.com/gitteromri-ux/apt-furniture-deck) | 2026-07-05T11:45:44Z | no |  |
| [gitteromri-ux/awesome-longevity](https://github.com/gitteromri-ux/awesome-longevity) | 2026-09-15T16:21:34Z | no | An awesome list of longevity resources for living longer, healthier lives. |
| [gitteromri-ux/blended-cpa-dashboard](https://github.com/gitteromri-ux/blended-cpa-dashboard) | 2026-05-23T18:03:55Z | no | Interactive blended-CPA cohort dashboard - DuckDB-WASM + ECharts |
| [gitteromri-ux/brown-hotels-greece-briefing](https://github.com/gitteromri-ux/brown-hotels-greece-briefing) | 2026-08-17T02:48:18Z | no |  |
| [gitteromri-ux/callcenter-kpi-dashboard](https://github.com/gitteromri-ux/callcenter-kpi-dashboard) | 2026-04-23T07:02:37Z | no | Call Center Intelligence: KPI Performance Analytics Dashboard |
| [gitteromri-ux/campaign-intelligence-dashboard](https://github.com/gitteromri-ux/campaign-intelligence-dashboard) | 2026-04-16T13:24:40Z | no | Campaign Performance Intelligence Dashboard |
| [gitteromri-ux/cartoon-circular-portraits-1783953556](https://github.com/gitteromri-ux/cartoon-circular-portraits-1783953556) | 2026-07-13T14:56:25Z | no |  |
| [gitteromri-ux/ceo-performance-suite](https://github.com/gitteromri-ux/ceo-performance-suite) | 2026-06-23T12:42:21Z | no | CEO Performance Suite |
| [gitteromri-ux/club-italia](https://github.com/gitteromri-ux/club-italia) | 2026-10-11T21:11:41Z | yes | Club Italia by eTeacher: live-online Italian language school (structural parity with FrenchAtelierLive) |
| [gitteromri-ux/club-italia-preview](https://github.com/gitteromri-ux/club-italia-preview) | 2026-10-11T21:11:45Z | yes |  |
| [gitteromri-ux/courtney-banners](https://github.com/gitteromri-ux/courtney-banners) | 2026-08-06T11:31:20Z | no |  |
| [gitteromri-ux/courtney-lla-masterclass](https://github.com/gitteromri-ux/courtney-lla-masterclass) | 2026-07-13T10:13:18Z | no |  |
| [gitteromri-ux/courtney-master-production](https://github.com/gitteromri-ux/courtney-master-production) | 2026-07-19T22:54:56Z | no | LLA · Courtney Master Production File: French Atelier deconstruction, clean script, 3 storyboards |
| [gitteromri-ux/courtney-review](https://github.com/gitteromri-ux/courtney-review) | 2026-08-24T12:53:53Z | no | Courtney Donofrio: LLA review package: videos + banners |
| [gitteromri-ux/cqi-sense-deck](https://github.com/gitteromri-ux/cqi-sense-deck) | 2026-06-02T07:33:36Z | no |  |
| [gitteromri-ux/cultural-capsules-pack3](https://github.com/gitteromri-ux/cultural-capsules-pack3) | 2026-10-08T10:07:33Z | yes | French Atelier: Cultural Capsules Pack 3: Cinema & Music (10 decks) |
| [gitteromri-ux/enneagram-8w7-4w3](https://github.com/gitteromri-ux/enneagram-8w7-4w3) | 2026-07-16T12:55:37Z | no |  |
| [gitteromri-ux/eteacher-longevity](https://github.com/gitteromri-ux/eteacher-longevity) | 2026-07-07T06:23:49Z | no | eTeacher Longevity Course Landing Page |
| [gitteromri-ux/eteacher-longevity-backup](https://github.com/gitteromri-ux/eteacher-longevity-backup) | 2026-04-13T06:24:10Z | no | eTeacher Longevity - Clean backup (no animated display elements) |
| [gitteromri-ux/eteacher-longevity-pr-campaign](https://github.com/gitteromri-ux/eteacher-longevity-pr-campaign) | 2026-07-08T12:11:02Z | no |  |
| [gitteromri-ux/eteacher-school-banners](https://github.com/gitteromri-ux/eteacher-school-banners) | 2026-06-25T13:15:05Z | no |  |
| [gitteromri-ux/fa-capsules-launch](https://github.com/gitteromri-ux/fa-capsules-launch) | 2026-10-22T22:41:11Z | yes |  |
| [gitteromri-ux/fa-capsules-review-public](https://github.com/gitteromri-ux/fa-capsules-review-public) | 2026-10-19T08:45:41Z | yes |  |
| [gitteromri-ux/final-versions](https://github.com/gitteromri-ux/final-versions) | 2026-10-01T13:41:25Z | yes | Julie Masterclass UGC Ads · FINAL VERSIONS |
| [gitteromri-ux/french-atelier](https://github.com/gitteromri-ux/french-atelier) | 2026-10-26T10:11:51Z | yes | The French Atelier by Acadomia: world-class French e-learning website |
| [gitteromri-ux/french-atelier-acq-drip](https://github.com/gitteromri-ux/french-atelier-acq-drip) | 2026-08-05T14:34:49Z | yes | French Atelier - ACQ Drip Series Stage 3: 12 emails, 12 landing pages, quiz, promo claim page, 36 exact-size images |
| [gitteromri-ux/french-atelier-capsules](https://github.com/gitteromri-ux/french-atelier-capsules) | 2026-10-23T01:40:43Z | yes |  |
| [gitteromri-ux/french-atelier-ceo-deck](https://github.com/gitteromri-ux/french-atelier-ceo-deck) | 2026-07-14T20:02:00Z | no | French Atelier CEO Marketing Review · June 2026 |
| [gitteromri-ux/french-atelier-client-demographics](https://github.com/gitteromri-ux/french-atelier-client-demographics) | 2026-08-06T11:59:23Z | no | The French Atelier by Acadomia: client demographics board briefing |
| [gitteromri-ux/french-atelier-emails-gallery](https://github.com/gitteromri-ux/french-atelier-emails-gallery) | 2026-06-07T08:34:51Z | no | 30-email lifecycle gallery with full mockups |
| [gitteromri-ux/french-atelier-june-results](https://github.com/gitteromri-ux/french-atelier-june-results) | 2026-09-22T10:56:32Z | no |  |
| [gitteromri-ux/french-atelier-jv-deck](https://github.com/gitteromri-ux/french-atelier-jv-deck) | 2026-10-07T08:10:14Z | yes |  |
| [gitteromri-ux/french-atelier-lifecycle-emails](https://github.com/gitteromri-ux/french-atelier-lifecycle-emails) | 2026-10-07T08:20:38Z | yes |  |
| [gitteromri-ux/french-atelier-onboarding](https://github.com/gitteromri-ux/french-atelier-onboarding) | 2026-10-13T14:57:53Z | yes | French Atelier by Acadomia: complete onboarding & nurture package (8 emails, 2 landing pages, WhatsApp, 2 Typeform quizzes, hero imagery, mockups). Brand-aligned with Caitlin design system. |
| [gitteromri-ux/french-atelier-social-deck](https://github.com/gitteromri-ux/french-atelier-social-deck) | 2026-06-25T04:43:04Z | no |  |
| [gitteromri-ux/french-atelier-social-kickstart](https://github.com/gitteromri-ux/french-atelier-social-kickstart) | 2026-09-16T21:57:21Z | yes | French Atelier · Organic Social Kickstart · Sept and Oct 2026 |
| [gitteromri-ux/french-atelier-v2](https://github.com/gitteromri-ux/french-atelier-v2) | 2026-06-29T11:13:10Z | no | French Atelier v2: Mapstr imagery + consistent teacher portraits |
| [gitteromri-ux/french-atelier-wa-8-briefs](https://github.com/gitteromri-ux/french-atelier-wa-8-briefs) | 2026-09-15T08:47:36Z | no | French Atelier · WhatsApp Batch of 8 (Content brief WA-8-new-Briefs): 6 content + 2 promo, 1792x897 imagery, all CTAs to www.frenchatelierlive.com |
| [gitteromri-ux/french-atelier-wa-batch-2](https://github.com/gitteromri-ux/french-atelier-wa-batch-2) | 2026-09-22T13:41:10Z | no | French Atelier by Acadomia - WhatsApp Batch 2: eight messages following the approved brief |
| [gitteromri-ux/french-atelier-wa-ret-acq](https://github.com/gitteromri-ux/french-atelier-wa-ret-acq) | 2026-08-06T10:32:46Z | yes |  |
| [gitteromri-ux/french-atelier-website](https://github.com/gitteromri-ux/french-atelier-website) | 2026-10-13T14:57:32Z | yes | French Atelier: full website mockup (CEO review June 2026) |
| [gitteromri-ux/french-atelier-win-paris](https://github.com/gitteromri-ux/french-atelier-win-paris) | 2026-07-02T09:05:13Z | no | Win a Free Flight to Paris for Bastille Day: French Atelier contest landing page & terms |
| [gitteromri-ux/frenchatelier-bastille-2026](https://github.com/gitteromri-ux/frenchatelier-bastille-2026) | 2026-06-27T20:29:03Z | no |  |
| [gitteromri-ux/frenchatelier-paris](https://github.com/gitteromri-ux/frenchatelier-paris) | 2026-06-24T22:30:49Z | no | French Atelier: Win a Flight to Paris |
| [gitteromri-ux/gita-cars](https://github.com/gitteromri-ux/gita-cars) | 2026-05-26T21:45:25Z | no | GITA CARS: Hebrew RTL premium car import consulting site |
| [gitteromri-ux/gita-cars-44](https://github.com/gitteromri-ux/gita-cars-44) | 2026-05-24T06:17:17Z | no |  |
| [gitteromri-ux/gita-finances](https://github.com/gitteromri-ux/gita-finances) | 2026-07-05T06:35:46Z | no |  |
| [gitteromri-ux/gita-machine](https://github.com/gitteromri-ux/gita-machine) | 2026-09-17T17:31:33Z | yes | Gita Machine: organic reach at machine scale |
| [gitteromri-ux/gitteromri-ux.github.io](https://github.com/gitteromri-ux/gitteromri-ux.github.io) | 2026-05-17T12:39:55Z | no | Employee rank & call allocation analysis dashboard |
| [gitteromri-ux/hana](https://github.com/gitteromri-ux/hana) | 2026-07-23T16:43:46Z | yes | Hana: a professional 108-item Enneagram assessment with full type and wing analysis |
| [gitteromri-ux/handover-instinct-grok](https://github.com/gitteromri-ux/handover-instinct-grok) | 2026-10-11T09:34:34Z | yes | Private master handover 2026-10-10 for Instinct / Grok Bot (Omri Gitter / Gita Agency) |
| [gitteromri-ux/handover-master](https://github.com/gitteromri-ux/handover-master) | 2026-10-20T13:20:16Z | yes | MASTER HANDOVER: every active project, link, rule, and asset. Compiled 2026-09-01 for cross-subscription continuity. |
| [gitteromri-ux/harel-brief](https://github.com/gitteromri-ux/harel-brief) | 2026-10-26T12:22:54Z | yes |  |
| [gitteromri-ux/harel-weekly-oct26](https://github.com/gitteromri-ux/harel-weekly-oct26) | 2026-10-26T12:23:10Z | yes |  |
| [gitteromri-ux/iching-reading](https://github.com/gitteromri-ux/iching-reading) | 2026-10-19T17:47:21Z | yes |  |
| [gitteromri-ux/in-venture-programme](https://github.com/gitteromri-ux/in-venture-programme) | 2026-08-09T11:22:50Z | yes |  |
| [gitteromri-ux/in-venture-website](https://github.com/gitteromri-ux/in-venture-website) | 2026-09-01T10:23:59Z | yes | IN Venture premium website rebuild by Gita Agency |
| [gitteromri-ux/jgc-masterclass-deck](https://github.com/gitteromri-ux/jgc-masterclass-deck) | 2026-07-07T06:24:15Z | no |  |
| [gitteromri-ux/julie-500-launch-plan](https://github.com/gitteromri-ux/julie-500-launch-plan) | 2026-10-19T23:12:42Z | yes |  |
| [gitteromri-ux/julie-ads](https://github.com/gitteromri-ux/julie-ads) | 2026-10-16T14:57:36Z | yes |  |
| [gitteromri-ux/julie-ceo-daily](https://github.com/gitteromri-ux/julie-ceo-daily) | 2026-10-26T12:24:13Z | yes |  |
| [gitteromri-ux/julie-ceo-launch-report](https://github.com/gitteromri-ux/julie-ceo-launch-report) | 2026-10-22T16:03:17Z | yes |  |
| [gitteromri-ux/julie-daily](https://github.com/gitteromri-ux/julie-daily) | 2026-10-11T14:07:18Z | yes |  |
| [gitteromri-ux/julie-gibson-clark-review](https://github.com/gitteromri-ux/julie-gibson-clark-review) | 2026-07-07T07:35:27Z | no | Julie Gibson Clark - Founding Faculty review (separate repo) |
| [gitteromri-ux/julie-gibson-plan](https://github.com/gitteromri-ux/julie-gibson-plan) | 2026-07-05T23:24:52Z | no |  |
| [gitteromri-ux/julie-groups-uplift](https://github.com/gitteromri-ux/julie-groups-uplift) | 2026-09-30T12:40:17Z | yes |  |
| [gitteromri-ux/julie-launch-review-20260923](https://github.com/gitteromri-ux/julie-launch-review-20260923) | 2026-09-24T11:09:14Z | yes |  |
| [gitteromri-ux/julie-live-qa](https://github.com/gitteromri-ux/julie-live-qa) | 2026-10-26T13:29:41Z | yes | Julie Masterclass live moderator Q&A desk |
| [gitteromri-ux/julie-masterclass-3tier](https://github.com/gitteromri-ux/julie-masterclass-3tier) | 2026-09-17T09:27:26Z | yes |  |
| [gitteromri-ux/julie-masterclass-blast](https://github.com/gitteromri-ux/julie-masterclass-blast) | 2026-10-18T13:56:19Z | yes |  |
| [gitteromri-ux/julie-masterclass-live](https://github.com/gitteromri-ux/julie-masterclass-live) | 2026-10-10T19:49:17Z | yes | Write mirror of Longevity-Academy/julie-masterclass: push here, the org repo syncs and deploys GitHub Pages |
| [gitteromri-ux/julie-masterclass-social-posts](https://github.com/gitteromri-ux/julie-masterclass-social-posts) | 2026-10-22T09:28:00Z | yes |  |
| [gitteromri-ux/julie-meta-banners](https://github.com/gitteromri-ux/julie-meta-banners) | 2026-08-05T06:36:44Z | no | Julie Gibson Clark · LLA Meta banner pack · every placement size, upload-ready |
| [gitteromri-ux/julie-onset-banners](https://github.com/gitteromri-ux/julie-onset-banners) | 2026-07-28T11:24:46Z | no |  |
| [gitteromri-ux/july-planning-longevity](https://github.com/gitteromri-ux/july-planning-longevity) | 2026-07-01T05:47:29Z | no |  |
| [gitteromri-ux/kerenor-adoption-en](https://github.com/gitteromri-ux/kerenor-adoption-en) | 2026-07-14T10:08:52Z | yes | Keren Or Farm: English adoption page with 33 animal profiles |
| [gitteromri-ux/latest-meta-ads](https://github.com/gitteromri-ux/latest-meta-ads) | 2026-10-20T17:53:09Z | yes |  |
| [gitteromri-ux/lawsuit](https://github.com/gitteromri-ux/lawsuit) | 2026-10-26T10:29:39Z | yes | Service performance audit: documented ETA, scope, status-accuracy and compute-waste findings across Gita Agency engagements (Jun-Aug 2026) |
| [gitteromri-ux/lla-90s-final](https://github.com/gitteromri-ux/lla-90s-final) | 2026-08-05T15:28:06Z | no | LLA 90s ad masters: Julie V24 + Courtney v18 with storyboards |
| [gitteromri-ux/lla-90s-review](https://github.com/gitteromri-ux/lla-90s-review) | 2026-08-06T08:09:35Z | no | LLA 90s cuts - autoplay review |
| [gitteromri-ux/lla-articles-deck](https://github.com/gitteromri-ux/lla-articles-deck) | 2026-07-19T20:57:15Z | no |  |
| [gitteromri-ux/lla-blueprint-vip-preview](https://github.com/gitteromri-ux/lla-blueprint-vip-preview) | 2026-10-23T07:07:42Z | yes |  |
| [gitteromri-ux/lla-campaign-chapters](https://github.com/gitteromri-ux/lla-campaign-chapters) | 2026-07-28T14:03:11Z | no |  |
| [gitteromri-ux/lla-ceo-delivery](https://github.com/gitteromri-ux/lla-ceo-delivery) | 2026-08-05T08:22:07Z | no |  |
| [gitteromri-ux/lla-chapter1-pr-coverage](https://github.com/gitteromri-ux/lla-chapter1-pr-coverage) | 2026-07-27T06:43:40Z | no | Chapter 1 PR: Live media coverage, Round 1 + Round 2, Longevity Life Academy by eTeacher Group |
| [gitteromri-ux/lla-course-checkout](https://github.com/gitteromri-ux/lla-course-checkout) | 2026-10-27T22:37:40Z | yes | Longevity Life Academy e-commerce landing page + 3-step self-service checkout |
| [gitteromri-ux/lla-courtney-cuts](https://github.com/gitteromri-ux/lla-courtney-cuts) | 2026-08-10T10:38:46Z | no |  |
| [gitteromri-ux/lla-courtney-final](https://github.com/gitteromri-ux/lla-courtney-final) | 2026-08-08T22:18:40Z | no |  |
| [gitteromri-ux/lla-delta-force](https://github.com/gitteromri-ux/lla-delta-force) | 2026-08-26T10:15:20Z | no | E-COMMERCE DELTA FORCE GO LIVE. Activation hub for Longevity Life Academy. |
| [gitteromri-ux/lla-employee-referral](https://github.com/gitteromri-ux/lla-employee-referral) | 2026-07-30T09:06:13Z | no | Longevity Life Academy by eTeacher Group: Employee Referral Program (internal campaign) |
| [gitteromri-ux/lla-favicons](https://github.com/gitteromri-ux/lla-favicons) | 2026-06-23T08:12:21Z | no |  |
| [gitteromri-ux/lla-final-5-articles](https://github.com/gitteromri-ux/lla-final-5-articles) | 2026-07-22T09:22:15Z | no | LLA Final 5 approved articles: full text mockups for outlet assignment |
| [gitteromri-ux/lla-funnel-analysis-sep14](https://github.com/gitteromri-ux/lla-funnel-analysis-sep14) | 2026-09-16T07:21:28Z | no |  |
| [gitteromri-ux/lla-funnel-analysis-sep9-15](https://github.com/gitteromri-ux/lla-funnel-analysis-sep9-15) | 2026-09-15T23:42:33Z | no |  |
| [gitteromri-ux/lla-funnel-deck](https://github.com/gitteromri-ux/lla-funnel-deck) | 2026-09-06T08:26:05Z | no | LLA ecommerce funnel performance Sep 3-6 2026 |
| [gitteromri-ux/lla-gal-september-2026](https://github.com/gitteromri-ux/lla-gal-september-2026) | 2026-10-12T09:33:31Z | yes | LLA GAL board report September 2026 (Excel + PDF + sources) |
| [gitteromri-ux/lla-growth-engine](https://github.com/gitteromri-ux/lla-growth-engine) | 2026-08-04T21:57:08Z | yes | LLA Growth Engine: full-funnel ecommerce marketing system for The Longevity Blueprint |
| [gitteromri-ux/lla-handoff-pack](https://github.com/gitteromri-ux/lla-handoff-pack) | 2026-09-02T05:38:45Z | yes | Longevity Life Academy - ecommerce and Meta media handoff pack |
| [gitteromri-ux/lla-homepage-demo](https://github.com/gitteromri-ux/lla-homepage-demo) | 2026-07-20T11:01:14Z | no |  |
| [gitteromri-ux/lla-julie-animations](https://github.com/gitteromri-ux/lla-julie-animations) | 2026-08-07T13:18:05Z | no | Julie Gibson Clark data animations and opening buildup storyboard for Longevity Life Academy |
| [gitteromri-ux/lla-julie-communications-plan](https://github.com/gitteromri-ux/lla-julie-communications-plan) | 2026-09-24T12:55:45Z | no |  |
| [gitteromri-ux/lla-julie-communications-plan-v2](https://github.com/gitteromri-ux/lla-julie-communications-plan-v2) | 2026-09-01T09:52:33Z | no | Julie communications plan V2: the Longevity Masterclass launch |
| [gitteromri-ux/lla-julie-cuts](https://github.com/gitteromri-ux/lla-julie-cuts) | 2026-08-10T07:36:13Z | no | LLA: Julie 90s / 60s / 45s launch cuts |
| [gitteromri-ux/lla-julie-letter](https://github.com/gitteromri-ux/lla-julie-letter) | 2026-09-07T15:14:59Z | no | Communications plan letter for Julie · full public site |
| [gitteromri-ux/lla-julie-masterclass](https://github.com/gitteromri-ux/lla-julie-masterclass) | 2026-09-02T11:01:15Z | yes |  |
| [gitteromri-ux/lla-julie-pr-articles](https://github.com/gitteromri-ux/lla-julie-pr-articles) | 2026-08-07T12:38:54Z | no | Julie Gibson Clark PR article pack, 4K downloads, Longevity Life Academy |
| [gitteromri-ux/lla-julie-review](https://github.com/gitteromri-ux/lla-julie-review) | 2026-07-09T16:32:46Z | no | LLA: Julie & Bryan chapters for review with Julie |
| [gitteromri-ux/lla-julie-ugc-ads](https://github.com/gitteromri-ux/lla-julie-ugc-ads) | 2026-10-19T09:39:51Z | yes |  |
| [gitteromri-ux/lla-julie-videos](https://github.com/gitteromri-ux/lla-julie-videos) | 2026-09-02T06:53:57Z | no |  |
| [gitteromri-ux/lla-marketing-dashboard](https://github.com/gitteromri-ux/lla-marketing-dashboard) | 2026-10-07T04:28:13Z | yes |  |
| [gitteromri-ux/lla-master-deck](https://github.com/gitteromri-ux/lla-master-deck) | 2026-07-21T13:31:55Z | no | LLA Press Release Master Deck: final approved articles + chosen Julie Gibson Clark stories |
| [gitteromri-ux/lla-masterclass-assets](https://github.com/gitteromri-ux/lla-masterclass-assets) | 2026-10-27T09:59:37Z | yes | Longevity Life Academy Masterclass: final creative assets |
| [gitteromri-ux/lla-masterclass-attendees](https://github.com/gitteromri-ux/lla-masterclass-attendees) | 2026-10-27T05:50:23Z | yes | Longevity Blueprint offer page for Julie Masterclass attendees (link-only, noindex). Clone of pages.dev funnel; production untouched. |
| [gitteromri-ux/lla-masterclass-emails](https://github.com/gitteromri-ux/lla-masterclass-emails) | 2026-10-22T12:45:54Z | yes | LLA Julie Masterclass lifecycle emails |
| [gitteromri-ux/lla-masterclass-emails-3tier](https://github.com/gitteromri-ux/lla-masterclass-emails-3tier) | 2026-09-24T13:25:52Z | yes | LLA Julie Masterclass lifecycle emails, 3-tier edition (Standard 9 / VIP 9 / Full Course + VIP free) |
| [gitteromri-ux/lla-masterclass-film-series](https://github.com/gitteromri-ux/lla-masterclass-film-series) | 2026-07-09T16:31:04Z | no |  |
| [gitteromri-ux/lla-masterclass-press](https://github.com/gitteromri-ux/lla-masterclass-press) | 2026-09-01T11:04:43Z | no | Round-three press articles for the Longevity Masterclass launch |
| [gitteromri-ux/lla-masterclass-syllabus](https://github.com/gitteromri-ux/lla-masterclass-syllabus) | 2026-10-27T22:42:32Z | yes | The Longevity Masterclass one-hour syllabus, prepared for Julie Gibson Clark |
| [gitteromri-ux/lla-meta-ad-sizes](https://github.com/gitteromri-ux/lla-meta-ad-sizes) | 2026-08-12T06:19:26Z | no | Longevity Life Academy Meta and Instagram paid ad sizes |
| [gitteromri-ux/lla-meta-banners-gallery](https://github.com/gitteromri-ux/lla-meta-banners-gallery) | 2026-08-05T01:15:48Z | no | Longevity Life Academy: Meta &amp; Instagram ad banners across 3 versions, 4 sizes each. Ready for upload. |
| [gitteromri-ux/lla-meta-ig-ad-sizes](https://github.com/gitteromri-ux/lla-meta-ig-ad-sizes) | 2026-09-27T19:26:46Z | no | Longevity Life Academy: Meta & Instagram paid media master size pack: 2 banners x 5 exact accepted sizes, safe-zone verified, download-ready PNGs. |
| [gitteromri-ux/lla-pr-article-ads](https://github.com/gitteromri-ux/lla-pr-article-ads) | 2026-07-30T09:36:02Z | no | LLA PR article ads: Meta and Instagram creative pack, 4 articles x 4 exact placement sizes with post copy |
| [gitteromri-ux/lla-pr-kit](https://github.com/gitteromri-ux/lla-pr-kit) | 2026-07-21T13:27:33Z | no |  |
| [gitteromri-ux/lla-privacy-policy](https://github.com/gitteromri-ux/lla-privacy-policy) | 2026-09-15T12:32:37Z | no | eTeacher / Longevity Life Academy privacy policy: verbatim original + Longevity Blueprint health-data update |
| [gitteromri-ux/lla-promo-emails](https://github.com/gitteromri-ux/lla-promo-emails) | 2026-07-21T11:50:32Z | no | LLA campaign: LPs + 4 promo emails + brand assets (LGV) |
| [gitteromri-ux/lla-redesign-deck](https://github.com/gitteromri-ux/lla-redesign-deck) | 2026-07-09T15:20:05Z | no |  |
| [gitteromri-ux/lla-s09-s10-downloads](https://github.com/gitteromri-ux/lla-s09-s10-downloads) | 2026-08-07T08:45:03Z | yes | LLA Scripts 09/10: Courtney editing brief + full-frame video masters |
| [gitteromri-ux/lla-site-live](https://github.com/gitteromri-ux/lla-site-live) | 2026-10-10T19:50:14Z | yes | Write mirror of Longevity-Academy/Longevity-Academy.github.io: push here, the org repo syncs and deploys GitHub Pages |
| [gitteromri-ux/lla-social-golive](https://github.com/gitteromri-ux/lla-social-golive) | 2026-08-24T13:08:30Z | no | Longevity Life Academy: organic Facebook & Instagram go-live pack: 23 ready posts, exact platform sizes, full page info |
| [gitteromri-ux/lla-thank-you](https://github.com/gitteromri-ux/lla-thank-you) | 2026-06-15T14:33:42Z | no | Standalone thank-you page for Longevity Life Academy form submissions |
| [gitteromri-ux/lla-turnaround-plan](https://github.com/gitteromri-ux/lla-turnaround-plan) | 2026-07-20T11:07:11Z | no |  |
| [gitteromri-ux/lla-v25-recut](https://github.com/gitteromri-ux/lla-v25-recut) | 2026-08-05T15:05:31Z | no | LLA Julie V25 / Courtney v17 corrected masters: download page |
| [gitteromri-ux/lms-image-pack](https://github.com/gitteromri-ux/lms-image-pack) | 2026-07-28T08:32:50Z | no |  |
| [gitteromri-ux/longevity-ads-presentation](https://github.com/gitteromri-ux/longevity-ads-presentation) | 2026-05-07T13:46:05Z | no |  |
| [gitteromri-ux/longevity-assets](https://github.com/gitteromri-ux/longevity-assets) | 2026-08-05T06:56:54Z | yes |  |
| [gitteromri-ux/longevity-banner](https://github.com/gitteromri-ux/longevity-banner) | 2026-05-04T11:21:43Z | no |  |
| [gitteromri-ux/longevity-july-plan](https://github.com/gitteromri-ux/longevity-july-plan) | 2026-07-02T19:51:43Z | no |  |
| [gitteromri-ux/longevity-life-academy](https://github.com/gitteromri-ux/longevity-life-academy) | 2026-08-25T04:55:46Z | yes | Longevity Life Academy by eTeacher Group |
| [gitteromri-ux/longevity-life-academy-ads-deck](https://github.com/gitteromri-ux/longevity-life-academy-ads-deck) | 2026-05-07T14:59:20Z | no |  |
| [gitteromri-ux/longevity-pilot-command](https://github.com/gitteromri-ux/longevity-pilot-command) | 2026-07-05T12:50:42Z | no | Longevity Pilot Command: interactive CEO planning dashboard |
| [gitteromri-ux/longevity-productions-courtney-julie](https://github.com/gitteromri-ux/longevity-productions-courtney-julie) | 2026-07-09T09:49:46Z | no |  |
| [gitteromri-ux/masterclass-rfp](https://github.com/gitteromri-ux/masterclass-rfp) | 2026-10-25T14:17:04Z | yes | Masterclass sales sprint RFP: Claude vs Grok vs Perplexity |
| [gitteromri-ux/personalix](https://github.com/gitteromri-ux/personalix) | 2026-07-23T11:16:24Z | yes | Personalix: Candidate first. Designed for people. AI-powered, human-first recruitment platform. |
| [gitteromri-ux/play-paros-redesign](https://github.com/gitteromri-ux/play-paros-redesign) | 2026-08-17T04:59:13Z | no | Premium editorial redesign of PLAY Paros (Brown Hotels, Cyclades): guest site + internal F&B strategy brief |
| [gitteromri-ux/rank-lens-analysis](https://github.com/gitteromri-ux/rank-lens-analysis) | 2026-04-29T14:50:46Z | no | Rep Rank SOV Sweet-Spot Analysis: Hebrew + Biblical |
| [gitteromri-ux/rosen-banners-review](https://github.com/gitteromri-ux/rosen-banners-review) | 2026-05-15T19:20:23Z | no |  |
| [gitteromri-ux/serious-claims](https://github.com/gitteromri-ux/serious-claims) | 2026-09-30T14:12:47Z | yes | Documented cases: deliveries that did not match Omri's written request (evidence log) |
| [gitteromri-ux/ugc-prod](https://github.com/gitteromri-ux/ugc-prod) | 2026-10-01T16:16:00Z | yes |  |
| [gitteromri-ux/vj-magic-site](https://github.com/gitteromri-ux/vj-magic-site) | 2026-06-16T14:56:06Z | no | VJ Magic: prompt-driven event production. Premium WebGL marketing site. |
| [gitteromri-ux/vj-magic-site-v2](https://github.com/gitteromri-ux/vj-magic-site-v2) | 2026-06-17T07:41:01Z | no | VJ Magic: V2 immersive award-winning redesign |
| [gitteromri-ux/ziv-book-cover-directions](https://github.com/gitteromri-ux/ziv-book-cover-directions) | 2026-09-28T11:05:48Z | yes | כך נפלנו כך נקום: 10 split-screen cover background directions (private review) |



# Date-ordered operating record

These are retained daily records. Their open questions are historical at their stated date; later evidence may supersede them. Gaps in dates are missing daily records, not proof that no work happened.



## Dream Learnings: 2026-09-30

### Activity Summary

Omri Gitter returned to PRNOW account access while the original credit-purchase receipt remained unresolved in the session evidence. (original session `595352b8-3a75-4932-956f-68633a201347`)

- **Urgent account access:** On 2026-09-29, Omri requested the login details immediately. The assistant supplied them, but the available conversation does not establish that Omri subsequently logged in. (original session `595352b8-3a75-4932-956f-68633a201347`)
- **Receipt recovery boundaries:** The earlier exchange distinguishes the original $399 wallet purchase from a $149 package invoice. Omri rejected email outreach and a substitute document; the assistant acknowledged that it had not recovered the requested receipt or verified the actual card descriptor. The renewed access request did not close those gaps. (original session `595352b8-3a75-4932-956f-68633a201347`)

### Sessions Processed

- 595352b8: Reprocessed the extended session through 2026-09-29; urgent PRNOW access details were supplied, without new receipt-recovery evidence. (original session `595352b8-3a75-4932-956f-68633a201347`)

### Open Questions

- Where is the original PRNOW $399 credit-purchase receipt from 2026-07-23, and what merchant descriptor identifies its card charge?
- Was the “Remaining Invoice - PR Now” correspondence resolved with Keren Ziv, and do its attachments contain the original credit-purchase receipt? The connector messages lack canonical URLs; attachment contents were not inspected.
- Did the LLA checkout complete the physical top-ten iOS and top-ten Android matrix and clear HOLD?
- Were Standard, VIP, and Blueprint purchase flows certified with authorized Card and PayPal transactions?
- Is PayPal visibly initialized on every maintained production checkout surface?
- Did Meta’s modified-fbclid diagnostic stop accumulating affected events, and was Ad Set 2 attribution proven?
- Were QA CRM orders `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, and unpaid VIP order `8032752` removed or voided?
- Which CRM order was the reported 2026-09-21 sale, what was paid, and was it ecommerce or sales-rep driven?
- Were the remaining French Atelier topics completed with exact media, and was comment-to-DM proven end to end?
- Were Sprout’s disconnected French Atelier and LLA profiles restored?
- Which French Atelier exports map to September, the current week, and July–August?
- Were the Morning invoice previews approved, Tax Authority authorization restored, and the invoices issued?
- Were the rejected LLA presenter takes replaced and accepted for naturalness and continuity?
- Which VIP Blueprint-credit amount and redemption terms are approved? Follow-up variants advertise `$79` versus `$249`, and the verified `JULIE249` tuition reduction is `$150`.

### General Procedural Notes

- Connector records without canonical source URLs remain research evidence, not new cited wiki claims. A generated social report does not certify profile restoration, and marketing payment options do not certify checkout behavior.


## Dream Learnings: 2026-10-01

### Activity Summary

Omri Gitter’s LLA masterclass work combines paid acquisition, mobile conversion design, and source-faithful film editing. Handovers record his campaign choices and design approval; inspection establishes repository changes and reported deployment checks, not payment or campaign-performance certification. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/97271cf58b8dde231a6a64752e9743564fb7132c)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be))

- **Controlled paid acquisition:** The handover records Omri choosing hard US age limits of 45–64 with Advantage+ audience off, then requiring interests AND buyer signals. He selected the single-mom thumbnail for two Julie video ads. The recorded learning-window commitment runs to 2026-10-03 at 18:32 IDT, after the thumbnail change-not the earlier targeting edit. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f))
- **Mobile purchase presentation:** Omri’s recorded approval covers larger phone typography, stronger VIP contrast, consistent LLA-blue CTAs, and a floating enrollment control hidden inside checkout. The handover reports responsive guard checks; it does not certify authorized transactions or the full physical-device matrix. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/97271cf58b8dde231a6a64752e9743564fb7132c))
- **Masterclass film adaptation:** The v6 source preserves the original film’s card hierarchy, limits Zoom to one appearance, and specifies a continuous music bed. Its review page describes twelve cutdowns but marks all four aspect-ratio groups as rendering; this is not evidence of accepted final media. ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be))

### Sessions Processed

- No new or extended session evidence beyond the 2026-09-30 synthesis; six previously cited sessions were loaded only for hygiene and correctness checks.

### Open Questions

- Where is the original PRNOW $399 credit-purchase receipt from 2026-07-23, and what merchant descriptor identifies its card charge?
- Was the “Remaining Invoice - PR Now” correspondence resolved with Keren Ziv, and do its attachments contain the original credit-purchase receipt? No canonical message URLs were returned, and attachment contents remain uninspected.
- Did the LLA checkout complete the physical top-ten iOS and top-ten Android matrix and clear HOLD?
- Were Standard, VIP, and Blueprint purchase flows certified with authorized Card and PayPal transactions?
- Is PayPal visibly initialized on every maintained production checkout surface?
- Did Meta’s modified-fbclid diagnostic stop accumulating affected events, and was Ad Set 2 attribution proven?
- Were QA CRM orders `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, and unpaid VIP order `8032752` removed or voided?
- Which CRM order was the reported 2026-09-21 sale, what was paid, and was it ecommerce or sales-rep driven?
- Were the remaining French Atelier topics completed with exact media, and was comment-to-DM proven end to end?
- Were Sprout’s disconnected French Atelier and LLA profiles restored?
- Which French Atelier exports map to September, the current week, and July–August?
- Were the Morning invoice previews approved, Tax Authority authorization restored, and the invoices issued?
- Were the rejected LLA presenter takes replaced and accepted for naturalness and continuity?
- Which VIP Blueprint-credit amount and redemption terms are approved? The earlier purchase brief specifies `$79` credit, while the corrected `JULIE249` course pricing implies a `$150` total reduction, not the coupon name’s number. (original session `f0880387-3aa3-4161-85ac-890ecca87e46`) (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)
- What did Set 01 achieve after its recorded 48-hour no-touch window ending 2026-10-03 at 18:32 IDT? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f))
- Were the v6 film’s cutdowns finished and visually accepted, and were its retained Zoom streak/logo tiles and first-punch-in blink accepted or repaired? ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be))

### General Procedural Notes

- Four user-behavior observations were routed off the user’s entity page into the preference-candidate workflow; all were already covered by the existing ledger.


## Dream Learnings: 2026-10-14

### Activity Summary

Omri Gitter focused on Julie masterclass acquisition, credible school-email invitations, and mobile purchase presentation, alongside French Atelier’s Culture Capsules launch. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)

- **Acquisition and attribution:** Omri requested ad-set decisions against a 20-sales/$150-CPA target, challenged mismatched CRM/Meta explanations, and authorized changes limited to Sets 03/05 plus card-gold pauses in 03/04. The final session reports 11 non-test paid orders from ten people for the Israel day 2026-10-14, matching Meta’s $659; settlement evidence was not inspected. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **School invitations and mobile design:** Omri replaced the cross-product coupon pitch with an automatic 36% masterclass discount for 72 hours, demanded authentic Rosen/IIBS context, and required the final emails at the original circulated link. The assistant reports eight variants there; repository evidence supports consolidation, not actual sending. Mobile revisions remain separate from payment certification. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/d23be44ce26d9b09973960db0d247cea2c5ef149))
- **Callable buyers and Culture Capsules:** Omri requested a paid-VIP-only spreadsheet with names, phones, and emails; the assistant’s final roster report distinguishes 26 real buyers from one test. For Culture Capsules he requested clearer typography, distinct branded pricing cards, and a public media plan; the reported preview is not a production merge. (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`) (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`)

### Sessions Processed

- 219ddd45: Golden CAPI audit, paid-order reconciliation, targeted campaign edits and pending proposals. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 5619952e: Segmented school invitations, mobile revisions, offer wording and same-link correction. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- d3d47d7a: Hourly reporting, projected LPV, unsupported CRM score and wallet investigation. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)
- 32a35d34: Literal output exclusions and correction of click-hour/purchase-time confusion. (original session `32a35d34-ee27-4481-8d88-0843d24f7ad7`)
- a572ab4f: Paid VIP roster, profile recovery report and exclusion of one test buyer. (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`)
- 41572080: Ad-set reporting format and the stated daily target; no changes executed in that thread. (original session `41572080-cfcc-4c6d-af2a-b8f571a26054`)
- 1f127955: Culture Capsules preview, branded cards, media-plan handoff. (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- 90701961: Search for another account’s dark Culture Capsule build; exact source unidentified. (original session `90701961-41f5-40dc-a674-a33926c9c165`)
- ae78e3a1: Requested graphic-overlay reversal; no text recovered and outcome disputed. (original session `ae78e3a1-3fa1-4828-9b20-87eeee89b0d6`)
- 595352b8: Extended PRNOW account/wallet reconciliation; original receipt remains missing. (original session `595352b8-3a75-4932-956f-68633a201347`)

### Notes distilled

- Incorporated: Culture Capsule project identity → `projects/french-atelier-culture-capsules`, verified against its source session. (original session `90701961-41f5-40dc-a674-a33926c9c165`)
- Already covered: historical checkout, attribution, video, French Atelier, and PR delivery constraints remain attached to their existing subjects; this review does not establish new activity.
- Deferred: source-less Gita Machine/design claims and note-only scaling/game-plan details lack claim-level support in the available turns; no new standing command or budget rule was inferred.

### Reconciliation Notes

- Source review of the earlier school pilot establishes an unnamed third school, with French Atelier only a lead-generation comparator. Its page and links now use the neutral direct-ecommerce-school title; the original brief’s price, budget, duration, and unresolved optimization choice are preserved. (original session `65fa5ab2-d190-4705-9d33-816e87f723fb`)
- Scoped wallet reconciliation: the main-site/Blueprint Card/PayPal-only change does not apply to Julie. Julie’s maintained payment contract includes both wallets; that configuration is not proof of success or the cause of abandonment. ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/blob/main/assets/julie-payment-safety.js)) ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/6b698eff26825a87c25a64a3a60c8a2fdf68dbb4))

### Open Questions

- Is Julie’s Apple Pay actually failing on current physical iPhones, and is any removal authorized? Maintained Julie source includes both wallets; the main-site Card/PayPal-only commit explicitly excludes Julie. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/blob/main/assets/julie-payment-safety.js)) ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/6b698eff26825a87c25a64a3a60c8a2fdf68dbb4))
- Where is the order-level CRM paid-order ↔ processor settlement/refund ↔ Meta ledger, including tests and upgrades? The 11-order session report is not settlement certification. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Did the latest mobile release pass the full physical top-ten iOS/Android matrix, authorized Standard/VIP/Blueprint Card/PayPal transactions, and visible PayPal initialization on every maintained surface?
- Did modified-fbclid diagnostics and the duplicate-server-event investigation clear, and was Blueprint Ad Set 2 attribution proven? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were QA orders `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, `8032752`, and newer unpaid tests `8050691`, `8050693`, `8050702`, `8050810` voided or removed? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Which CRM order identifies the reported 2026-09-21 sale, with amount and ecommerce/rep origin?
- Were the eight invitation variants installed or sent, and what are the actual ActiveCampaign automation triggers, enrollment counts, and send results? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Does Set 01 have an order-reconciled result for the exact learning-window endpoint? Later daily reports show attributed events, not an hour-bounded settled outcome. ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Did subsequent readbacks confirm the inert value-rule substitution and desired 03/05 targeting without collateral changes? A generic approval is not evidence of the literal freeze-lift sentence. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- Which current dark Culture Capsule source matches the other account’s pricing/fold work, and was the French Atelier staging preview promoted and payment-tested? (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`) (original session `90701961-41f5-40dc-a674-a33926c9c165`)
- Was the original PRNOW $399 top-up receipt found, what is its merchant descriptor, and was Keren Ziv’s invoice correspondence resolved? Compare the two R6LYD3K attachment contents before counting them twice. (original session `595352b8-3a75-4932-956f-68633a201347`)
- Were French Atelier’s remaining publishing topics, exact-media schedules, and comment-to-DM test completed; were the French Atelier/LLA Sprout profiles restored; and which exports map to September, the relevant week, and July–August?
- Were Morning invoice previews approved, authorization restored, and invoices issued?
- Were rejected presenter takes replaced and accepted, and were Julie v6 cutdowns rendered and visually accepted?

#### VIP course benefit

You replaced the cross-product coupon pitch in the invitation emails, but the approved underlying VIP Blueprint benefit and redemption terms still need a single authoritative definition. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

- What Blueprint benefit and redemption terms should VIP buyers actually receive, separate from the automatic masterclass discount? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)

### General Procedural Notes

- Ten conversation files contain corrections but no preloaded tool trajectories; tool operations and completion claims in their summaries are therefore attributed to the assistant, not independently re-certified.
- An HTTP response, repository commit, emulated checkout, or visible wallet button is not a paid settlement or real-device wallet test. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))


## Dream Learnings: 2026-10-15

### Activity Summary

Omri Gitter worked on Julie masterclass acquisition, community-offer presentation and a speaker deck, alongside a personal lease renewal. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- **Campaign decisions and buyer evidence:** Omri approved Canada excluding Quebec for Set 03, concentrated its creatives, and returned Set 05 to lowest-cost bidding after weak delivery. Readbacks support those changes, not the 20-sale goal. CRM recovery identified one order’s last-click ad, not settlement. He also requested removing two test rows from the VIP workbook. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`)
- **Separate community experience:** Omri requested a hidden-link 72-hour offer and repeatedly rejected inadequate mobile pricing/design fixes. A separate clone and design handoff were reported; final visual acceptance and a subsequent approved port remain unestablished. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)
- **Julie’s teaching materials:** Omri approved removing supplements from the speaker deck and replacing that block with a daily-routine walkthrough. The assistant reported a revised 16-slide HTML deck using longevity imagery, not Julie photographs; publication and acceptance remain open. (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- **Lease renewal:** Omri narrowed contract edits, retained guaranty pages without emailing guarantors, and arranged tenant-first signatures. DocuSign readback confirms invitations sent, not completed signatures. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### Sessions Processed

- 219ddd45: extended campaign decisions, API readbacks and operating-handoff rules. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 59596b49: recovered CRM last-click identity and corrected reporting/strategy assumptions. (original session `59596b49-4843-4756-b08f-17722a531c89`)
- 5619952e: extended pause test and distinction between timestamps and learning evidence. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- d3d47d7a: deployed tracking coverage patch; accepted diagnostic events, not traffic-wide certification. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)
- adbe076f: separate community-offer clone and presentation revisions. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- 8a2c0e39: rejected mobile fixes, undeployed phone-guard branch and design-only handoff. (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)
- 15bf3163: corrected public-coupon history and production/clone identity. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- a572ab4f: final two-row removal and reported 27-person VIP workbook. (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`)
- 2c8c0ade: masterclass speaker deck and supplement exclusion. (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- e2f0868a: lease revisions and signature routing. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)
- a1dcbba2: follow-up question; no new accepted video change or campaign execution. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- 52f19091: bare session link; no recoverable substantive task, summary skipped. (original session `52f19091-3d1d-460b-aafe-700433e3ed43`)
- c894a65f: single coin-side clarification; summary skipped, no durable personal inference. (original session `c894a65f-6cb3-422b-b3a6-a97db07bcd46`)

### Notes distilled

- Reconciled historical Julie ad-set guardrails with later explicit configuration approvals → `projects/lla-julie-meta-pilot`. Prior rejections are not permanent prohibitions. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Incorporated source-supported reporting, context-reuse and process-complaint observations through preference reconciliation; note-only interpretations were not admitted. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

### Open Questions

- Has the operating-agent handoff been installed, and were existing 05:00/13:00/16:45 automations coordinated? The strategy document does not prove automation deployment. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Does the deployed tracking patch have Events Manager and real-traffic coverage evidence, and was the literal item-specific freeze-lift requirement satisfied? Accepted test events do not settle these questions. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- Is Julie Apple Pay successful on physical iPhones, and has the maintained mobile/Card/PayPal/wallet matrix passed? Julie wallet configuration and Linux WebKit tests are not physical-device payment certification. ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/julie-masterclass-handover-2026-10-09.md))
- Where is the order-level CRM ↔ payment settlement/refund ↔ Meta ledger, including upgrades and test exclusions? Last-click order identification is not payment evidence. (original session `59596b49-4843-4756-b08f-17722a531c89`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Did modified-fbclid and duplicate-server diagnostics clear, and was Blueprint Ad Set 2 attribution proven? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were QA orders 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752 and unpaid tests 8050691, 8050693, 8050702, 8050810 voided or removed? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Which CRM order establishes the reported September 21 sale, and does Set 01 have a settled result for its exact learning-window endpoint? ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Were the eight school invitations installed/sent, with actual automation triggers and enrollment/send counts? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Which dark Culture Capsule source matches the other account’s work, and was the staging preview promoted and payment-tested? (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- Was the original PRNOW $399 receipt recovered and Keren Ziv’s invoice thread resolved? Compare R6LYD3K attachment contents before counting twice. (original session `595352b8-3a75-4932-956f-68633a201347`)
- Were French Atelier publishing/DM work, Sprout profile restoration and correctly scoped exports completed; were Morning invoice previews approved and issued; and were replacement presenter takes and Julie v6 cutdowns accepted?
- Were the revised speaker deck and community page accepted/published, and did any approved design-only port preserve production checkout/tracking? (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)
- Did the lease complete tenant-first and Omri-second signatures, with guaranty pages handled separately? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

#### VIP course benefit

You replaced the cross-product invitation pitch, but the underlying VIP Blueprint benefit still needs authoritative redemption terms. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

- What benefit and redemption terms should VIP buyers receive, separate from the automatic masterclass discount? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

#### Lease wording

You limited the lease to specific corrections, but the assistant’s final disclosure still included two unrequested appendix sentences. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should those extra appendix sentences remain, and should Sandra Gitter be included as a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- A Meta daily budget is not a hard spend ceiling; `budget = spend + allowance` does not guarantee a stop at that allowance. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- Distinguish API configuration, test-event acceptance, attributed events and settled orders; an unchanged learning timestamp does not prove preservation of a positive purchase counter. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`)
- Read-only connector coverage was GitHub and Google Calendar/Gmail. Historical handovers were not treated as current campaign readbacks; mailbox results without canonical record URLs were not promoted to wiki claims.


## Dream Learnings: 2026-10-16

### Activity Summary

Omri Gitter focused on Julie’s mobile checkout reliability and premium offer presentation while maintaining campaign oversight toward the 20-sale daily goal. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **Checkout recovery:** Omri supplied third-party iPhone retests and challenged broad completion claims. The isolated preview gained SDK retry, a real PayPal fallback and removal of the blank card box. The final relayed test found tappable PayPal on iPhone 16 Pro Max and card/Apple Pay rendering on iPhone 15; neither proves a completed payment. Production promotion is not established. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Presentation and scope:** Omri approved only the pricing cards, 72-hour strip and payment fix initially, then requested distinct tier colors, concrete benefit copy, larger logo and working direct-checkout buttons. The assistant reported those changes on the preview; the final visual revision still lacks acceptance. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Campaign oversight:** A scheduled read reported nine Meta-attributed purchases for the Israel reporting day, below the goal and not settlement-certified. The 05:00 automation actually ran and its prompt was changed to read-only; broader operating-agent installation remains unresolved. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Sessions Processed

- a1dcbba2: extended checkout diagnosis, preview iterations, third-party device retests and offer/navigation corrections. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- 219ddd45: new terminal campaign read and verified read-only edit to the 05:00 automation; prior summaries retained for unchanged sessions. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Open Questions

- Is the separate operating-agent handoff installed, and are the 13:00/16:45 jobs coordinated with the now-read-only 05:00 automation? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Does the tracking coverage patch have Events Manager and real-traffic evidence, and was its item-specific freeze lift plus required guard satisfied? The merged PR and accepted diagnostic events do not answer those questions. ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/projects/julie-tracking-freeze/README.md))
- Was the final checkout preview explicitly approved and promoted, and does the promoted build preserve protected tracking, attribution, payment-safety bytes and ActiveCampaign triggers? (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- Did real card, Apple Pay and PayPal payments pass the maintained device matrix? The final relayed BrowserStack test proves only iPhone 15 form/wallet rendering and iPhone 16 Pro Max PayPal fallback; the latter still cannot load Airwallex. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/julie-masterclass-handover-2026-10-09.md))
- Where is the order-level CRM ↔ payment settlement/refund ↔ Meta ledger, including upgrades and test exclusions? Neither last-click identity nor Meta purchase counts establish settlement. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `59596b49-4843-4756-b08f-17722a531c89`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Did modified-fbclid and duplicate-server diagnostics clear in a fresh read, and was Blueprint Ad Set 2 attribution proven? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were QA orders 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752 and unpaid tests 8050691, 8050693, 8050702, 8050810 voided or removed? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Which CRM order establishes the reported 2026-09-21 sale, and does Set 01 have a settled result for its exact learning-window endpoint? ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Were the eight school invitations installed/sent, with actual triggers and enrollment/send counts? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Which dark Culture Capsule source matches the other account’s work, and was the staging preview promoted and payment-tested? (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- Was the original PRNOW $399 receipt recovered and Keren Ziv’s invoice thread resolved, with R6LYD3K attachment contents compared before counting twice? (original session `595352b8-3a75-4932-956f-68633a201347`)
- Were French Atelier publishing/DM work, Sprout restoration and correctly scoped exports completed; were Morning invoice previews approved/issued; and were replacement presenter takes and Julie v6 cutdowns accepted?
- Were the speaker deck and separate community page accepted/published? The new checkout-recovery preview is not evidence of either acceptance. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- Did the lease complete tenant-first and Omri-second signatures, with guaranty pages handled separately? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

#### VIP course benefit

You requested clearer course-benefit copy and rejected cash-back phrasing, but the $249 Blueprint credit still needs authoritative redemption terms. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

- What exact benefit, eligibility and redemption terms should VIP buyers receive, separate from the automatic masterclass discount and the full 18-week course? (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

#### Lease wording

You limited the lease to specific corrections, but the extra appendix sentences and co-lessor wording still need a decision. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be included as co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)


## Dream Learnings: 2026-10-17

### Activity Summary

Omri Gitter concentrated on Julie’s checkout interruption, rollback evidence and campaign controls, repeatedly challenging conclusions that exceeded the available records. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **Payment recovery and rollback:** Omri relayed passing forced-block guest-card and iPhone 15 rendering tests, authorized production release, then rejected further visual revisions. In a separate investigation they explicitly requested rollback to the 2026-10-15 build. The tests did not complete card, Apple Pay or PayPal payments, and rollback does not establish the cause of the interruption. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- **Forensic accountability:** Omri demanded a reverse audit after reporting five post-rollback sales. The assistant withdrew its zero-paid claims when checkout telemetry proved incomplete. They also challenged blanket “golden” tracking assurances: rollback retained the merged coverage patch, rather than restoring the frozen tag. (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Campaign and order controls:** Omri ordered exact budget-only changes, ending at $1,990 daily across five sets. They corrected unique-buyer comparisons and the assumption that repeat payments must be accidental. The latest scheduled report shows five Meta purchases for 2026-10-17, but no order-to-event or settlement reconciliation. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Sessions Processed

- a1dcbba2: extended recovery tests, explicit go-live, rejected designs, campaign corrections and budget reductions. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- af49d9a8: investigation, evidence-limit correction and explicitly approved production rollback. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- 6850a0ab: reverse audit, incomplete telemetry and withdrawn zero-paid conclusions; further device test attempted. (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- 219ddd45: extended budget execution, tracking review, purchase-count corrections and three read-only scheduled prompts. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Notes distilled

- Reviewed payment ownership, payment-audit and device-evidence notes: ownership/reporting distinctions already covered by Julie subject pages; uncited device-gate wording was not admitted as new evidence. (original session `49da238d-ec07-4c74-85c2-42e13984b328`) (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)
- Historical pricing-card rejection is scoped to its earlier build; the later white/light-blue production request and subsequent rollback govern recovery presentation. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`)
- Historical-context and net-first reporting notes reinforce existing preference topics; recent order-count corrections are reconciled against direct session evidence rather than treating the notes as corroboration. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `59596b49-4843-4756-b08f-17722a531c89`)

### Open Questions

- Is the separate operating-agent handoff installed? The 05:00, 13:00 and 16:45 jobs now have actual wakes and read-only prompts in the trajectory, resolving the narrower schedule-existence gap. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Was the tracking coverage patch’s literal item-specific freeze lift granted, and did its required guard pass? What do Events Manager, real-traffic matching and deduplication show for the rollback build? PR merge and event acceptance alone do not answer these questions. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/projects/julie-tracking-freeze/README.md))
- What caused the checkout interruption? Compare the exact changed build with rollback production on real iPhone Safari, and reconcile paid-order timing; absence from worker logs cannot prove no payment. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- Did real card, Apple Pay and PayPal payments pass the maintained device matrix? Forced-block guest-card opening and control-wallet rendering are not completed-payment evidence. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `6850a0ab-974e-41db-82e5-f33e6fd752a2`)
- Where is the order-level CRM ↔ payment settlement/refund ↔ Meta ledger? Resolve six CRM-paid orders including test 8054067 versus five Meta events, without assuming which event belongs to which order or whether repeat ticket purchases were intentional. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Were paid test 8054067 refunded and unpaid QA orders 8054068/8054071 removed? Prior QA backlog: 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752, 8050691, 8050693, 8050702 and 8050810. Reporting exclusion is not refund or deletion. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Did modified-fbclid and duplicate-server diagnostics clear in a fresh read, and was Blueprint Ad Set 2 attribution proven? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Which CRM order establishes the reported 2026-09-21 sale, and does Set 01 have a settled result for its exact learning-window endpoint? ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Were eight school invitations installed/sent with verified triggers and counts? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md))
- Which dark Culture Capsule source matches the other account’s work, and was staging promoted and payment-tested? (original session `1f127955-24f1-4f23-84d9-91115b5a57b7`)
- Was the original PRNOW $399 receipt recovered and Keren Ziv’s invoice thread resolved after comparing R6LYD3K attachments? (original session `595352b8-3a75-4932-956f-68633a201347`)
- Were French Atelier publishing/DM work, Sprout restoration and correctly scoped exports completed; were Morning invoice previews approved/issued; and were replacement presenter takes and Julie v6 cutdowns accepted?
- Were the speaker deck and separate community page accepted/published? Recovery-preview release and rollback do not establish either outcome. (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Did the lease complete tenant-first and Omri-second signatures, with guaranty pages handled separately? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

#### VIP course benefit

You requested clearer course-benefit copy and rejected cash-back phrasing, but the $249 Blueprint credit still needs authoritative redemption terms. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

- What exact benefit, eligibility and redemption terms should VIP buyers receive, separate from the automatic masterclass discount and the full 18-week course? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

#### Lease wording

You limited the lease to specific corrections, but the extra appendix sentences and co-lessor wording still need a decision. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be included as co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)


## Dream Learnings: 2026-10-18

### Activity Summary

Omri Gitter focused on Julie’s campaign, community launch and rollback safety, alongside board reporting and Culture Capsules delivery. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

- **Campaign decisions:** Omri approved the $99 purchaser/warm set and four creatives, then corrected CRM naming. They ordered selective existing-set budgets; the evening control check ran 3.5 hours late. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `9d666722-8f9e-4635-8aeb-6afa7b621bf8`)
- **Community and board handoffs:** Omri approved IIBS v4 with hero destinations, four US time zones and short refund terms. The fixed campaign clock and six-slide board artifacts are sourceable; complete ActiveCampaign imports/sends remain unverified. Blueprint’s direct funnel stays separate from masterclass upsell. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/Longevity-Academy/masterclass-72hours/commit/a68b6edaf2e238abf1871171c6c83fb543ec0eaf)) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/6df81d9a9298cbd38a93d20533474560856cb791)) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/5dd604eb8fdc9331ec6a8ceaed16d2d2f3e3e0fb))
- **Rollback safety:** Omri rejected unauthorized preview publication; the assistant reported restoring it without production changes. Omri corrected ten logged payments to thirteen CRM sales, not proof of unchanged files or full payment health. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- **Culture Capsules:** Omri rejected incorrect/inaccessible handoffs. Mobile fixes were eventually reported public at the existing URL; the dark-source identity and payment certification remain unresolved despite a sourceable mirror. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `0b5e32e6-fbb9-418f-a0ac-32c046b29743`) ([recorded evidence](https://github.com/gitteromri-ux/fa-capsules-launch/blob/bridge/bridge/out/capsules-site/_mirror.log))

### Sessions Processed

- 15bf3163: extended promo, rollback, unauthorized-preview and payment-count corrections. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- ad99e93f: community launch, IIBS v4, board corrections and Culture Capsules public mobile delivery. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- 219ddd45: extended conditional budget permissions, selective overrides and late evening check. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 2b7e0eda: approved purchaser-audience activation, targeting limits and unresolved static CRM URL tags. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- 9d666722: exact budget cuts, hourly metrics and correction of the wrong-page test. (original session `9d666722-8f9e-4635-8aeb-6afa7b621bf8`)
- 0b5e32e6: Culture Capsules source retrieval; remembered staging identity not located. (original session `0b5e32e6-fbb9-418f-a0ac-32c046b29743`)
- 4f3d2b6d: incomplete conversational fragment; no substantive fact or summary. (original session `4f3d2b6d-f321-4366-a0ec-fd572eaf6c8a`)

### Notes distilled

- Incorporated acquisition model and board targets → `projects/lla-october-board-update`, `projects/lla-growth-engine` and `projects/lla-course-checkout`; fixed timer and IIBS v4 → `projects/lla-julie-community-offer` and `projects/lla-julie-invitation-blast`. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- Incorporated active-audience configuration → `projects/lla-julie-purchaser-audience`; older $44/35–64 launch-review notes are superseded by the explicit GOLIVE configuration. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Mobile-publication and read-only-audit notes were admitted only at the detail supported by readable session evidence. Exact SDK exception mechanics, source/destination ad-copy IDs, seed field-completeness statistics and font-overlap diagnostics were not promoted from notes alone. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Board-verification, cache-busting and proportional-execution observations were reconciled with existing preference topics rather than duplicated. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

### Open Questions

- Is the separate operating-agent handoff installed, and how will scheduled-control punctuality be established after the 20:00 check ran at 23:35? Existing read-only base jobs and dated mutation permissions are different scopes. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Was the tracking patch’s literal item-specific freeze lift granted, and did the required guard pass? What do Events Manager, real-traffic matching and deduplication show for rollback production? ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/projects/julie-tracking-freeze/README.md))
- What caused the checkout interruption, and did real card, Apple Pay and PayPal payments pass the maintained physical-device matrix? UI rendering, hash matches and incoming sales do not answer that. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- Where is the order-level CRM ↔ payment settlement/refund ↔ Meta ledger? Reconcile the 2026-10-17 snapshots and the 2026-10-18 counts of 10 card-route logs, 12 in the five-set report and Omri’s 13 CRM sales using exact cutoffs, page origin and test exclusions. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) ([recorded evidence](https://github.com/gitteromri-ux/latest-meta-ads/blob/main/index.html))
- Were paid test `8054067` refunded and unpaid QA orders `8054068`/`8054071` removed? Prior QA backlog: `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, `8032752`, `8050691`, `8050693`, `8050702`, `8050810`. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were new-set copied URL `adGroupID` values aligned to `108814` under explicit approval? Renaming alone leaves `108813`/`108815`/`108817` mappings. Resolve 18-versus-19 staged-ad inventory and readiness without altering originals. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Do community paid-order records retain `/masterclass-72hours/`, query parameters and post-launch payment time alongside payment status? Recheck the clone’s canonical tracking guard rather than accepting either copied-code or shared-pixel assertions as runtime proof. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Were IIBS v4 and the all-email link/time/refund corrections applied to every ActiveCampaign launch variant, with intended triggers and counts? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/6df81d9a9298cbd38a93d20533474560856cb791))
- Does the community checkout still have the setup error, old refund wording and persistent forced-error state? Its 82 UI checks did not certify completed payments. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- Which dark Culture Capsule source matches the remembered build, and was French Atelier staging promoted and payment-tested? The bridge mirror supplies a source candidate, not that identity or deployment proof; recheck its recorded syllabus-PDF 404 on the actual live page. (original session `0b5e32e6-fbb9-418f-a0ac-32c046b29743`) ([recorded evidence](https://github.com/gitteromri-ux/fa-capsules-launch/blob/bridge/bridge/out/capsules-site/_mirror.log))
- Did modified-fbclid and duplicate-server diagnostics clear, was Blueprint Ad Set 2 attribution proven, and which CRM order establishes the 2026-09-21 sale and Set 01’s exact learning-window result? ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/projects/julie-tracking-freeze/README.md)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648)) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Were the original PRNOW $399 receipt and Keren Ziv’s R6LYD3K invoice thread resolved; French Atelier publishing/DM work, Sprout restoration and scoped exports completed; and Morning invoice previews approved/issued? (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were replacement presenter takes, Julie v6 cutdowns and the separate speaker deck accepted? A Meta-served v6 report and the board-deck update do not establish those acceptances. ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/5dd604eb8fdc9331ec6a8ceaed16d2d2f3e3e0fb)) ([recorded evidence](https://github.com/gitteromri-ux/latest-meta-ads/blob/main/index.html)) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- Did the lease complete tenant-first and Omri-second signatures, with guaranty pages handled separately? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

#### VIP course benefit

You requested clearer VIP course-benefit copy, but the $249 credit’s authoritative eligibility and redemption terms are still undecided. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

- What exact benefit and redemption terms should VIP masterclass buyers receive, separate from the new Blueprint VIP-tier plan? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

#### Lease wording

You limited the lease to specific corrections, but the extra appendix sentences and co-lessor wording still need a decision. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be included as co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- CSS-only changes are not proof of zero functional risk: interaction, responsive layout and the complete buyer journey still require scoped verification; sales counts cannot certify unchanged files. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- Budget settings are not hard spend caps; observational before/after performance and unverified overdelivery percentages cannot support guaranteed CPA or learning-preservation claims. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)


## Dream Learnings: 2026-10-19

### Activity Summary

Omri Gitter worked on Blueprint and Culture Capsules presentation, client administration and masterclass reporting, while exploring personal career and location questions through an I Ching reading. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `117f81fc-a6ad-4602-b268-893abb797157`)

- **Offer and launch presentation:** Omri settled Blueprint’s $79/$99 introductory payments, approved preview-only publication and demanded the original section order and floater. The assistant reported repairs, but acknowledged that the new offer’s full advertising package was not delivered. For Culture Capsules, Omri retained the dark hero, selected unchanged video-kit UGCs and rejected banners; replacements and a separate public review were reported published. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- **Client administration:** Omri resolved the missing allocation-number thread and approved new invoices after catching stale currency conversion. Browser records confirm issuance. They authorized only one roof-electrical clause for the Sokolov lease; the replacement was prepared but not resent. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- **Sales operations:** Omri challenged a contact-based buyer count. The corrected export contains 127 order records from 117 people, including two cancelled/duplicate flags; it is not settlement reconciliation. (original session `117f81fc-a6ad-4602-b268-893abb797157`)
- **Personal exploration:** Omri requested both general and question-specific readings about suitable work, hospitality and remaining in Israel, repeatedly asking for more depth. These questions establish exploration, not decisions or predicted outcomes. A requested support refund email was sent; no refund is established. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)

### Sessions Processed

- 3c41987c: Blueprint reconstruction, final schedules, headline and limited VIP styling. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)
- 642f6ef0: preview-only release, original folds/floater and incomplete advertising package. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- ad99e93f: extended Culture Capsules launch library, UGC selection and banner corrections. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- 6bfde4d1: allocation retrieval, corrected FX, approved issuance and unresolved actual tax-payment status. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- bd4275ad: exact roof clause and prepared, unsent lease replacement. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- 117f81fc: order-level call-center roster and left-to-right correction. (original session `117f81fc-a6ad-4602-b268-893abb797157`)
- 7915eae5: balanced public lighting revision, separate GitHub review and later layout request. (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- f3ef654d: full I Ching readings, personal questions and refund request. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- 355b674a: ambiguous call fragment; no durable medical fact admitted. (original session `355b674a-0431-4707-bed5-d9b4fa5734b8`)
- 697531c0: generic Grok question; no durable subject or preference established. (original session `697531c0-3e62-478c-b32d-e81ee460c4f1`)
- 219ddd45: existing summary reviewed; no later activity beyond the prior synthesis. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Notes distilled

- Incorporated source-supported Blueprint scope/prices → `projects/lla-blueprint-relaunch`; Culture Capsules hub/review distinctions → `projects/french-atelier-culture-capsules`. Note-only deployment IDs and globalized design rules were not promoted. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- Monthly eTeacher billing cadence was verified against the original session and incorporated into `projects/eteacher-monthly-invoicing`. The new current-rate correction is scoped to the new invoices, not retroactive rewriting of September. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`) (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`)

### Open Questions

- Is the operating-agent handoff installed, and what scheduler run history establishes punctuality after the delayed control check? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Was the tracking patch’s item-specific freeze lift approved and required guard passed? The merged PR reports QA-mode checks, not post-patch real-traffic matching/deduplication or rollback payment certification. ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- What caused Julie’s interruption, and did real card, Apple Pay and PayPal payments pass the physical-device matrix? Where is the order-level CRM ↔ settlement/refund ↔ Meta ledger, with page origins, cutoffs and test exclusions reconciling the prior 10/12/13 counts and the new roster? (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- Were paid test `8054067` refunded and unpaid QA orders `8054068`/`8054071` removed? Prior backlog: `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, `8032752`, `8050691`, `8050693`, `8050702`, `8050810`. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were copied new-set `adGroupID` tags aligned to `108814` under approval, and was the 18-versus-19 staged inventory resolved without changing originals? (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Do community paid records retain `/masterclass-72hours/`, queries and payment time? Did the clone’s runtime guard pass, were checkout setup/refund/forced-error defects resolved, and were all IIBS v4 variants imported/sent with intended triggers/counts? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Which original dark Capsules build matches the remembered source; was French Atelier staging promoted/payment-tested and the syllabus PDF rechecked? Did the later public-review margin/type request finish, and were replacement banners accepted? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`) (original session `0b5e32e6-fbb9-418f-a0ac-32c046b29743`)
- Did modified-fbclid/duplicate-server diagnostics clear, was Blueprint Set 2 attribution proven, and which order establishes the September sale and Set 01’s learning-window result? ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648)) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- Were PRNOW’s original receipt and Keren Ziv’s R6LYD3K thread resolved; French Atelier DM/publishing, Sprout restoration and scoped exports completed; and Julie presenter takes, v6 cutdowns and speaker deck accepted? (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- Was the lease replacement uploaded and sent with only the approved clause, the old envelope superseded and tenant-first signatures completed, with guaranty pages separate? (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- Where is the complete new Blueprint offer ad package, distinct from legacy galleries, and what approval covers live checkout/CRM activation? (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- Was the support refund request acknowledged or refunded? Its register labels are not legal adjudication. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- Were actual VAT/tax filings and payments verified outside the Morning allocation authorization screen, and which open invoices have receipt/settlement evidence? Dashboard labels alone do not establish liabilities or prior payment. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested clearer VIP masterclass course-benefit copy, but its eligibility and redemption terms remain undecided, separate from the Blueprint VIP offer. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

- What benefit and redemption terms should VIP masterclass buyers receive? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

#### Lease wording

You approved only the roof-electrical addition, while acceptance of the earlier extra appendix wording and a co-lessor role remains unestablished. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- Successful source-file, preview or modal checks do not establish a completed payment, installed automation, recipient receipt or accepted design; keep each evidence layer separate. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)


## Dream Learnings: 2026-10-20

### Activity Summary

Omri Gitter concentrated on French Atelier’s ecommerce launch and purchaser recovery, alongside Julie sales operations and the Sokolov lease signatures. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`) (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)

- **Launch presentation and checkout:** Omri approved the beige teacher section after portrait and readability corrections, then authorized design-only publication. A separate workstream reported fixing Capsules pricing, CAPI, mobile overflow and false confirmation. Live form checks and a sandbox purchase do not establish real-device payment settlement; a later typography-changing lighting preview was rejected and unpublished. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Purchaser recovery and targeting:** Omri demanded French Atelier-wide purchasers, rejected mixed-brand seed padding and froze Meta changes. The approved read-only export produced 6,633 submissions, but matching to ActiveCampaign did not complete the direct CRM payment match. The final 26-record attachment still includes two billing-issue statuses. Resent three-set targeting is advice, not a launched configuration. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `1ad26cec-e6d7-4c05-a960-9620bad9b66a`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)
- **Sales and signatures:** Julie’s roster was corrected to 129 orders after removing internal records; a later audience reconciliation submitted 122 unique identities from 131 orders. Omri authorized only paused set 3’s lookalike addition, not set 6. For Sokolov, the amended lease was reported sent and both tenants signed; two guarantors and Omri remained pending. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`) (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)

### Sessions Processed

- 5f70d990: approved design-only release, French Atelier-wide purchaser scope and resent proposal. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- 39e18618: Capsules pricing/CAPI fixes, launch defects, rejected seed padding and incomplete CRM recovery. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- e5d1fc33: 101→122 seed identities, paused set 3, untouched set 6 and pacing correction. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- 117f81fc: same-link 129-order roster; internal-record removal and corrected five-order increase. (original session `117f81fc-a6ad-4602-b268-893abb797157`)
- bd4275ad: actual amended PDF resend, tenant signatures and guarantor invitations. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- 1ad26cec: video readiness inventory and outcome-based targeting correction. (original session `1ad26cec-e6d7-4c05-a960-9620bad9b66a`)
- 7915eae5: extended targeting discussion; repeated deletion theory is not corroboration. (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`)

### Notes distilled

- Teacher presentation and release notes verified against screenshots/hash/readback trajectory → `projects/french-atelier-culture-capsules`. Exact review type sizes are not global site rules. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Purchaser verification and ad-set review notes → `projects/french-atelier-purchaser-recovery`; latest user creative labels remain unmapped, and direct CRM validation is still missing. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Julie audience note → `projects/lla-julie-purchaser-audience`; retained order/identity/matched-user distinctions and verified the two final accepted additions. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)

### Open Questions

- Where is the authoritative French Atelier order/payment export across all products, including partial payment, cancellation, refund and test flags? Can the 26-marker attachment’s two billing-issue rows be resolved, and the lead IDs matched directly to CRM rather than marketing fields? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Has the submitted-lead lookalike cleared Updating/too-small, and do its 16 forms cover CRM/web leads? Any upload or audience change needs specific approval; the export exception is read-only. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Did physical-device card and PayPal payments pass, are installment collections evidenced, and was the unpaid “QA Three Final” production record removed? Which Cinema & Music start date is authoritative: CRM 2027-01-10 or the requested first Sunday? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Was production CRM forwarding moved off the Longevity gateway onto French-only credentials, and is there access-log evidence for the removed publicly reachable hashed-identifier file? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Did the separate public-review margin/type revision finish, were rebuilt banners accepted, and was the syllabus PDF rechecked? Teacher publication is established by the later design-release record, not by the older preview. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- Has Julie seed processing finished with a refreshed match count, and what does hourly delivery show after set 3 resumes? Normal lookalike status does not establish unchanged pacing. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- Have both guarantors and Omri completed the amended Sokolov envelope? The latest session reports tenant signatures and both guarantor invitations, not all-five completion. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- Is the operating-agent handoff installed, and does scheduler run history establish punctuality? Was Julie’s item-specific tracking freeze lift approved and required guard passed, with real-traffic matching/deduplication? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- What caused Julie’s interruption, did the physical-device card/wallet matrix pass, and where is the CRM ↔ settlement/refund ↔ Meta order ledger with page origins, cutoffs and test exclusions? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- Was paid QA `8054067` refunded and were unpaid `8054068`/`8054071` removed? Prior cleanup backlog: `8030579`, `8030580`, `8030584`, `8030590`, `8030591`, `8030593`, `8030594`, `8030596`, `8032752`, `8050691`, `8050693`, `8050702`, `8050810`. Roster exclusion is not refund or deletion. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were copied new-set `adGroupID` tags aligned to `108814` under approval and the 18-versus-19 inventory resolved without changing originals? (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Do community paid records retain `/masterclass-72hours/`, queries and payment time; did its guard/failure paths pass; and were all IIBS v4 variants imported and sent with intended triggers/counts? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Did modified-fbclid/duplicate-server diagnostics clear, was Blueprint Set 2 attribution proven, and which order establishes the September sale and Set 01 learning-window result? ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were PRNOW receipt and Keren Ziv R6LYD3K resolved; French Atelier DM/publishing, Sprout restoration and scoped exports completed; and Julie presenter takes, v6 cutdowns and speaker deck accepted? (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- Where is the complete new Blueprint offer ad package, distinct from legacy galleries, and what approval covers live checkout/CRM activation? (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- Was the support refund request acknowledged/refunded, and were actual VAT/tax filings, payments and invoice settlements verified outside dashboard labels? (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested clearer VIP masterclass course-benefit copy, but eligibility and redemption terms remain undecided, separate from Blueprint VIP. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

- What benefit and redemption terms should VIP masterclass buyers receive? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

#### Lease wording

You approved only the roof-electrical addition, while acceptance of earlier extra appendix wording and a co-lessor role remains unestablished. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- Incomplete marketing-system reads cannot establish deleted customers or unavailable purchasers; source counts, contact matches, paid orders, submitted identities and platform-matched audience size require separate evidence. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)


## Dream Learnings: 2026-10-21

### Activity Summary

Omri Gitter pushed French Atelier’s Culture Capsules launch toward release while clarifying purchaser audiences, continuing Julie acquisition monitoring and pursuing the final Sokolov lease signature. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **Checkout and presentation:** Omri requested an emergency checkout check and corrected repeated pricing-card misunderstandings: the large number must be the per-capsule price, not the package installment. The assistant reported the final hierarchy live, alongside manual coupon behavior and registration-based refund wording. Card-field rendering and staging amounts still do not certify physical-device payments or settlement. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- **Purchasers and launch ads:** A newly supplied sales workbook reportedly enabled 232 name-matched identities after expanding beyond the paid/noncancelled subset; upload acceptance is not paid-buyer or match-count verification. Omri requested one concept per ad across placement formats and an immediate numbered chart. The assistant reported 29 renamed paused launch ads, with intended audience roles still differing from saved settings and audiovisual corrections outstanding. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Julie and signatures:** Julie reports continued with ad-level performance and observed configuration changes, not settlement reconciliation. Both Sokolov guarantors were reported signed; Omri requested his invitation again, but the fifth signature is not established. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Sessions Processed

- 219ddd45: extended monitoring through 2026-10-22 UTC; distinguish observed changes, Meta totals and settlement. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 5f70d990: extended reviewed publication, intended/saved launch chart and reported 29-ad naming/audit outcome. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- 39e18618: extended workbook/name match, approved 232-identity submission and 29 paused launch ads. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- bd4275ad: extended guarantor signatures and resend to Omri; no envelope-specific fifth-signature proof. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- 11b3a24a: new emergency checkout/design session; final per-capsule price hierarchy. (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)

### Notes distilled

- Copy/design guardrails verified against their source and reinforced by Capsules corrections → preference candidate reconciliation; exact visual style remains brand-scoped. (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- Service Performance Record remains an already-covered subject; its note adds no source-verified change. Residence/language notes need unavailable underlying source verification; device and generic design-system notes lack claim-level provenance, so no new personal facts were admitted.

### Open Questions

- Can the 940-order/645-student workbook, its 410 paid/noncancelled subset and expanded 232 submitted identities be independently reconciled to payment/refund/test/cancel flags? Where are the direct email/phone export, ambiguous-name resolutions and disposition of the earlier two billing-issue rows? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Have both FA lookalikes cleared Updating/too-small with real match counts, and do the sixteen forms cover CRM/web leads? Is the three-role targeting map approved/applied with real age controls, final exclusions, remaining budgets and spend-cap enforcement? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Did physical-device card/PayPal and recurring collections pass, was the CEO’s failed order cleared, and were “QA Three Final” and unpaid staging probes (including examples 8054332–8054335) cleaned up? Which Cinema & Music date is authoritative? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- Was production forwarding moved to French-only credentials, and is there access-log evidence for the removed hashed-identifier file? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Did public-review margin/type work and syllabus checks finish? Were Fashion UGC’s Tuesday hook, presenter language-learning framing and unqualified price copy corrected and continuously reviewed? Are Caitlin’s studio source, Stan’s identity and the latest static-banner scope resolved? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `7915eae5-e0c8-4e9f-8bae-8d57695ba748`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- Did Julie seed processing finish with refreshed matches? What do hourly results show for resumed Set 03, and what authorizes its later bidding/budget changes? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- Is Sokolov envelope 3D9C2B43-CD9A-89E5-8181-14A7CF89334D complete with Omri’s signature? The session establishes only four signatures and his resent invitation. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- Is the operating-agent handoff installed with punctual scheduler run history, and was Julie’s item-specific tracking freeze lift approved/guarded with real-traffic matching/deduplication? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- What caused Julie’s interruption, did the physical-device card/wallet matrix pass, and where is the CRM ↔ settlement/refund ↔ Meta ledger with page origins, cutoffs and test exclusions? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Was paid QA 8054067 refunded and were unpaid 8054068/8054071 removed? Older cleanup backlog: 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752, 8050691, 8050693, 8050702, 8050810. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were copied new-set adGroupID tags aligned to 108814 under approval and the 18-versus-19 inventory resolved without changing originals? (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- Do community paid records retain /masterclass-72hours/, queries and payment time; did guard/failure paths pass; and were all IIBS v4 variants imported/sent with intended triggers/counts? (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Did modified-fbclid/duplicate-server diagnostics clear, was Blueprint Set 2 attribution proven, and which order establishes the September sale and Set 01 learning-window result? ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were PRNOW receipt/Keren Ziv R6LYD3K, French DM/publishing/Sprout/export work and presenter/v6/deck acceptance resolved? (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`)
- Where is the complete new Blueprint offer ad package and approval for checkout/CRM activation? (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- Was the support refund request acknowledged/refunded, and were filings, payments and invoice settlements verified beyond dashboard labels? (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested clearer VIP masterclass course-benefit copy, but eligibility and redemption terms remain undecided, separate from Blueprint VIP. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

- What benefit and redemption terms should VIP masterclass buyers receive? (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

#### Lease wording

You approved only the roof-electrical addition, while acceptance of extra appendix wording and a co-lessor role remains unestablished. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- A supplied order workbook can unlock local name matching without proving every matched identity paid; preserve order rows, status-filtered people, submitted identities and platform matches as separate units. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Source spot-check removed an unsupported example from `concepts/github-pages-delivery`; the public media-page requirement is directly supported by the original request. (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`)


## Dream Learnings: 2026-10-22

### Activity Summary

Omri Gitter drove Culture Capsules into paid launch while preparing Julie's event, reviewing board audience evidence and comparing Blueprint VIP offers. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)

- **Launch and attribution:** Omri approved selected ads, a campaign-link gate and checkout repairs. The assistant reported 17 active ads and Meta-accepted checkout events across all packages; sandbox bundle enrollment advanced, but a current-code Purchase credited to an ad set was not demonstrated. Omri rejected preview-based proof and Israel-targeted testing. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Event communications:** Omri corrected the no-show sequence to include 30-day recording access and requested a rehearsal brief with Harel opening and Courtney moderating. Chris owns dynamic links and scheduling. Executive social drafts were separated by voice, then ended in an unresolved professional audit rather than accepted copy. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- **Board and offer review:** Two audience slides were reportedly inserted into the existing board deck and emailed to Keren; Omri removed an unsupported masterclass-to-Blueprint funnel headline without resending. Three Blueprint VIP price variants became phone-comparison previews, with repeated readability and luxury-design objections and no final offer choice. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/a5e4ff4f9c1674eea09981bee6cedde154b96bb6))

### Sessions Processed

- 5f70d990: extended through 22:53 UTC: launch, gate, tracking, bundle repair and rejected attribution-test shortcuts. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- 658b2028: no-show correction, eight-slide board handoff, urgent-mode request and three pricing previews. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- b3b81423: rehearsal ownership, Harel opening, Courtney moderation and unresolved offer/script details. (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`)
- f55de7df: role-specific social copy and professional risk audit; no final repaired package. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- a7807e3c: combined ad board, culture-class framing and two five-card carousels. (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`)
- 219ddd45: assistant-only 10:08 UTC report extends indexed bounds; observed changes are not execution authority. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- ea4bcf59: question-mark-only exchange; no substantive extraction. (original session `ea4bcf59-f154-4fb5-8ba6-b3fd95996912`)

### Notes distilled

- Incorporated source-supported bundle mechanism and source-level cross-student guard → `projects/french-atelier-capsules-checkout`; campaign gating and neutral review access → `projects/french-atelier-culture-capsules`. The gate note's original denial text is superseded by the source session's neutral welcome. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/83b3ddf1651829dbeee4597ee752fef480b1010a)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/7ac29ef221d04bf2202e68790f323716c10d0256))
- Attribution-handoff and identity notes are corroborated at source-change scope, not paid/ad-credit certification. The note claiming all three launch sets had Advantage+ OFF conflicts with the detailed transcript; no definitive final launch-age/expansion claim was admitted. Unseen deployment/run hashes and cover dimensions were not promoted. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/5ec96a2dbb6098aa97305d90ef1736ad22215b11))
- External-specialist and proof-before-status notes reinforce staged preference candidates; supported originals, not the notes themselves, supply provenance. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Open Questions

- Can the FA workbook's 940 rows/645 students, 410 paid/noncancelled students and 232 submitted identities be reconciled to processor/refund/test/cancel flags, direct contacts and the earlier two billing-issue rows? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- What are the final saved FA Advantage+/hard-age settings, exclusions, match counts, lead-source form coverage and spend-cap controls after launch? The transcript's Main settings conflict with the derived note; checkout/cart lookalike readiness is unproved. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Where is a current-code paid Purchase credited to a specific FA ad set, with browser/server dedup evidence and CRM/processor reconciliation? Did TEST expire, was the Israel test confirmed paused, and was the original three-capsule buyer's missing enrollment repaired? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Did physical-device card/PayPal and recurring collections pass, were failed/QA orders cleared, and which Cinema & Music date is authoritative? New unpaid QA includes 8059679, 8059694, 8059712, 8059999 and 8060186–8060209; staging bundle tests include 8054360–8054371. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- Is `FA_checkout_events` configured with the three named cart-stage values and working recovery automations? Was production forwarding restricted to French credentials, and is there access-log evidence for the removed hashed file? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Were the new UGC/presenter/banner variants continuously reviewed, eight caption-led covers applied, and shared-board selection merging fixed? Are Caitlin's studio source, Stan's identity and remaining scope resolved? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Did Julie seed processing finish with refreshed matches, and what authorizes the latest budget/bid changes? Was the inconsistent hourly raise analysis repaired before use? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- Was Julie's rehearsal completed, teaching deck approved/published, and Chris's four-email sequence imported with correct links, November reminders and 30-day recording access? Is the public “no replay” promise aligned with the stated benefit? (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`)
- Was the social package repaired and made shareable, with historical rank/biography, syllabus, scarcity and first-person claims validated? Were the board's fluctuating Meta totals reconciled and Blueprint CRM buyers profiled separately? (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- Is Sokolov envelope 3D9C2B43-CD9A-89E5-8181-14A7CF89334D complete with Omri's signature? The probe's older resend email does not supersede the later four-signature session report. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- Is the operating-agent handoff installed with punctual scheduler history; was Julie's tracking freeze lift approved and guarded; what caused the interruption; and where is the CRM ↔ settlement/refund ↔ Meta ledger? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- Was QA 8054067 refunded and were 8054068/8054071 removed? Older cleanup: 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752, 8050691, 8050693, 8050702, 8050810. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were new-set adGroupID tags aligned to 108814 under approval and 18-versus-19 inventory resolved; did community origin/query/payment retention and IIBS v4 send/trigger checks pass? (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Did modified-fbclid/duplicate-server diagnostics clear, was Blueprint Set 2 attribution proven, and which order establishes the September sale and Set 01 learning-window result? ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Were PRNOW receipt/Keren Ziv R6LYD3K, French DM/publishing/Sprout/export work, presenter/v6 acceptance, support refund, filings and invoice settlements verified? Is the complete Blueprint offer ad package approved for checkout/CRM activation? (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested clearer VIP masterclass course-benefit wording and a rehearsal close, but the exact redemption promise and deadline are still unsettled. (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

- What benefit, eligibility and redemption deadline should the close and buyer communications promise? (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)

#### Blueprint VIP choice

You compared three Blueprint VIP price options beside Standard, but have not selected the production offer or accepted the final design. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

- Which VIP variant and presentation should be approved for production? (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

#### Bundle record shape

You requested one student and one order for a bundle, while the deployed fix uses one charged order plus extra zero-owed course orders. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/83b3ddf1651829dbeee4597ee752fef480b1010a))

- Is that CRM record shape acceptable, or must enrollment be consolidated under one order? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

#### Lease wording

You approved the roof-electrical addition, while acceptance of extra appendix wording and a co-lessor role remains unestablished. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)


## Dream Learnings: 2026-10-24

### Activity Summary

Omri Gitter pressed for measurable ecommerce progress, clearer Julie teaching materials, literal testing scope and follow-through on service complaints, alongside an immediate camera search. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `c4e0d11f-6f69-4675-af30-bf08364014c2`)

- **Ecommerce and guardrails:** Omri challenged causal learning/budget claims and saved overnight cuts as decrements, not target budgets. The later French report lists one $79 ad-set Purchase, without order/settlement proof; mobile diagnosis reproduced a discounted-payment fallback. Omri requested clearer mobile design while locking attribution/CAPI. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Teaching and offer review:** He selected originals into a 21-slide Julie review, with alternatives outside Play mode, and refined Courtney's moderator runbook. Presenter acceptance, rehearsal and comment delivery remain open. Blueprint's white Standard/navy VIP comparison remains unselected; November acquisition goals are not activation approval. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Testing scope and complaints:** Omri rejected an unauthorized production registration during a screenshot request, then authorized refund demands and follow-ups. Support offered a task refund and acceptance was sent; the ownership-confirmation send encountered an approval block. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Personal shopping:** For an intended Luna Park Tel Aviv visit, Omri wanted a tiny head-mounted video camera from a currently open Wolt shop delivering to Tel Aviv. No complete match was verified, and he ended the exchange without an established purchase. (original session `c4e0d11f-6f69-4675-af30-bf08364014c2`)

### Sessions Processed

- 5f70d990: extended through indexed 2026-10-24 22:51 UTC plus later untimestamped trajectory turns; learning/scaling corrections, saved overnight rules, website screenshots and discounted-payment diagnosis. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- 219ddd45: continuation through 2026-10-24 16:57 UTC plus later trajectory; authorized budget deltas, unauthorized CRM test, support follow-ups and blocked ownership send. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 5fc1c29a: meaning hierarchy, rejected rebuilds and 21-slide Julie review; comments use local email composition, not confirmed delivery. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- 12e9ff81: all-version visual picker, multi-select/all-86 repair and exact 40-slide working collection. (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)
- 658b2028: continuation through 2026-10-23 07:06 UTC; contrasting pricing-card correction, no acceptance. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- c4e0d11f: immediate Wolt camera search for planned outing; no verified purchase. (original session `c4e0d11f-6f69-4675-af30-bf08364014c2`)
- 697531c0: trivial Grok clarification, no substantive durable extraction or separate summary. (original session `697531c0-3e62-478c-b32d-e81ee460c4f1`)
- Six substantive sessions have persisted summaries; this continuation replaces two summaries, retaining the prior run's remaining session audit. Unchanged summaries were not rewritten.

### Notes distilled

- Slide-selection and teaching notes were checked against their original sessions → `projects/lla-julie-masterclass-deck`. The 40-slide collection is not the final curated deck; later explicit permission authorizes choosing main slides without redesign. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)
- Campaign-gate and bundle notes are already covered by `projects/french-atelier-culture-capsules` and `projects/french-atelier-capsules-checkout`. The gate's old denial text and note-level deployment date were not promoted; canonical commits support neutral access and bundle mechanics. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/7ac29ef221d04bf2202e68790f323716c10d0256)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/83b3ddf1651829dbeee4597ee752fef480b1010a))
- Attribution-ownership note reinforces the session-grounded verification preference. Older Julie pricing-card colors were not generalized to the distinct Blueprint comparison. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- Meta-guidance and scope notes remain covered by the preference ledger; no note-only budget heuristic was promoted. The acquisition note's older price schedule does not resolve the later Blueprint installment wording. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)

### Open Questions

- Which CRM order and settled processor transaction back the reported $79 Purchase on French Set 1 #108761/Ad #13, and is browser/server deduplication verified? Is Taglert connected with an independent report; have Testbirds or Ubertesters completed testing? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- What fixes the reproduced CAPSULE20 advisor fallback for Fashion & Art/Gastronomy, and has the mobile-only redesign shipped without changing protected attribution? Were diagnostic orders 8061102/8061103 and the unauthorized Omri QA-Test lead handled under explicit approval? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Does automation 658668c7-5f7a-453d-9a44-7cb520aebdfa enforce the corrected once-per-set decrements and raises through 2026-10-25 07:00 Asia/Jerusalem? Verify actual cadence/final wake across the timezone change; the reported 06:40 last check is not established by the saved 20-minute schedule. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Where is a sourceable returned-credit receipt for the accepted support task refund, and what decisions remain on the four earlier cases? Was the ownership-confirmation email approved, sent from a verified identity and accepted by support? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- Can the FA workbook's 940 rows/645 students, 410 paid/noncancelled students and 232 submitted identities be reconciled to processor/refund/test/cancel flags, direct contacts and the earlier two billing-issue rows? (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- What are the final FA Advantage+/hard-age controls, exclusions, match counts, lead-form coverage and enforced spend controls? How does the 17-ad launch report relate to the later 15-link audit? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Was the original three-capsule buyer's missing enrollment repaired? Did TEST remain expired and the Israel test remain paused? Did real-device card/PayPal and recurring collections pass, were QA orders cleared, and which Cinema & Music date is authoritative? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- Is `FA_checkout_events` configured with the three named cart-stage values and working recovery automations? Was production forwarding restricted to French credentials, and is there access-log evidence for the removed hashed file? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Were eight caption-led covers applied, shared-board selection merging fixed and presenter/UGC variants accepted? Are Caitlin's studio source and Stan's identity/scope resolved? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`)
- Did Julie seed processing finish with refreshed matches; what authorizes other observed budget/bid changes beyond the verified Set 04 +$110 and Set 01 +$69; and was the inconsistent hourly raise analysis repaired? Where is the separate operating-agent installation and punctual scheduler history? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- Did Julie accept the 21-slide review, were sauna/end-card and nutrition/movement revisions completed, and was a rehearsal held? Were wording/step-count discrepancies resolved, and did an actual comment email reach Omri? Local storage and `mailto` are not real-time shared review. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- Was Chris's four-email sequence imported with correct dynamic links, November reminders and 30-day recording access? Is the remaining public “no replay” promise aligned, and is the social package repaired, validated and shareable? (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- Were board Meta totals reconciled and Blueprint sales-team CRM buyers profiled separately? (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- Can a final certificate establish completion and Omri's signature for Sokolov envelope 3D9C2B43-CD9A-89E5-8181-14A7CF89334D? (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- Was Julie's tracking freeze lift authorized and guarded; what caused the interruption; and where is the CRM ↔ settlement/refund ↔ Meta ledger? Did modified-fbclid/duplicate-server diagnostics clear and Blueprint Set 2 attribution pass? (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Was QA 8054067 refunded and were 8054068/8054071 removed? Older cleanup: 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752, 8050691, 8050693, 8050702, 8050810. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Were new-set tags aligned to 108814 under approval, 18-versus-19 inventory resolved, and community query/payment retention plus IIBS v4 trigger checks completed? (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Which order establishes the September sale/Set 01 learning-window result; were PRNOW receipt/Keren Ziv R6LYD3K, French publishing/Sprout/export work, presenter/v6 acceptance, support refund, filings and invoice settlements verified; and is the full Blueprint ad package approved for checkout/CRM activation? ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648)) (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested a clear moderator close and VIP course benefit, but its value, eligibility and redemption deadline are still undecided. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`)

- What amount and deadline should be promised? The dictated $270 differs from $79 + $199 = $278. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

#### Blueprint VIP choice

You compared three VIP price options and contrasting card designs, but have not selected the production offer or accepted the final presentation. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

- Which VIP variant and presentation should be approved for production? (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- Does the later approximately $199 recurring-payment description change Standard's reviewed four $169 installments, or describe another offer? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)

#### Bundle record shape

You requested one student and one order, while the implementation attaches additional zero-owed course orders after one package payment. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/83b3ddf1651829dbeee4597ee752fef480b1010a))

- Is that CRM record shape acceptable, or must enrollment be consolidated under one order? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

#### Lease wording

You approved the roof-electrical addition, while acceptance of extra appendix wording and a co-lessor role remains unestablished. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra appendix sentences remain, and should Sandra Gitter be a co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- Connector records without a canonical URL remain retrieval leads rather than citable wiki evidence; obtain a durable source before promoting them.


## Dream Learnings: 2026-10-26

### Activity Summary

Omri Gitter focused on Julie's live-event readiness and French Atelier reliability, while pursuing support accountability and an advertising case-study reference. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `228c5c1b-38ff-478c-9e6a-c3496535b65a`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)

- **Fulfillment and reporting:** Omri kept sales open while requiring Capsules identity/enrollment repair. Missing-course assignments now have readbacks, not full access proof. Corrected weekly reporting formulas were also read back. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **Live production:** He refined automatic recording, V45 order, attendee chat and Julie-only Instagram assets. A shared Q&A desk was reported delivered, while the closer remains unaccepted and its last natural-light revision unfinished. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `59567e86-3c35-48de-83af-fed43792d9db`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`) (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Sales routing and evidence:** He set French budgets and requested Julie changes; only the latter Set 03 pause succeeded. The attendee page became learning-first, but eligible cohorts and callback receipt remain unverified. The VIP roster was a historical backup, not a current refresh. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- **Accountability and references:** He pursued the hidden-code incident and refunds; partial credit posting does not resolve all demands. His Intermarché Cannes reference search required an open video, not an article or subscription. (original session `228c5c1b-38ff-478c-9e6a-c3496535b65a`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)

### Sessions Processed

- 50d09f1f: extended through authorized assignment repair; production/staging readbacks, residual duplicates and incomplete payment/access certification. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- cf7b1560: extended through 09:05 UTC; saved row-90 price/revenue formula readbacks and source-faithful denominators. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- 97ea884b: extended through 2026-10-27 04:44 UTC; automatic recording, attendee chat and Instagram-only Julie handoff. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- 219ddd45: extended through 2026-10-27 05:14 UTC; audience labels, $149/$79/$169 French budgets and later no-data reports. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 5fc1c29a: extended teaching-deck review, logos, closer options and platform-specific social request. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- 439a0622: public social recovery, film edits, approved GUESTLIST and user-reported iPhone 14/17 success. (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)
- 292ed309: extended learning-exit investigation; deterministic promises and rigid replacement threshold both unsupported. (original session `292ed309-b521-461b-a3f4-e8b6438eec24`)
- 5b70164c: substantive one-turn AI sales RFP; proposals and estimates, not approved activity. (original session `5b70164c-5a23-4fe9-bf6b-bc963c9c2035`)
- 0425b0f4: read-only runbook audit and separately authorized attendee offer page. (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`)
- 607a8771: social copy refinement and blocked publication in that session; separate later recovery remains distinct. (original session `607a8771-2773-4d2d-8e4e-07acb0f39353`)
- 5f70d990: campaign continuation, guest-change audit, French enrollment gap and withdrawn buyer→set inference. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- 20d790c3: October 27 Israel sales snapshot; Set 03 paused, two budget writes not applied, Set 05 increment ambiguous. (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)
- 59567e86: closer archive and repeated rejected revisions; trajectory-only final natural-light/smaller-type request remains in progress. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- c3a19142: learning-first attendee LP; source curriculum restored, cohort and sales receipt still open. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- 8904dadb: confidential VIP transition text; requested live roster remains incomplete, 27-row October 20 backup delivered. (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- e431dbfa: internal-test Purchase correlation and user-reported IIBS messages; exact event/CRM causality unverified. (original session `e431dbfa-a68c-4adc-b8af-701f0309f281`)
- addc845a: desktop Zoom pinning guidance, without verified successful pin or local role/version. (original session `addc845a-4912-41d8-8990-1dbd73fe583a`)
- 858958e0: V45-only correction, V2 alternative versus Play correction and limits of remote already-open-tab updates. (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- 75ba57bc: shared Q&A desk and draft generation reported delivered after seven-minute deadline. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- db0d86f4: dark attendee-page restoration and hidden branded URL; both codes display $149×5, not proven enrollment. (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`)
- bcbf11d5: V45 duplicate initially incomplete because review comments were browser-local. (original session `bcbf11d5-4971-4350-899a-5a76cee495b4`)
- 228c5c1b: open Cannes video-reference research; article/paywall alternatives rejected. (original session `228c5c1b-38ff-478c-9e6a-c3496535b65a`)
- 2d117a2b: guest-code forensic audit, CLAIM-0461, support-confirmed credit posting and saved follow-up schedule. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)

### Notes distilled

- Weekly reporting exclusions, denominators and formulas → `projects/french-atelier-weekly-reporting`. Fresh trajectory reads support saved formulas and precision; unneeded workbook/tab naming remains unpromoted. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- Bundle and rehearsal notes reinforce `projects/french-atelier-capsules-checkout` and `projects/lla-julie-live-operations`. New trajectory reads support the assignment relay mechanism beyond the earlier write guard; unsupported course-not-found details and assertions that scripts cannot be separate appendices remain unpromoted. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/3e7767bed72aa6bcfdc8146cf866e683e011fdc6))
- Changed design, inventory, reporting and execution notes were reviewed against source sessions. Protected design boundaries and cross-platform scope remain covered; a CRM contact-field number is not treated as verified configuration from note attribution alone. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `607a8771-2773-4d2d-8e4e-07acb0f39353`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Recording, V45/closer, Q&A and lead-page notes were checked against conversations/trajectories → production, deck, closing-slide, Q&A and attendee-offer pages. Historical roster scope and support-credit distinctions were also source-checked; no new location or agent-only implementation rule was promoted. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `59567e86-3c35-48de-83af-fed43792d9db`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`) (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)

### Open Questions

- Which CRM orders/settled transactions back French $79 #108761/Ad #13 and $151 #108757 purchases, and do actual Purchase pairs deduplicate? Obtain a connected independent report and completed Testbirds/Ubertesters paid-feed/device evidence. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Verify learner access for the original buyer and student 11682495, native bundle/financial coverage and full real-card→assignment→event pairing after the authorized repair; orders 8061645/8061646 have assignment evidence, not login proof. Resolve residual duplicate students 11682493/11682494 and CAPSULE20 fallback. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Verify actual execution/final wakes of overnight automation 658668c7-5f7a-453d-9a44-7cb520aebdfa and purchaser-lookalike +10% job across the timezone boundary; determine whether the separate operating agent exists. Latest French authorized readbacks are Buyers $149/Francophile $79/Leads $169. Complete or reconcile unapplied Julie Set 04 $1,149 and Set 02 $514 targets. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `292ed309-b521-461b-a3f4-e8b6438eec24`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)
- Obtain complete support ledger/ownership acceptance and itemized decisions beyond confirmed 71,349 and 3,039 task-credit returns; resolve 0.75 discrepancy, guest/repair refunds, July reimbursement and compensation. Verify actual seven-run follow-through, not merely saved automation 959fee2a-9baa-41c0-9800-180a476b4ff5. Verify authorized cleanup of diagnostic orders 8061102/8061103, Omri QA-Test, QA Tracking Check 8061284 and QA Test Gita/QA WebKit Gita. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- Reconcile 940 workbook rows/645 students, 410 eligible students and 232 submitted identities to processor/refund/test/cancel flags, direct contacts and two billing-issue rows. Verify audience matches, final Advantage+/hard-age/exclusions/form coverage, enforced spend controls and 17-versus-15 inventory. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Verify TEST expiry, paused Israel test, actual card/PayPal recurring collection and the authoritative Cinema & Music date; verify `FA_checkout_events`' three values/recovery, French-only production forwarding and removed hashed-file access logs. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`)
- Confirm applied caption covers, shared-board merging, presenter/UGC acceptance, Caitlin source and Stan scope; refresh Julie seed matches and resolve 18-versus-19 inventory/new-copy URL tags, community paid-query retention and IIBS v4 triggers. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`) (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- Resolve final runbook clock/timings and acceptance, reconcile V45 with the separate Julie review/closer and confirm presenter playback rather than local-tab updates. Verify Q&A desk acceptance/use and actual comment-email delivery. The last closer request for natural light and smaller spaced type has no completed publication evidence. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `59567e86-3c35-48de-83af-fed43792d9db`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`) (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- Verify Julie-only Instagram handoff assets and final acceptance/posting, not just the reported isolated page. Verify Chris's import/dynamic links/reminders, recording/replay parity and current October 27 VIP-only Meshi roster; the 27-row October 20 backup is not a live refresh. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`) (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- Validate attendee cohort IDs/start dates, completed purchase and callback receipt; reconcile newer GitHub learning-first content with the older branded URL. Confirm exact benefit/expiry across page/scripts. Weekly populated formulas now have source readbacks; verify daily exclusions, disposition of existing weighted CPA/profit “x” cells and Gal handoff. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`) (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`)
- Trace Omri's reported IIBS WhatsApp welcome/group notices against CRM assignment and template audit logs while preserving legitimate Blueprint reminders; neither exact 30-minute trigger claims nor all-attendee impact was established. Reconcile the internal French test to the actual event/order ledger rather than timing alone. (original session `e431dbfa-a68c-4adc-b8af-701f0309f281`)
- Establish Blueprint-specific golden paid-ad Purchase proof and CRM paid orders for campaign #116622; reconcile contradictory CAPI-zero claims with reported Julie/French receipts rather than generalizing across funnels. Confirm freeze-lift authorization, interruption cause, modified-fbclid/duplicate-server diagnostics and CRM↔settlement/refund↔Meta ledger. (original session `292ed309-b521-461b-a3f4-e8b6438eec24`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648))
- Verify refund of QA 8054067 and disposition of 8054068/8054071 and older 8030579, 8030580, 8030584, 8030590, 8030591, 8030593, 8030594, 8030596, 8032752, 8050691, 8050693, 8050702, 8050810. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `59596b49-4843-4756-b08f-17722a531c89`)
- Reconcile board Meta totals and separately profile Blueprint sales-team buyers; obtain Sokolov final certificate/Omri signature for envelope 3D9C2B43-CD9A-89E5-8181-14A7CF89334D, September Set 01 order/learning evidence, PRNOW/Keren Ziv R6LYD3K receipt, French publishing/Sprout/export results, filings/invoice settlements and full Blueprint ad-package approval. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/995c0f30f4bd7b34a8a181b63bac523801c28648)) (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `595352b8-3a75-4932-956f-68633a201347`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

#### VIP course benefit

You requested the $249 attendee benefit and both coupon aliases, but final eligibility and redemption deadline still need one consistent decision. (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`)

- What are the authoritative eligibility and expiry terms for JULIE249 and MASTERCLASS-VIP, given the midnight-versus-December wording? The displayed $249 value combines $150 tuition reduction with a $99 included masterclass. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`)

#### Julie budget increment

You requested Julie ad-set changes, but the dictated Set 05 increase still needs a clear amount. (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

- Was the Set 05 increase $9, $99 or another amount? (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

#### Blueprint VIP choice

You compared Blueprint offer alternatives and want to reuse the successful Julie setup, but the production offer and transition remain unselected. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

- Which VIP design/schedule is final, and does approximately $199 recurring replace reviewed Standard four $169 installments or describe another offer? (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)

#### Lease wording

You approved the roof-electrical addition, but acceptance of the additional appendix wording and co-lessor role remains undecided. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra sentences remain, and should Sandra Gitter be co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### General Procedural Notes

- Mail records without canonical URLs remain retrieval leads, not URL-citable wiki outcomes; the probe's support-credit and ownership-message findings are logged for retrieval.


## Dream Learnings: 2026-10-27

### Activity Summary

Omri Gitter concentrated on the masterclass-to-Blueprint conversion handoff, reconciling the commercial offer, mobile experience and official event invitation. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

- **Offer and dates:** Omri approved $79 for month 1 and four $169 payments, then required pages.dev to match the attendee link because follow-up emails pointed there. November 23/25 class options were mapped to Eastern/Pacific times; the final mobile audit still found hidden Pacific labels on the branded page while its fix was publishing. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`)
- **Customer-facing clarity:** He repeatedly reviewed pricing typography, compact cards, mobile benefit sliders, signup popups and an attendee-only question form below the offer. The full course film was repaired and accepted after end-card evidence. Controlled checks did not establish real paid enrollment or callback receipt. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Event communication:** He refined a separate official Facebook/Instagram invitation and requested exact CRM Member IDs to investigate missing WhatsApp reminders. The invitation hub was delivered; actual posting, reminder delivery and the requested identifier mapping remain unverified. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `93ae6be7-ca41-4c79-bdaa-7638c404be09`)
- **French Atelier recovery:** Omri requested the already-created purchaser file rather than another Meta audit; the 232-row seed was recovered and shared. He also stopped the Capsules hourly reader after repeated no-data reports, without stopping Julie's separate schedules. (original session `0c2dee01-dd4c-464e-b989-21af2bcb74d2`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### Sessions Processed

- c3a19142: extended through 22:41 UTC; approved offer, branded-page design, mobile benefits and mocked callback checks. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- 25a94f9a: new; mirrored offer/dates/film, plus trajectory-only final mobile audit and unanswered QA-order approval. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- 658b2028: extended through 10:03 UTC; official brand social hub and recovered chat/Q&A links. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- 7f86bc26: new; final Chris handoff destinations versus unverified live ActiveCampaign installation. (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`)
- 93ae6be7: new; StudentId is not certified Member ID, and October 26 signup population remains incomplete. (original session `93ae6be7-ca41-4c79-bdaa-7638c404be09`)
- 0c2dee01: new; purchaser source CSV recovered and shared, not a 2% modeled-audience export. (original session `0c2dee01-dd4c-464e-b989-21af2bcb74d2`)
- 219ddd45: extended through 17:41 UTC; Capsules hourly automation paused, Julie schedules separate. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- 20d790c3: extended final fallback; Meta login restriction left two requested budget changes unapplied. (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

### Notes distilled

- Approved installment schedule, exact-reference design, benefit cards, callback placement, typography and film notes were source-checked → `projects/lla-masterclass-attendee-offer`, `projects/lla-course-checkout` and `projects/lla-julie-masterclass-video`. Displayed tuition, controlled tests and paid enrollment remain distinct. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- Semester/class-date and identity notes → checkout and masterclass pages. Uncited exact mobile CSS sizing, note-only staging-order details and an attribution of assistant-run sandbox tests to Omri were not promoted. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) (original session `93ae6be7-ca41-4c79-bdaa-7638c404be09`)
- Julie's separate Instagram-only scope remains covered by `projects/lla-julie-executive-social`. The official brand invitation is a separate subject; no posting or personal biography was inferred from marketing copy. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)

### Open Questions

- Verify deployed Pacific labels on the branded attendee page after commit a2616302e9896d923e48bddf488f8646c08959d9, the sticky-price comparison, current approved schedule at the real provider screen, physical iPhone behavior, completed payment/enrollment and production callback receipt. The final nine callback tests were mocked; source changes and pre-payment checks do not close these gaps. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/6c27b2fff1d9bcaeeb8fb8687470ecc87b9b2de0))
- Verify Chris's installed JM-U1–U4 and abandoned-cart destinations, dynamic Zoom/LMS links, reminders and replay parity. Resolve CRM Member ID versus StudentId using the tester's field definition and audit logs; retrieve all October 26 Israel-time Julie signups and the current October 27 VIP-only Meshi roster. Keren Ziv's order 8032863/StudentId 11653945 has no confirmed event date. (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`) (original session `93ae6be7-ca41-4c79-bdaa-7638c404be09`) (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- Reconcile French $79 #108761/Ad #13 and $151 #108757 attributed purchases to CRM/processor orders and deduplicated event pairs; obtain actual Testbirds/Ubertesters paid-feed/device proof. Verify original-buyer and student 11682495 access, native bundle/financial coverage, orders 8061645/8061646, duplicate students 11682493/11682494 and CAPSULE20 fallback. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- Reconcile 940 workbook orders/645 students, 410 eligible students and 232 submitted identities to cancellation/refund/test flags, direct contacts and two billing-issue rows. Verify audience match counts, current expansion/age/exclusions, enforced spend controls, 17-versus-15 inventory and any promised purchaser-refresh scheduler/runs; the recovered seed does not establish a 2% audience or running sync. (original session `0c2dee01-dd4c-464e-b989-21af2bcb74d2`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- Verify actual overnight automation 658668c7-5f7a-453d-9a44-7cb520aebdfa and purchaser-lookalike +10% job executions, separate operating-agent existence, and unapplied Julie Set 04 $1,149/Set 02 $514 targets. Capsules hourly reader 9e4332aa-87fb-4950-a05e-c8c3b2da922b is paused; old no-data reports are not fresh zero-sale evidence. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`) (original session `292ed309-b521-461b-a3f4-e8b6438eec24`)
- Obtain complete support usage/refund ledger and ownership acceptance beyond the confirmed 71,349/3,039 credit returns; resolve 0.75 discrepancy, guest/repair/July reimbursement and compensation. Verify seven-run follow-through for 959fee2a-9baa-41c0-9800-180a476b4ff5 and authorized cleanup of 8061102/8061103, Omri QA-Test, QA Tracking Check 8061284, QA Test Gita/QA WebKit Gita. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- Verify TEST expiry, paused Israel test, actual card/PayPal recurring collection, Cinema & Music date, FA_checkout_events values/recovery, French-only forwarding and hashed-file access-log removal. Confirm applied caption covers, review-board merging, presenter/UGC acceptance, Caitlin source/Stan scope, Julie seed matches and 18-versus-19/new-copy tags, community paid-query retention and IIBS v4 triggers. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`) (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`)
- Confirm runbook clock/timings, closer natural-light/smaller-type acceptance, V45/Julie-review/V46 playback and what the presenter actually sees. Verify Q&A desk use, comment-email receipt, Julie-only Instagram acceptance/posting and official brand posting/bio changes. V46 source edits do not establish acceptance. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `59567e86-3c35-48de-83af-fed43792d9db`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-syllabus/commit/a6f832b4e0c45ce38d37059f40f1de162b3c48da))
- Verify weekly daily exclusions, disposition of weighted CPA/profit “x” cells and Gal handoff. Trace reported IIBS welcome/group messages against CRM/template audit logs while preserving legitimate Blueprint reminders; reconcile internal French test to the event/order ledger rather than timing. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`) (original session `e431dbfa-a68c-4adc-b8af-701f0309f281`)
- Establish Blueprint-specific golden paid-ad Purchase proof and paid orders for #116622; reconcile freeze-lift authorization, interruption cause, modified-fbclid/duplicate-server diagnostics and CRM↔settlement/refund↔Meta ledger. Julie/French evidence cannot certify Blueprint. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `292ed309-b521-461b-a3f4-e8b6438eec24`)
- Verify refund of 8054067 and disposition of 8054068/8054071, 8030579/8030580/8030584/8030590/8030591/8030593/8030594/8030596/8032752/8050691/8050693/8050702/8050810. Reconcile board Meta totals/Blueprint sales-team buyers, Sokolov certificate/Omri signature for 3D9C2B43-CD9A-89E5-8181-14A7CF89334D, September Set 01 evidence, PRNOW/Keren Ziv R6LYD3K receipt, French publishing/Sprout/export results, filings/invoice settlements and full Blueprint ad-package approval. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

#### Offer expiry terms

You approved the new installment schedule, but the attendee eligibility and redemption cutoff still need one consistent decision across the distributed links. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

- What eligibility and final deadline apply to JULIE249 and MASTERCLASS-VIP? The cloned source still contains December-versus-midnight/October cutoffs; it is not the branded production repository. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-attendees/blob/main/blueprint/assets/lla-promo.js))

#### Checkout verification approval

You requested a final mobile checkout audit, and the last recorded approval request would create one marked production QA order without a charge. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

- Was that QA-order approval granted after the available trajectory ended? (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

#### Julie budget increment

You requested Julie ad-set changes, but the Set 05 increment is still unspecified. (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

- Was the increase $9, $99 or another amount? (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)

#### Blueprint VIP choice

You compared three Blueprint VIP variants, but the final VIP offer and ad-set transition remain unselected. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

- Which VIP schedule/design is final, and does the approximately $199 recurring discussion describe that offer? Standard attendee $79 + four $169 payments is now approved separately. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

#### Lease wording

You approved the roof-electrical addition, but the extra appendix sentences and co-lessor role remain undecided. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- Should the extra sentences remain, and should Sandra Gitter be co-lessor/signatory? (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)


# Full project knowledge register

The following preserves every available project page, including older dependency projects and non-email subjects. Fresh current-state findings at the front override historical statements. Session IDs are retrieval identifiers, not claims that each original session was newly re-audited.



---

Record: `lla-masterclass-emails` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Masterclass Lifecycle Emails

LLA Masterclass Lifecycle Emails is Longevity Life Academy's retention and conversion gallery, adapted from the French Atelier lifecycle structure. Omri's Julie no-show revision has a four-message branch split by missed session, with a 30-day recording hook after the final date; gallery publication is not ActiveCampaign installation or delivery. ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/9ac7d2683dc94148623014b5f331fc67b559806c)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/cded64d1b61353ddba44ef97e12ea9436b8517a0)) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### How it works

The system covers three abandoned-cart paths, consolidated onboarding, post-masterclass no-show follow-up, and package-specific sales follow-ups. It uses production checkout and curriculum facts as the authority for price, product claims, and feature availability ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/9ac7d2683dc94148623014b5f331fc67b559806c)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/1fccf61d79222e794c91718637ec6325ea62fdf0)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/e834392666d431fba227ffcbcf0d218a712ed64d)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/9cfe120934d02c70fd2ed968ad0f281f484eea9f)) (original session `eb59d6be-403b-4f0d-b4c4-084a56bd88f3`).

- **Approved LLA presentation across all emails**: The full set uses the real logo, cream/navy palette, alert strip, and pill CTA instead of retaining the French Atelier skin ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/cded64d1b61353ddba44ef97e12ea9436b8517a0)).
- **Package-specific sales follow-up**: The maintained sales-email set has separate versions for Standard `$49`, VIP `$79`, and the Full Course. All preserve the operational placeholders and use a neutral ecommerce/phone opening rather than claiming a prior call (original session `eb59d6be-403b-4f0d-b4c4-084a56bd88f3`).
- **Offer descriptions stay tier-specific**: VIP includes the additional 30-minute Q&A; Full Course copy includes the 18-session program, recordings, course materials, CGM and VIP masterclass. Blueprint redemption wording is a separate commercial promise, not established by old package labels. (original session `eb59d6be-403b-4f0d-b4c4-084a56bd88f3`) (original session `f0880387-3aa3-4161-85ac-890ecca87e46`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Credit wording must match redeemable value**: VIP follow-ups include a `$249` credit label, but neither that label nor the alias JULIE249 establishes a cash-equivalent tuition deduction. (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`) `projects/lla-masterclass-attendee-offer` owns the revised approved schedule and short “Masterclass credit” label; installed email copy/offer parity remains unverified. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Product-specific feature claims**: The original Blueprint lifecycle copy removes unsupported course-Q&A claims and uses approved footage; this restriction is not the separate Julie VIP masterclass’s 30-minute Q&A offer ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/e834392666d431fba227ffcbcf0d218a712ed64d)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/9cfe120934d02c70fd2ed968ad0f281f484eea9f)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/66500f66c4c4c18015802ef13b17fc66234a03ba)) (original session `f0880387-3aa3-4161-85ac-890ecca87e46`).
- **Production-safe ActiveCampaign output**: The gallery previews emails with sample data but exposes production HTML using real ActiveCampaign personalization tags. Email cards avoid unapproved custom fields and use only Sandra’s three approved names as headlines ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/e5451299c374e320f98afccf2f5b65f3ec60c9a8)) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/e83ccd4dbc2335ac8173fa8427c8be4fba270d60)).
- **Sandra’s original length is the ceiling**: The three-tier edition keeps every email at or below the original Sandra copy length, so package differentiation cannot expand into longer lifecycle messages ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails-3tier/commit/067a6c3c)).
- **Abandoned-cart reminder copy follows the reference-email sequence**: The Blueprint reminder states the course promise first, then the personalized protocol, six pillars, and 18-live-session format. It uses “we’ll help you build” rather than implying the learner constructs the protocol without guidance (original session `c13c884d-4b6f-46da-ac47-0f64d9472631`).
- **One-time school acquisition is a separate handoff**: Omri’s Rosen/IIBS invitation variants live in `projects/lla-julie-invitation-blast`, not this lifecycle gallery. Ready-to-install email files do not prove that the corresponding ActiveCampaign sequence was installed or sent (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`).
- **No-show routing ends with the final event**: Emails `JM-X1`–`JM-X3` serve buyers who miss 2026-10-27 and can attend 2026-11-14. `JM-X4` serves 2026-11-14 no-shows with 30-day LMS recording access and the Blueprint promotion. It never invites them to a nonexistent later session. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/ebbe0a3c62c68ff2468c10ce32e0262b322cec02))
- **Recording benefit overrides stale sales copy**: Omri explicitly confirmed 30-day recording access and ordered all no-show “no replay” claims removed. The mixed-tier branch also removes unsupported $200 credit, sales-page detail buttons and the “started enrollment” footer; the replacement footer is “You received this as a masterclass registrant.” (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/18b89c487feac5389fb2d07a48844a2c4103cffd))
- **Chris owns deployment values**: Dynamic dates, Zoom and LMS links are Chris's responsibility, not defects to resolve by hardcoding guessed URLs. The handoff calls out “same Zoom link” consistency and November preparation/day-before/two-hour reminders. The reported source/gallery revision does not certify imports, links populated or sends. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Follow-up destination drives host parity**: Chris's final handoff has JM-U1–U4 pointing to `longevitylifeacademy.pages.dev` with MASTERCLASS-VIP; three checkout-screen abandoned-cart sequences for Regular/VIP return to Julie masterclass pricing. These are document-level destinations, not verified ActiveCampaign configuration. Omri authorized aligning pages.dev to the attendee offer instead of editing live emails in that urgent task. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) (original session `7f86bc26-cac2-4af5-8a69-13e059680d3d`)
- **No-show link and live copy are separate layers**: The no-show gallery links to `longevitylifeacademy.pages.dev/?enroll=1&plan=monthly&code=JULIE249`. Its $149×5 wording predates the separately approved $79-plus-four-$169 destination schedule; actual import, recipient copy and sending require independent verification. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

### Key surfaces

- Repo: `gitteromri-ux/lla-masterclass-emails` ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/9ac7d2683dc94148623014b5f331fc67b559806c))
- No-show review: `https://gitteromri-ux.github.io/lla-masterclass-emails/?v=18b89c4`. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### See also

- `projects/lla-delta-force`: lifecycle funnel architecture
- `projects/lla-course-checkout`: offer and event truth
- `projects/lla-promo-email-funnel`: campaign email standard
- `projects/lla-growth-engine`: recovery system
- `entities/longevity-life-academy`: client and offer
- `projects/lla-julie-invitation-blast`: one-time school invitation variants


---

Record: `lla-masterclass-attendee-offer` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Masterclass Attendee Offer

LLA Masterclass Attendee Offer is Omri's separate Blueprint enrollment and unanswered-question destination for masterclass attendees. The approved offer is $79 in month 1 plus four $169 payments, $755 total, with JULIE249 or MASTERCLASS-VIP. The branded page is reported published with the rebuilt design and checkout screens; actual paid enrollment, physical-iPhone completion and production sales-callback receipt remain unverified. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

### How it works

The page reuses the exact pages.dev components, course information and established checkout logic. The hero reads “Build your personal longevity protocol in 18 live classes,” includes the reference Trustpilot treatment and opens signup in place. Learning and syllabus content precede pricing; unanswered questions go into a separate callback section below pricing and all inclusions. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

- **Separate from event checkout**: The attendee surface does not replace live Julie registration or change protected CAPI. Omri separately approved restoring the dark attendee design and then requested link-only publication on the LLA domain. (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`) (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`)
- **Link-only is not access control**: The reported `noindex` and robots exclusion reduce discovery; the public URL is not an authenticated attendee entitlement. (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`)
- **Approved installment contract**: Month 1 shows crossed-out $169 beside $79; months 2–5 are $169 each. The actual reduction against $169×5=$845 is $90. The chosen short label is “Masterclass credit,” not cashback or an unsupported $249/$279 tuition-saving claim. No zero-dollar first payment is approved. The separate upfront option stays $799. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Same offer on email destination**: Omri separately authorized aligning pages.dev because the post-event email handoff points there. That offer/date alignment does not authorize copying attendee-only question content onto pages.dev. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Two actual first-lesson choices**: The November choices use Eastern/Pacific first-lesson dates, not the semester-start label or Israel/Central display times. `projects/lla-course-checkout` owns the exact semester/class mapping. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/1eb51fef8d87c807986880f455ad6e27f176d929))
- **Conventional compact pricing hierarchy**: One coherent offer, not competing installment cards. The four-payment $169 line is prominent; the $755 total is smaller and regular-weight. Coupon choices are restrained text rather than white/blue boxes. Display typography uses larger Playfair Display italic; equal benefit-card heights do not justify stretching the pricing card. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Benefits visible before purchase**: The four headings are “18 live classes / once a week,” “Master 6 longevity pillars,” “Abbott Lingo CGM included” and “Your personal Blueprint.” Mobile uses swipeable cards before pricing, an all-benefits summary, arrows and a counter. The standalone “Julie live masterclass included” card is excluded. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Callback is not enrollment**: The attendee-only form reuses Blueprint's question/contact/consent flow below the full offer, alongside the reference WhatsApp access. Final browser validation and response handling passed nine mocked-backend cases; that is not production sales receipt. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Test layers stay distinct**: Normal production signup reached checkout for both coupon aliases; controlled CRM/Golden reporting tests passed. The shared reference and attendee sandbox returned provider_unavailable, while live card fields loaded. No actual charge or final paid enrollment follows from those checks. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Mobile visibility requires rendered labels**: The final audit found Pacific labels in the DOM but computed display:none at 375px on the branded page. A fix was pushed while the branded build was still publishing. The separate pages.dev source includes the Pacific-label repair; final branded deployment and payment-provider QA approval remain open. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/6c27b2fff1d9bcaeeb8fb8687470ecc87b9b2de0))
- **Source-complete learning content**: The reported revision includes eighteen classes, four phases, fifty-four learning goals, class activities, between-class work, device requirements, recordings and FAQs. Restoring these sections follows the existing `.pages.dev` course page rather than inventing a new syllabus. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

### Surfaces

- Distributed attendee handoff: `https://www.longevitylifeacademy.com/blueprint-attendees-7q4x/?code=JULIE249`, backed by `Longevity-Academy/blueprint-attendees-7q4x`, not a folder in the main-site repo. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- Earlier learning-first clone: `https://gitteromri-ux.github.io/lla-masterclass-attendees/?code=JULIE249`. Its $149×5 and inclusion/expiry text is not the authority for the separately approved branded offer. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-attendees/blob/main/blueprint/index.html))
- The accepted full course film is distinct from the standalone masterclass adaptation; `projects/lla-julie-masterclass-video` records its asset identity and end-card evidence. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

### See also

- `projects/lla-course-checkout`: course enrollment and attribution
- `projects/lla-julie-masterclass`: live event and benefits
- `projects/lla-julie-live-operations`: production course-offer transition
- `projects/lla-blueprint-relaunch`: separate VIP comparison preview
- `projects/lla-julie-masterclass-video`: course-film asset and acceptance


---

Record: `lla-julie-official-social` | knowledge last updated: 2026-10-28T03:24:00+00:00

## Julie Masterclass Official Social Invitation

Omri's official LLA invitation package promotes the Julie Gibson Clark live event through the brand's Facebook and Instagram accounts. Its public handoff combines captions, copy controls, bio-link values and existing media; it is separate from executive/faculty posts and Julie's personal Instagram-only page. Publication of the handoff does not establish posting or account-bio changes. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### How it works

The official hub packages the full masterclass film, Zoom Blue short reel and Zoom class still with platform-specific copy and downloads. It uses the same event and registration destination as the live masterclass, not the Blueprint course-conversion page. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

- **Event-specific hierarchy**: The final requested order is LLA's invitation opening, “Learn to age slower with Julie Gibson Clark,” the 2026-10-27 7 PM Eastern/Zoom details, concise Julie/protocol context, three learning bullets, starting price/VIP Q&A, then the institution mission. The November date, competitor comparison and refund paragraph are excluded from this announcement. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Three teaching themes**: Biological-aging measurement and what moves the number; daily sleep/food/movement/stress routines; testing before spending. These are the announcement's teaching promises, not independent validation of clinical efficacy. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Campaign language is scoped to copy**: Omri selected “6.5 years per decade” and a second-slowest-aging authority hook for this invitation. The package's marketing wording does not independently establish a current global ranking or medical result. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Ticket and course offers stay separate**: The invitation starts at $49 for the 60-minute masterclass; VIP adds a private 30-minute Q&A. It does not advertise Blueprint tuition, a new 24-hour VIP promotion or an attendee course coupon. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Preserved media families**: The full landscape masterclass film, native vertical Zoom Blue reel and Zoom still remain available alongside feed/square/vertical derivatives. Blurred-fill versions are labelled rather than silently substituted for native formats. This is not the course-page film's accepted end-card proof. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Platform-native link behavior**: Facebook copy carries the registration URL in the body. Instagram copy uses link-in-bio language and separately copyable bio URL/title. A typed tag or prepared handle list is not evidence of resolved tagging, endorsement or distribution reach. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### Surfaces

- Official brand handoff: `https://gitteromri-ux.github.io/lla-masterclass-assets/social-share/official/`, with Facebook/Instagram tabs, copy buttons and media downloads. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- Registration: `https://www.longevitylifeacademy.com/julie-masterclass`. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### See also

- `projects/lla-julie-executive-social`: separate role-specific sharing package
- `projects/lla-julie-masterclass`: live event and registration


---

Record: `lla-julie-masterclass` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Julie Masterclass

LLA Julie Masterclass is the direct-ecommerce launch surface for Julie Gibson Clark’s live Longevity Masterclass. The maintained public pricing presentation has Standard `$49` and VIP `$79`; the historical three-tier build and Blueprint coupon are not a description of the current public cards. A separate community-offer clone does not replace the paid-campaign page. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

### How it works

The public class page presents Julie’s authority and syllabus, then routes registration and payment through eTeacher’s commerce stack. Purchase completion updates the contact-level ActiveCampaign checkout status with order, student, and session details ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass)) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-masterclass)).

- **Direct purchase, downstream community conversion**: The class is full ecommerce rather than a lead-form funnel, with a real purchase event and no in-checkout order bump in the original scope. Omri’s acquisition strategy builds a paying community for later Blueprint conversion through sales or direct checkout; that downstream goal is separate from an in-checkout upsell. ([recorded evidence](https://github.com/gitteromri-ux/lla-handoff-pack)) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Payment-response compatibility**: The checkout accepts PascalCase `StudentId` and `OrderId` returned by the lead API so the real order can advance into payment ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass)).
- **Attribution survives malformed campaign links**: The checkout recovers and persists `cid` from malformed double-question-mark URLs and avoids adding static Google campaign `116641` when a real campaign ID or non-Google source exists ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass)).
- **Class and VIP structure**: Standard sells the live 60-minute masterclass and VIP adds a 30-minute Q&A. The recorded session choices are 2026-10-27 and 2026-11-14. The earlier three-tier build also offered Full Course with Blueprint and VIP; that archived build must not be mistaken for the maintained two-card public page. (original session `f0880387-3aa3-4161-85ac-890ecca87e46`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- **One checkout, plan-aware downstream data**: The selected tier controls the order value, CRM course identifier, CAPI value and content name, and success-screen message. The plan is re-resolved when the staged order is created rather than frozen before selection (original session `f0880387-3aa3-4161-85ac-890ecca87e46`).
- **Post-purchase benefit is not a public pricing coupon**: `MASTERCLASS-VIP` is reported on the VIP post-payment success screen. `JULIE249` belonged to the older Blueprint pricing card, removed from public pricing on September 24. Neither old source memory nor the invitation discount establishes authoritative current Blueprint redemption terms. (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)
- **Marketing evidence remains source-faithful**: The marketing repository uses the real Trustpilot mark and approved LLA pillar videos, and simplifies the page to three clean statistics ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-masterclass)).
- **Authority proof uses recognizable evidence**: Julie’s portrait, biography, and plain-English statistics form one coherent section, while six press cards use real publication mockups instead of generic imagery ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-masterclass/commit/3f12738700d43129115d584deda9348732e1e16a)).
- **Critical content renders immediately**: Reveal fades were removed from the Julie and press sections so their headings and evidence are visible without waiting for scroll-triggered animation ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-masterclass/commit/a32c435e94dab8778e330b9d6fbfd209f15e5dff)).
- **Phone presentation is isolated from tracking**: Omri’s mobile work addresses readable hero/pricing typography, fold length, breathing room, navigation, and floating enrollment controls. The newer source adds a phone-only layer, followed by further phone/checkout revisions; those repository changes and emulated reviews are not real-device payment certification ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/97271cf58b8dde231a6a64752e9743564fb7132c)) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/8151806fd4046fa17b75783d1c8c3ff04111a629)).
- **Package screenshots and unpaid intents are not payment certification**: The nine delivered package-flow images cover details, session/price, and payment layouts, but the payment images were uninitialized or labelled previews (original session `dd017f79-f19e-40e4-9b16-9092f70b5529`). The later live review mounted one unpaid `$79` VIP intent without authorizing a charge; Standard, paid VIP, and paid Blueprint runs were not executed, and wallet methods had been removed rather than certified ([recorded evidence](https://github.com/gitteromri-ux/julie-launch-review-20260923/blob/review/FULL-SCOPE-STATUS-2026-09-24.md)).
- **Strategy artifacts are not the ecommerce handoff**: The staged-budget CEO deck and read-only version archives are separate from the working purchase site. A recovered Vercel URL returned 404 and was withdrawn as a usable delivery surface (original session `261e9757-116e-4a2c-8b89-19a0b118e688`).
- **Promotion messaging without a cross-product code**: Omri chose an automatic 36% masterclass discount for 72 hours, from $49, rather than advertising a `$249` coupon toward another product. He requested restored promo/floating controls and larger pricing copy without changing protected CAPI code. This wording decision is not evidence of a changed CRM price plan (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`).
- **Production rollback supersedes the recovery release**: The community clone remains separate. Omri authorized the tested `projects/lla-julie-checkout-recovery` for production, then explicitly ordered rollback to 2026-10-15 build `a188c6c`. Production therefore excludes that recovery/design port while retaining the merged tracking coverage patch; rollback is not frozen-tag restoration or payment certification. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Teaching materials have named versions**: The public `projects/lla-julie-masterclass-deck` separates Julie review's twenty-one teaching slides plus closer from the corrected V45 sequence. Version C and explicit overrides govern content; alternatives stay out of Play mode and publication is not Julie's acceptance. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- **Wallet configuration is surface-specific**: The maintained Julie payment-safety source lists Card, Google Pay, and Apple Pay with merchant country `CY` for Apple Pay. The main-site Card/PayPal-only change explicitly leaves Julie untouched; wallet configuration does not establish a completed wallet payment ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/blob/main/assets/julie-payment-safety.js)) ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/6b698eff26825a87c25a64a3a60c8a2fdf68dbb4)).
- **Call-center roster is order-level, not contact-level**: Omri’s expanded VIP and Regular handoff uses one row per masterclass deal/order, newest first, with contact details, country/state, tier, session and CRM identifiers. Test orders are excluded, VIPs highlighted and cancellation/duplicate flags retained. Both XLSX and native Google Sheet are left-to-right. (original session `117f81fc-a6ad-4602-b268-893abb797157`)
- **Roster counts have a precise evidence boundary**: The 2026-10-20 call-list snapshot has 129 paid-status order records: 36 VIP + 93 Regular, including two cancellation/duplicate flags; excluding them leaves 127. Five new Regular orders are measured against the corrected 124-order baseline, not the earlier reported 127 that still included three internal records. All acquisition sources are included; this is not processor settlement. (original session `117f81fc-a6ad-4602-b268-893abb797157`)
- **Deal history avoids overwritten-contact omissions**: Contact-level fields produced an incomplete report; full deal enumeration supports order-level reporting. The same-link sheet and Excel were updated and their 129 sorted order IDs verified equal. A later audience reconciliation reaches 131 orders/122 distinct emails at a later cutoff; those units do not replace the call-center snapshot or establish settlement. (original session `117f81fc-a6ad-4602-b268-893abb797157`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)
- **October 27 VIP roster is a distinct handoff**: Omri requested launch-to-current October 27 VIP enrollments only, excluding November and Regular, with all Meshi sales columns: name, phone, email, country/state, enrolled event and CRM Student/Order IDs. The delivered twenty-seven-row file is explicitly an October 20 historical backup; twenty-six rows lack source state information and the current refresh is incomplete. (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- **Order records and settlement stay distinct**: The `projects/lla-julie-checkout-incident` documents incomplete telemetry and repeated CRM-paid orders. Omri’s $49 test `8054067` is a real charge but not customer revenue; shared buyer identity does not establish accidental duplicate tickets, refunds or exact Meta event attribution. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Dated targets are not roster totals**: The `projects/lla-october-board-update` targets 350 registrations per date, 700 by 2026-11-14 and one Blueprint conversion per 10–12 masterclass buyers. Omri supplied 113 signups for board use on 2026-10-18; that figure does not replace a CRM-paid/VIP/per-date reconciliation. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Purchaser-audience extension is distinct**: The approved `projects/lla-julie-purchaser-audience` adds a lookalike/warm set, without changing the website or replacing the existing sets’ targeting. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Rehearsal ownership and presenter sequence**: Omri leads rehearsal; Harel opens as CEO, then Julie teaches. Courtney runs the room, slides, timers and Q&A handoffs. Omri later reported a poor rehearsal and requested a whole-team production timeline. The separate `projects/lla-julie-live-operations` guide preserves scripts and the original document; publication is not final presenter acceptance. (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **Event times and attendee recording**: The rehearsal brief uses 2026-10-27 at 19:00 ET and 2026-11-14 at 13:00 ET. Omri explicitly confirmed 30-day LMS recording access and ordered no-show “no replay” claims removed. `projects/lla-masterclass-emails` carries the corrected four-email branch and Chris's link/scheduling ownership. (original session `b3b81423-a57d-494a-9b97-c41f016bd1c2`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Attendee benefit is not public ticket pricing**: JULIE249 and MASTERCLASS-VIP belong to the separate Blueprint attendee offer, not the ordinary $49/$79 event cards. (original session `db0d86f4-82e3-4ed6-b13c-902f1e638f0f`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`) Omri approved revised Standard installments under short “Masterclass credit” wording; the alias is not a $249 tuition-deduction promise. `projects/lla-masterclass-attendee-offer` owns the actual offer and expiry/eligibility evidence. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Complimentary guest access is not a paid conversion**: Omri selected hidden-code `GUESTLIST`, valid through October 28 at 23:59 Israel time for both tiers. It is intended to create unpaid guest access without a charge, Purchase event or Blueprint VIP benefit. Separate Zoom admission remains unestablished; `MASTERCLASS-VIP` and `JULIE249` are Blueprint-related codes, not ordinary Julie checkout coupons. (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)
- **Guest-code usability includes visible controls**: The forensic audit traced hidden promo inputs to a 2026-09-23 CSS rule inherited by the later guest-code implementation. The field is now reported visible and GUESTLIST accepted for both tiers; no completed guest enrollment/Zoom-access proof follows from that check. No documented tracking rationale for hiding the field was found. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- **Wrong-school messages are a reported incident**: Omri reports IIBS-branded welcome/group WhatsApp messages after masterclass assignment and distinguishes his legitimate Blueprint reminder. No retrieved CRM audit establishes the responsible entity, ProductID, template mapping, exact trigger timing or impact on all attendees. (original session `e431dbfa-a68c-4adc-b8af-701f0309f281`)
- **Reminder investigation needs exact identities**: Omri separately reported missing WhatsApp reminders and requested tester-facing CRM Member IDs plus every October 26 Israel-time signup. The retrieved roster supplies StudentIds, not certified Member IDs: Omri 11673788/order 8054067 is associated with October 27; Keren Ziv 11653945/order 8032863 has no confirmed session. The complete cohort and field-equivalence mapping were not delivered. (original session `93ae6be7-ca41-4c79-bdaa-7638c404be09`)
- **Attendee course offer stays isolated**: `projects/lla-masterclass-attendee-offer` provides a separate course/question-box destination, with November class IDs and reported production signup/screens. These checks do not establish a completed paid course enrollment. (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **Brand announcement is distinct from role-specific sharing**: `projects/lla-julie-official-social` holds LLA's October 27 Facebook/Instagram invitation. It does not replace `projects/lla-julie-executive-social` or Julie's Instagram-only handoff, and a published asset hub is not a posted event announcement. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

### Key surfaces

- Checkout repo: `https://github.com/Longevity-Academy/julie-masterclass` ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass))
- Marketing repo: `https://github.com/gitteromri-ux/lla-julie-masterclass` ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-masterclass))
- Three-tier build: `https://github.com/gitteromri-ux/julie-masterclass-3tier` (original session `f0880387-3aa3-4161-85ac-890ecca87e46`)
- Call-center sheet: `https://docs.google.com/spreadsheets/d/1Zh5_yJkIp746hm8Dr6F4RANPUKRSr_ALU2KYM6ysVuI/edit`; XLSX file ID `1E178lM3XV8W0G8_yfQmvjN4ehlKkt8Wn`. (original session `117f81fc-a6ad-4602-b268-893abb797157`)

### See also

- `projects/lla-julie-community-offer`: separate community purchase clone; `projects/lla-masterclass-attendee-offer`: attendee course destination
- `projects/lla-julie-checkout-recovery`: isolated payment recovery preview
- `projects/lla-julie-checkout-incident`: rollback and order reconciliation
- `projects/lla-julie-masterclass-deck`: class teaching materials; `projects/lla-julie-live-operations`: team production guide; `projects/lla-masterclass-emails`: lifecycle and recording handoff
- `projects/lla-julie-meta-pilot`: paid-acquisition experiment; `projects/lla-julie-official-social`: brand-account event invitation
- `projects/lla-julie-tracking`: protected attribution contract


---

Record: `lla-julie-masterclass-video` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Julie Masterclass Video

LLA Julie Masterclass Video is the film and paid-social edit system built around Julie Gibson Clark’s on-camera longevity story for Longevity Life Academy. It carries a course-promotion release line and a separate adaptation for the standalone live masterclass (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`) ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be)).

### How it works

The edit keeps Julie’s monologue in its approved narrative order, inserts matching pillar b-roll on the spoken words, and closes with the established LLA course-card and enrollment sequence (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`) (original session `bd50ffb8-ceb9-432b-a6b9-634d727dc6aa`).

- **Locked narrative order**: The structure runs intro, identity, willpower hook, credentials, mechanism, method, payoff, one-use repetition insert, CTA, closing cards, “I’m Julie, welcome,” and outro. Reordering or duplicating monologue lines is a release error (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`).
- **Word-synchronized b-roll**: Sleep, food, and movement each use one dedicated six-pillar library shot exactly where Julie says the matching word, with a return to Julie between inserts (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).
- **Disallowed footage stays excluded**: The Harvard age graph, lab/pipette shot, and green b-roll are not part of the approved Julie edit (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).
- **V16 card architecture**: A full clock graphic precedes “Uncover the secret to slow down aging”; the 90-second cut places “Master the six pillars” immediately before “18 Live Session Course”; the close then uses biomarker/protocol, CGM, Zoom, and enrollment assets (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).
- **Voice-first audio chain**: Julie’s camera mic measured near `-35 LUFS`; the accepted repair adds roughly `+19 dB` gain with compression/EQ before the mix, then re-ducks music and masters near `-13 LUFS` with peaks below about `-1.2 dBTP` (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).
- **Approved pillar sources only**: Food, sport, supplements, and movement use the designated Drive library; sleep comes from the Master Six Pillars film. Stock or invented substitutes are outside the brief (original session `bd50ffb8-ceb9-432b-a6b9-634d727dc6aa`).
- **Course-promotion release line**: Julie’s approved GitHub release is V24, separate from Courtney’s numbering, with full and 90-second masters, music stems, fonts, and matching V24 storyboards under `julie-v24-final` (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads)) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`).
- **Version-paired handoff**: V24 introduced Playfair captions, corrected pillar timing, and a sharper eTeacher logo; V23 boards must not be paired with V24 films because the caption styling differs (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`).
- **Accepted course-page asset**: The attendee page and pages.dev serve the same full course film: 139.050667 seconds, 1280×720 H264/AAC, 19,553,623 bytes. The pages.dev asset is `assets/julie-film-v20260927/full-film-720p.mp4`; the branded attendee copy is `lp/julie-film-720p.mp4`. Native MP4 playback replaces the broken stream path on those surfaces. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Course end cards, not event advertising**: Captured frames show “18 Live Session Course. Claim your seat,” the biomarker/protocol card and the final LLA “Enroll Now” card. Omri accepted this evidence and left the full film unchanged; the final card does not literally say Blueprint. This acceptance is scoped to the course-page film, not all standalone-masterclass social edits. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Editor typography**: Cards use Playfair Display Regular/Italic, captions use Playfair Display ExtraBold, and supporting text uses Inter Regular/SemiBold (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`).
- **Raw-source mapping**: Julie’s V23 source map uses the 1920×1080 main Riverside camera, not the second camera, and records five raw-camera sync points for reconstructing on-camera segments (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`).
- **Motion-package design system**: Julie’s supporting data animations use a shared navy, ice, and light-blue language with distinct cinematic concepts, oversized feed-readable type, immediate cold-viewer clarity, safe zones, and no decorative abstraction or invented claims (original session `6164427a-685c-483d-9610-b2895f09a15b`).
- **Corrected render replaces the flawed batch**: Headline smear in animations 3–5 requires corrected 4K masters and mobile-safe playback proxies to be deployed and visually approved before the package is treated as final (original session `6164427a-685c-483d-9610-b2895f09a15b`) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-animations)).

### Live masterclass film adaptation

The separate `lla-masterclass-assets` source specifies twelve paid-social cutdowns: 75/60/45-second variants in 16:9, 9:16, 1:1, and 4:5. Its earlier rendering labels do not certify final delivery of all twelve. Omri later selected the full approximately 2:18 source for the public social handoff rather than the mistakenly selected 56-second cut; this work does not itself change the purchase site or tracking. ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be)) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)

- **Original card hierarchy retained**: The adaptation swaps in live-masterclass copy while retaining the film’s layouts, fonts, sizing, and word count. Press proof uses three large recognizable publication cards rather than small unreadable tiles ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be)).
- **Zoom appears once**: The live Zoom class uses the later shot; the earlier slot returns to original B-roll, and the faculty card retains its original design ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be)).
- **Continuous music rather than stitched fragments**: Each cut uses one music bed aligned to the master’s swell beneath the closing cards. Talking-head captions and native vertical/square card layouts remain part of the specified cutdown treatment ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-assets/commit/21f5b29b853711f0d6e12ae8c18a2432dcbac3be)).
- **Full-film corrections preserve the rest of the edit**: Omri requested exact source card design/fonts, both event dates large, repaired music dips and equal 0.9-second press-logo holds without changing other cuts. The assistant reported full-film revisions and 1920×1080, 1080×1350, square and vertical social variants with blurred fill rather than cropped text. Version labels changed while a filename was reused; filenames alone do not establish approval of the final film. (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)

### See also

- `entities/julie-gibson-clark`: on-camera authority
- `entities/longevity-life-academy`: client and course
- `concepts/video-quality-qa`: release-quality gates
- `projects/lla-s09-s10-video-delivery`: Courtney video system
- `projects/lla-julie-masterclass`: standalone class offer
- `projects/lla-julie-meta-pilot`: live campaign deployment; `projects/lla-julie-executive-social`: public social handoff


---

Record: `lla-julie-masterclass-deck` | knowledge last updated: 2026-10-28T03:24:00+00:00

## Julie Masterclass Speaker Deck

Julie Masterclass Speaker Deck is Omri's teaching and review presentation for Julie Gibson Clark's 60-minute Zoom class. The Julie review and V45 are distinct versions with different selected playback sequences; the review has twenty-one teaching slides plus an appended closer. Version C and Omri's explicit overrides govern content, not a single universal slide count. Publication does not establish Julie's acceptance. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`) (original session `59567e86-3c35-48de-83af-fed43792d9db`)

### How it works

The source is `The-Longevity-Masterclass-script-three-versions.docx`, Version C, with its spoken text and “On screen” directions. The deck teaches longevity foundations rather than reproducing the script as dense slides. Omri accepted a meaning-first structure before moving from redesign to curation of his selected slides. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)

- **One official title, then the human why**: Julie's running-from/running-to story is the emotional center; her measurement supports it and the protocol is its practical payoff. The user rejected treating ordinary age/capability examples as the main story or splitting the opening into multiple fact cards. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Foundations before icing**: The cake organizes sleep, food, movement and stress, distinguishes menopause therapy as its own thin layer, and places other therapies in the icing. Whole uncut cake throughout the teaching; only the closing white cake is sliced. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Teach in an intelligible order**: Explain the measurement with DunedinPACE, introduce the cake, teach sleep, diet framing before sugar, movement categories before body-system effects, then stress and the integrated day protocol. Finish with measuring before buying, the whole cake and Why/Intention/Resources. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Testing and personal choices are distinct**: The curated review includes `Test. Then buy.` at slot 19. Version C names Vitamin D, Homocysteine and red blood cell nutrient levels; the assistant treats Julie's disclosed supplement list as spoken content with a list-bearing alternative. Exact costs were not supplied by the script. This review's testing/disclosure content is not evidence that every public syllabus was updated. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Fidelity before redesign**: The curation preserves selected designs and keeps alternatives out of Play. The twenty-one teaching slides have twenty-nine alternatives; all were expanded/full-color in Omri's open Julie review tab. Displaying an option does not select it for Play or establish remote-browser synchronization. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- **Specific selected placements**: The Round 10 plate is slot 10, before sugar; DunedinPACE appears beside slot 3. The weekly protocol already exists at slot 15 and is not a missing slide. Omri's v2.2 approval is limited to its title card, brain, gauge, cake and protocol-ring concepts, not similar-looking versions generally. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)
- **Separate selection stages**: The full canvas spans 24 version groups/457 reported previews. An 86-slide shortlist supports multiple choices per topic and all-86 visibility; the later 39 choices plus added WHY image form a 40-slide working collection, not the single main presentation. (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)
- **Legible scientific visual language**: Playfair Display italic, very large text and source lines, light/dark variation, clear separation of text and imagery, real sourced scientific models, no Julie portraits or generated people. Alternate review designs remain separate from the final image-preserving curation. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Clean-logo derivatives preserve originals**: The assistant reports replacing inconsistent baked-in marks across all 21 main images with clean light/dark website logos at a consistent relative size. The originals remain in the repo, option thumbnails retain originals, and review/Play use the new derivatives. This reported repair is not presenter acceptance. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Course bridge and final action slide**: The separate `projects/lla-julie-closing-slide` foregrounds Blueprint with sugar/CGM, movement and sleep. The selected image was appended as Julie review slide twenty-two while the preceding twenty-one were protected; final creative acceptance remains open. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- **V45 preserves original slide references**: Omri's V45-only directions remove original slots 9 and 12, split 10 into Food then plate, and retain the specified existing Claude replacements. Movement week V2 is a full-color alternative under slot 15, labeled “Julie to update,” not an additional main playback frame. Trajectory readback corrects an earlier misleading insertion report: twenty main slides precede the separately appended exact closing image. (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- **Stable URL is not live remote refresh**: Publishing keeps the V45 address but does not update Julie's already-open browser automatically. Updating Omri's local Comet tab is not presenter synchronization. (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- **V46 is a separate source version**: The maintained `/slide-canvas/v46/` tree includes a slide-order/hash lock, PPTX and image/build sources for Julie-comment revisions. Its sleep card adds “8 hour opportunity”; the protocol source changes the caffeine cutoff to 9 AM and the food source removes “On my plate.” These code/assets do not prove final presenter acceptance or which version is open during delivery. ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-syllabus/commit/a6f832b4e0c45ce38d37059f40f1de162b3c48da))

### Review mechanism and remaining delivery

- **Comments are browser-local until sent**: Text boxes persist in local storage. `Send my comments` composes an email to Omri and copies the same labelled text to the clipboard; there is no shared backend. Generated email content and persistence were checked, not inbox receipt or real-time comment visibility. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Content/design acceptance remains open**: The final user-approved message names the sauna and “It's your life. Live it well.” end card as still to add, plus further nutrition/movement design work. An earlier audit also identified wording, 7,000-versus-8,000-step and stress-graph differences; the final “headlines word for word” assurance does not demonstrate their repair. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **Moderator document is separate**: `projects/lla-julie-live-operations` owns the team run-through and script navigation, including Courtney's slide/timer and Q&A operations. Omri reports poor rehearsal feedback; presenter acceptance and live-production clearance remain separate from the existence of the guide. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)

### Surfaces

- Main Julie review: `https://gitteromri-ux.github.io/lla-masterclass-syllabus/slide-canvas/julie/`; Play runs the selected main sequence only. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- Full visual canvas: `/slide-canvas/`; grouped shortlist: `/slide-canvas/shortlist/`; exact working collection: `/slide-canvas/selected/`, all on the same syllabus GitHub Pages site. (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)
- Script source: `https://github.com/gitteromri-ux/lla-masterclass-syllabus/raw/main/script/The-Longevity-Masterclass-script-three-versions.docx`. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)

### See also

- `projects/lla-julie-masterclass`: class and commercial offer
- `projects/lla-julie-communications-plan`: approved syllabus source
- `projects/lla-julie-executive-social`: social promises follow syllabus
- `projects/lla-julie-live-operations`: slide and script handovers
- `projects/lla-julie-closing-slide`: action composition and archive
- `projects/lla-julie-live-qa`: deck-based live answers


---

Record: `lla-julie-executive-social` | knowledge last updated: 2026-10-28T03:24:00+00:00

## Julie Masterclass Executive Social Package

Omri's executive social package promotes Julie Gibson Clark's masterclass through distinct CEO, management/board and faculty voices. A public no-login sharing hub is reported delivered with nine posts, copy buttons and platform-sized media. Public availability does not establish actual posting, audience response or approval of every claim. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`) (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)

### How it works

The brief addresses readers unfamiliar with Julie or longevity, introduces LLA's personalized-protocol education mission and invites them to a rare live teaching event. Harel's launch post is a tone reference, not permission to repeat its Bryan Johnson/$2 million opening. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)

- **Three speaker roles**: Harel's version is CEO-only; the management/stakeholder version is intended for Omri, the board and senior colleagues; faculty need their own voice. Claims about teaching experience, attendance or personal endorsement cannot be inferred from membership in a distribution list. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- **Historical ranking, not current global rank**: The requested authority hook identifies Julie's 2023 Rejuvenation Olympics result. The assistant's final audit identifies conflicting age/rank language, “proven protocol,” “no laboratory” and unsupported scarcity in the drafts; the audit is not a repaired package or independent verification of biography. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`)
- **Mission and event are distinct from Blueprint**: LLA helps learners develop personalized longevity protocols; the live invitation is not an 18-week course purchase or a replacement for Blueprint. The curated teaching review follows Version C and explicit overrides, with testing/disclosure content; neither old social drafts nor a public review page establish final syllabus acceptance. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`)
- **CEO institutional voice**: Omri's corrected framing makes Julie integral to LLA's mission and unique course design, not the person to whom the academy outsources its thinking. The revised posts retain a strong introduction, restrained subheads and paste-compatible emphasis. (original session `607a8771-2773-4d2d-8e4e-07acb0f39353`)
- **Platform-specific handoff**: The public hub has CEO/management/faculty × LinkedIn/Facebook/Instagram copy, tracked URLs and three attachment families: Zoom Blue, the selected masterclass film and Julie-on-Zoom still. Reported adaptations cover landscape, feed, square and vertical sizes with muted autoplay, opt-in sound and downloads; these are not posting results. (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`)
- **Link placement is platform-specific**: The later reported hub removes first-comment buttons: LinkedIn/Facebook use body links, Instagram uses a Story Link sticker rather than a bio-change requirement. This records the chosen package behavior, not a verified universal reach/algorithm claim. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Brand accounts are platform-specific**: Omri states LLA has Facebook/Instagram but no LinkedIn page, and excludes Bryan Johnson tags. The revised hub identifies `@longevitylifeacademy` for Instagram and the official Facebook page; a typed mention is not proof it resolves for every poster. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Separate Julie-only Instagram handoff**: Omri explicitly requested Instagram only, her approved caption and three downloadable choices: full film, short video and still, without Harel/management/teacher drafts. The later session reports that isolated GitHub page live with copy buttons and Instagram sizes. This establishes the corrected requested scope and reported delivery, not final acceptance or actual posting. (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **Official brand invitation has its own scope**: `projects/lla-julie-official-social` packages Facebook/Instagram copy and existing media for LLA's own event announcement. Its bio-link workflow and October 27-only copy do not replace the executive hub's Story-link treatment or Julie's personal approved caption. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Public surface replaces repository-only delivery**: Use `https://gitteromri-ux.github.io/lla-masterclass-assets/social-share/`. The earlier private `julie-masterclass-social-posts/README.md` is not the delivered open hub. The earlier session's rejected writes and later public recovery are distinct outcomes. (original session `439a0622-9c29-4beb-a842-cfe2507b97c8`) (original session `607a8771-2773-4d2d-8e4e-07acb0f39353`)

### See also

- `projects/lla-julie-masterclass`: event and commercial offer
- `projects/lla-julie-masterclass-deck`: approved teaching content
- `projects/lla-julie-communications-plan`: broader Julie campaign briefing
- `projects/lla-julie-masterclass-video`: full-film social adaptations
- `projects/lla-julie-official-social`: separate brand-account event invitation


---

Record: `lla-course-checkout` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Course Checkout

LLA Course Checkout is Blueprint's self-service enrollment and eTeacher CRM integration, based on Rosen's checkout flow. (original session `d671ac39-6efd-4bed-b813-20a26fa5b2ab`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout)) (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/fc4db99dbda96141670dd0fab691e47fbbe33b59)) It runs on pages.dev; the approved offer-alignment audit did not complete a real payment. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

### How it works

The project pairs a long-form LLA landing page and Bio-Age Quiz with a three-stage self-service checkout and Airwallex payment screen. The production surface now runs at `longevitylifeacademy.pages.dev`, with the CRM proxy allowing that origin and the checkout using the same environment in which the order was created ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/fc4db99dbda96141670dd0fab691e47fbbe33b59)) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/940ba8cf638938b6a9f527bf2fad0000171a77c6)).

- **Reference fidelity over reinterpretation**: The checkout mirrors Rosen’s structure, field order, labels, tooltips, payment-brand marks, testimonial rail, and `Proceed` action while replacing the school-specific content with LLA facts (original session `d671ac39-6efd-4bed-b813-20a26fa5b2ab`).
- **One course truth across the funnel**: The course has eighteen live weekly sessions, cohorts of 8–15 and a written personal longevity protocol. (original session `d671ac39-6efd-4bed-b813-20a26fa5b2ab`) November's choices include both Monday and Wednesday classes. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Approved offer configuration**: Monthly base is $169×5=$845; JULIE249 and MASTERCLASS-VIP select $79 first payment plus four $169 payments, $755 total. Upfront stays $799. Omri authorized pages.dev to match the branded attendee offer, and the source implements that schedule; no new real payment was submitted in that alignment audit. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/ac35c2874e54bcc2b67f14beaff4ed8c900f9962))
- **Live Airwallex boundary**: Production uses the Airwallex Drop-In card form and displays the real payment amount; staging remains routed to the Airwallex demo environment for valid test-card behavior ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/940ba8cf638938b6a9f527bf2fad0000171a77c6)) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/40549832efc90ca9eda840b21548178110301b53)).
- **Private source and Cloudflare hosting**: The repo was made private, which unpublished its former GitHub Pages deployment; the checkout now runs from Cloudflare Workers static assets while `elijahworkz` has read access for eTeacher review (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`).
- **Secrets stay at the Worker layer**: Staging and production service-token headers, API tokens, and server URLs are encrypted Cloudflare bindings rather than code. The upstream API requires `Authorization: token`, not `Bearer` (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`).
- **Approved staging order mapping**: `AddNewECommerceLeadAndOrder` uses ProductID `26`, MainAbroadCourseId `258`, AbroadCourseId `1774`, PreferredCourseId `-1`, LanguageId `101`, IsTrial `0`, and campaign `cid=116641` inside `QueryString`; `CampaignID` is omitted (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/ecc6c6a5)).
- **CRM is the pricing authority**: The checkout resolves schedule and payment details from the same CRM environment that created the order rather than trusting marketing-page copy when totals differ (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/40549832efc90ca9eda840b21548178110301b53)).
- **Class identity selects CRM pricing**: The checkout sends course and class identifiers rather than a monetary amount. CRM resolves the configured price and payment plan, returns its own Airwallex intent, and remains the authority for subsequent merchant-triggered installments (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Promotional pricing must preserve the CRM round trip**: Multiple payment plans can exist against the same `$1,399` course total. The safe implementation path is to bind to a CRM class or payment-plan configuration that produces the intended first payment, then prove the complete result in staging; charging a separate amount outside CRM would create an order/payment mismatch (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Promotional override uses CRM-supported payment fields**: The safe lower-price path was proven through `FirstPayment` and `NumberOfPayments`: staging completed the round trip, while production minted a live intent at the overridden first-payment amount without changing the course catalogue total (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **No write on page visit**: Automatic order creation was removed; opening the checkout never writes to CRM. The integrated website flow creates the lead only after valid Stage 1 data and a successful `Continue` action ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/00f3bf9f21b7c6162d2815a0409ce7d1bc048c98)) (original session `600e5062-67d9-4632-95b0-11e7295e9508`).
- **Lead generation and ecommerce share one form sitewide**: Homepage, bio-age, founders, store, and staging lead forms keep the application as the primary path while adding a prominent `Enroll Online Now` action into the same card; the action opens an on-page CRM checkout instead of presenting a chooser or “skip the call” path (original session `600e5062-67d9-4632-95b0-11e7295e9508`) ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/8d8aaac3411233bb51313eed72880874aa479185)).
- **Worker deploys only the prepared static bundle**: The private repo uses `wrangler.static.toml` with `dist/`; publishing the repository root would expose working files and exceed asset limits (original session `025ef529-f6b6-46d6-82d0-39a257149ad4`).
- **Three-stage Meta funnel is isolated from CRM writes**: Screen 1 `Continue` sends `AddToCart`, screen 2 `Continue` sends `InitiateCheckout`, and successful payment sends `Purchase`. Browser and server copies share a stable event ID, session guards prevent repeated pre-purchase events, and the event code does not create additional CRM leads ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/5fdebd36fa699860995e5eb3ee6968023168ce2a)) (original session `e8f80581-31fc-4a86-989d-138e3812a19f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/9d06ca7)).
- **Narrow ActiveCampaign event route**: The Worker exposes `POST /api/ac/event` for checkout-trigger updates, but writes only the `LGV_checkout_events` latest-status field: no lists, tags, or extra contact fields ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/9a923c7e541eb3d2381dd08315b0eaa6f12da843)) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/7dc419a824ac8bb583998cb2bd43f5ac01423347)).
- **Meta account remains read-only**: Funnel instrumentation belongs in the checkout website code; the implementation did not change Ads Manager, GTM, CRM, the integration Worker, or Airwallex (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Homepage tests write to production**: The homepage ignores `?env=staging`; an end-to-end AddToCart check created production CRM order `8014922`. Checkout QA therefore needs a production-write safeguard and cleanup of test orders (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Production QA requires explicit cleanup**: No-card or failed-card probes created production orders `8018522` and `8019354`; both are test records that should be purged alongside earlier production QA orders (original session `e8f80581-31fc-4a86-989d-138e3812a19f`) (original session `b67fcc3a-79db-4df7-9b0b-7eaea2397dae`).
- **USD is locked at two layers**: The CRM order is created with US pricing for every buyer while the buyer’s real country and phone are retained for operations; the page also blocks any non-USD payment intent from rendering. This prevents the Israeli-country path from silently minting an ILS charge (original session `7777d4e8-1fdf-4453-b28c-8c53a8e6c65c`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/dc1dce2ee5)).
- **PayPal is a parallel eTeacher payment path**: PayPal runs through the PayPal JS SDK and reports its approval identifiers to `SetECommercePayment`; it is not an Airwallex Drop-In method. The card path remains Airwallex (original session `7777d4e8-1fdf-4453-b28c-8c53a8e6c65c`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/dc1dce2ee5)).
- **Every checkout entry point preserves the three-screen flow**: Plan cards, navigation, drawer, floating CTA, and other enrollment links are intercepted even when they carry `?plan=monthly` or `?plan=upfront`, preventing direct jumps to a dead payment page (original session `7777d4e8-1fdf-4453-b28c-8c53a8e6c65c`).
- **CRM provisioning is asynchronous**: `GetECommerceFirstPaymentDetails` can temporarily return `OrderId=-1`; the checkout retries the read and converts permanently expired orders into a clean restart rather than exposing raw CRM JSON (original session `7777d4e8-1fdf-4453-b28c-8c53a8e6c65c`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/dc1dce2ee5)).
- **Multi-host attribution must be audited as one system**: The Pages checkout, the LLA store checkout, and the Worker checkout can all feed the same CAPI relay. Correcting `fbc` on only one host does not close the attribution defect (original session `877b3029-7b5b-4444-aa88-b40f2dfe9722`).
- **Ecommerce “Contacted” inflation is a Sisense definition issue**: Self-service orders were counted as Contacted despite zero rep calls. The safe remedy is an eTeacher BI measure filter that classifies the ecommerce order identifiers as Leads; changing checkout events or form behavior would solve the wrong layer (original session `e50e3c64-a87e-4499-ae63-5d0730d6b1e2`).
- **Presentation and commerce remain separable release layers**: The institution/eTeacher fold and mobile CSS can be revised without changing checkout JavaScript, CRM hooks, or Meta event code. A full-page audit is still required because mobile-only CSS fixes can leave desktop and residual selector defects (original session `a1a76d15-f6ab-46d0-8e4f-f36d2a7fe5ff`).
- **Repository handover is part of the release surface**: The source now includes a handover document plus dedicated audit and deploy tooling, so future releases can be checked and published from the maintained repository rather than reconstructed from an opaque live bundle ([recorded evidence](https://github.com/gitteromri-ux/lla-handoff-pack)) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/c458f13770dbdd2b1e02559c0fd3a8d28bd38642)).
- **Redesign work stays isolated from commerce**: Premium visual changes live on `design/luxury-transform-v1`; the live page, checkout, GTM, Meta Pixel, CRM, Airwallex hooks, and video sources remain outside that branch’s redesign scope. The branch still requires visual and responsive approval before any release (original session `b215bc27-e478-46fe-970d-9e2cba4884f2`).
- **Cohort choice precedes order creation**: The buyer selects from CRM-backed cohort rows before the order is created. Israeli operating times are converted into clear US-facing card dates, the selected cohort is written into CRM notes, and enrollment remains available for seven days after a cohort starts (original session `93982c4b-9e0a-4555-a85d-c5adf8a3709f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/a0e3995)).
- **Payment-plan choice precedes the CRM round trip**: Monthly and upfront selection now happens before order creation so the selected offer, CRM order, and Airwallex intent cannot drift into different amounts (original session `93982c4b-9e0a-4555-a85d-c5adf8a3709f`).
- **Purchase identity is hydrated before the existing event fires**: The completion path retrieves buyer identity from the existing CRM checkout/details response before sending the unchanged Purchase event, improving match inputs without creating another CRM write (original session `dc80bd1f-43dd-41aa-a0a9-a71e1cc29b4b`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/f017311)).
- **Wallet integration and acceptance are separate**: The wallet implementation used the existing Airwallex Drop-In, while PayPal remained a parallel tab. The earlier release record covers `.dev` and `.com/blueprint`, not every checkout copy or current wallet acceptance (original session `f7ef9939-c682-4966-ab55-c859f3167e77`).
- **WhatsApp is a direct support entry point**: The checkout and related LLA forms use `https://wa.me/12015023701`; the final implementation is a direct WhatsApp link with an IIBS-sized floater, not an on-site chat popup (original session `93982c4b-9e0a-4555-a85d-c5adf8a3709f`).
- **Mobile rendering must stabilize before interaction**: The r16 build moved late page styles into the document head, deferred phone video loading until after page load, preloaded the poster and fonts, and shared the browser/server PageView event ID. This removed the measured layout shift that could move the primary CTA under a buyer’s finger ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/48774e94)).
- **Payment-method preservation is a release gate**: Card runs through Airwallex while PayPal remains a separate path. A device audit that cannot see PayPal is not permission to remove it; the live render and maintained source are separate evidence layers (original session `88173292-8ba8-4b89-8435-20f250919933`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/bd8837a9)).
- **Event QA is end-to-end, not code-only**: Matching browser/server IDs and a Meta `200` response prove transport but not complete funnel health. The latest audit still found browser-only InitiateCheckout behavior on some iPhone transitions and a rejected server `Enroll_CTA_Click`, so event coverage must be verified at each step rather than inferred from AddToCart alone (original session `88173292-8ba8-4b89-8435-20f250919933`).
- **ClickID transport and ad-set attribution are separate proof layers**: The relay and checkout copies now preserve the original ClickID through navigation, refresh the cookie at send time, and can correct a mismatched cookie when the original ID is present. Controlled AddToCart events reached Meta through CAPI, but no qualifying Ad Set 2 interaction was proven to complete attribution in the checked window (original session `653edf1a-2b37-4695-ac45-302de528ddef`).
- **Live reporting cannot be treated as net customer activity without test reconciliation**: Meta totals were repeatedly contaminated by production QA, and Ad Set 4 view-through events could not be classified event by event as genuine customers or tests. Reporting must separate verified test, verified customer, and unresolved activity before commercial conclusions are drawn (original session `a43dd532-6960-481c-a712-882a6081a8e5`) (original session `23822628-c1d7-4345-acf3-6b6e6c078cb9`).
- **Mobile release evidence requires physical-device completion**: Responsive emulation passed across the selected profiles, but the requested top-ten iOS and top-ten Android physical-device matrix did not. The candidate remained on HOLD with production unchanged and a compact Samsung rotation condition unresolved (original session `eb5e1f20-f4b7-495d-89c7-119102c6ae3d`).
- **Card/PayPal scope does not transfer to Julie**: Apple Pay failed merchant validation in the production domain context despite verification files and IIBS-matched options; no completed wallet payment proved that flow (original session `49da238d-ec07-4c74-85c2-42e13984b328`). The Blueprint source removes Apple Pay/Google Pay, and a separate main-site commit applies Card/PayPal-only configuration to `/checkout/` and `/blueprint/checkout.html`, explicitly leaving Julie masterclass untouched ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/280e385)) ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/6b698eff26825a87c25a64a3a60c8a2fdf68dbb4)).
- **Support and enrollment events remain measurement-specific**: Historical WhatsApp clicks cannot be recovered because the links were not wired to a dedicated counter. The older `Clicked_on_Enroll` rule also misses capitalization and wording variants, while the separate `Enroll_CTA_Click` route uses different counting logic; the two event families cannot simply be added (original session `1f15da00-ebd8-4e11-b762-48ab50e207f9`) (original session `a6445ad4-cc79-4601-8614-8943bdf58f0b`).
- **Separate direct-funnel relaunch**: Omri’s `projects/lla-october-board-update` distinguishes Blueprint direct acquisition from masterclass upsell. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) The `projects/lla-blueprint-relaunch` retains unselected VIP comparisons in a payments-disabled review. Standard's approved attendee schedule has its own production authorization and does not establish a VIP release. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Blueprint needs its own paid-ad proof**: The challenged campaign `#116622` report showed zero Meta purchases after approximately 390 AddToCarts and $11,689 spend. That is not proof of zero real sales. The assistant withdrew categorical tracking-health claims: Julie's golden transaction cannot certify this separate `pages.dev` funnel, whose paid-ad-to-Purchase chain was not demonstrated. (original session `292ed309-b521-461b-a3f4-e8b6438eec24`)
- **Attendee offer is a separate enrollment path**: `projects/lla-masterclass-attendee-offer` shares the approved Standard schedule and established checkout mechanism without replacing Julie event registration. Its production signup/screens and controlled reporting checks are not a completed paid enrollment. (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)
- **November class mapping**: Semester 2395 offers class 170275 on 2026-11-23 at 8 PM EST/5 PM PST and 170277 on 2026-11-25 at noon EST/9 AM PST. Course IDs are preserved while the displayed timezones reflect the actual November first lessons, not the semester-start label. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`) ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/1eb51fef8d87c807986880f455ad6e27f176d929))

### Key surfaces

- Repo: `gitteromri-ux/lla-course-checkout` ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout))
- Checkout: `https://longevitylifeacademy.pages.dev` ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout/commit/940ba8cf638938b6a9f527bf2fad0000171a77c6))
- Integration Worker: `eteacher-leads-proxy` (original session `cc4e0505-3765-4dea-949a-1010b12d8f18`)

### See also

- `projects/lla-october-board-update`: separate direct-funnel relaunch plan; `projects/lla-masterclass-attendee-offer`: attendee course route
- `projects/lla-julie-meta-pilot`: paid acquisition proof boundary
- `projects/lla-growth-engine`: recovery marketing system
- `projects/lla-masterclass-emails`: lifecycle follow-up system
- `projects/lla-funnel-performance-deck`: ecommerce performance review
- `projects/lla-julie-tracking`: separate masterclass attribution contract


---

Record: `lla-blueprint-relaunch` | knowledge last updated: 2026-10-28T03:24:00+00:00

## LLA Blueprint Relaunch Preview

Omri's Blueprint relaunch reconstructs the full course funnel with an introductory-payment Standard package and a separate VIP comparison. The GitHub review's three VIP schedules remain unselected preview alternatives. Standard's $79-plus-four-$169 schedule is separately approved for the attendee page and pages.dev; that release does not activate a VIP variant or approve the comparison design. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)

### How it works

The approved review preserves the existing long-form course page and presents Standard and VIP side by side. Omri authorized a duplicate when the original introductory-payment revision could not be recovered. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)

- **Standard stays fixed during comparison**: Blueprint is $79 for month 1 plus four $169 payments, $755 total. Omri corrected the introductory number to $79, not $69, and requested the same Standard card beside every VIP variant. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Three VIP review options**: Option 1: $99 plus four $199 payments, $895 total, $140 above Standard. Option 2: $129 plus four $229, $1,045 total, $290 above Standard. Option 3: $99 plus four $229, $1,015 total, $260 above Standard. These are comparison alternatives, not three approved production plans. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/lla-blueprint-vip-preview/commit/70b8dff7df82679feca86359b1c5b4091f7a7c4e))
- **VIP adds four benefit categories**: Monthly one-to-one teacher sessions, two CGMs delivered by lesson 5, $299 credit toward the next LLA course and 30% off quarterly masterclasses. These are Blueprint offer terms, not the masterclass VIP Q&A or its separate course-benefit scheme. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`)
- **Approved headline, preserved structure**: “Build your personal longevity protocol in 18 live classes.” Julie’s hero caption is removed; the hero background remains. Pricing belongs sixth, after Julie’s bonus and before the syllabus, not inside or immediately after the hero. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Page-specific copy constraint**: Omri prohibited all-caps display wording, decorative dashes, pill badges and generic promotional filler throughout this Blueprint review. That correction is not a request to alter Julie Masterclass. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Complete original section order**: Hero → six pillars → course inclusions → CGM → Julie bonus → pricing → syllabus → teachers → institution → press/journal → mechanism → course differences → FAQ → closing enrollment. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Floater remains an enrollment control**: It links to `#offer`, with desktop top-right and mobile bottom placement. The correction restores visibility rather than adding scroll/pricing-based hiding behavior. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Comparison view preserves customer context**: The review shows one Standard/VIP pair per option, side by side rather than vertically separating the cards on a phone. Large headings spell out introductory payment, four remaining payments, totals and difference. “More than Blueprint” is excluded from the customer card, not from explicit internal comparison headings. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Price prominence without misleading commitment**: Omri keeps the introductory number largest but rejects installment/total text so small that $79 appears to be the full price. Repeated typography, CTA-color and luxury-design objections prevent treating the final assistant redesign as accepted. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Contrasting cards within the light direction**: Omri chose Apple-style light, then explicitly rejected matching white cards. The last reported preview has white Standard, deep-navy VIP, different brand-blue CTAs and visible dimensional edges/shadows. That correction does not approve a price variant, generic pill styling or production release. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Preview-only authorization**: Explicit publication permission covers the existing review site only; payments and CRM submissions stay disabled. Reported asset repairs and browser checks are presentation evidence, not completed-payment certification. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Standard approval has a separate production scope**: Omri approved the $755 installment offer and its “Masterclass credit” presentation for `projects/lla-masterclass-attendee-offer`, then authorized pages.dev parity because event follow-ups point there. The preview's VIP comparisons and disabled payment controls are not the production checkout. (original session `25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2`)
- **Advertising is a separate deliverable**: The assistant acknowledged that legacy ad galleries and delivery hubs were not a completed campaign package for the $79/$99 offer. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)
- **Existing-ad-set transition is the requested acquisition direction**: Omri wants to reuse Julie Set 4 with identical targeting, new Blueprint copy/destination and masterclass ads stopped when the event ends. Adding a few ads previously is not proof that replacing every ad preserves learning; the proposed staggered transition and one-hour check are not an executed migration. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **November recovery goal is not an approved media plan**: Omri seeks a further roughly 21-day opportunity and about fifty monthly Blueprint sign-ups at approximately $300 acquisition cost. The assistant's $15,000 plan and predicted warm/cold yields are proposals, not commitments or verified forecasts. Omri describes $79 first month and approximately $199 thereafter in this planning discussion; it does not select a VIP variant or resolve Standard's reviewed installment schedule. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Surfaces

- Public GitHub review: `https://gitteromri-ux.github.io/lla-blueprint-vip-preview/`; pricing-only `/options/` and phone image `/compare/` are separate review views. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/lla-blueprint-vip-preview/commit/70b8dff7df82679feca86359b1c5b4091f7a7c4e))
- Earlier Vercel review: `https://lla-blueprint-89-vip-preview.vercel.app/`; it retains the older $189 VIP installment and is not the current comparison source. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- Maintained commerce system: `projects/lla-course-checkout`, distinct from this review. (original session `3c41987c-693c-466d-97dd-01e8ffcf531b`) (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`)

### See also

- `projects/lla-course-checkout`: production commerce and CRM
- `projects/lla-october-board-update`: separate direct-funnel acquisition strategy
- `projects/lla-julie-overnight-guardrails`: masterclass-only budget authority
- `projects/lla-masterclass-attendee-offer`: approved Standard attendee offer


---

Record: `french-atelier-purchaser-recovery` | knowledge last updated: 2026-10-28T03:24:00+00:00

## French Atelier Purchaser Recovery and Launch Audiences

Omri’s purchaser-recovery effort covers all French Atelier courses/products and the Culture Capsules acquisition launch. A supplied sales workbook enabled a reported 232-identity submission, not 232 verified paid buyers. Reported ad credit belongs to the purchaser and lead lookalikes, not the Francophile interest set; order-level payment reconciliation remains separate. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### How it works

The requested seed is brand-specific purchasers, reconciled as people against orders, payments and cancellation/refund/test flags. Historical leads and marketing contacts supply matching identifiers, not payment proof. Omri rejected unrelated eTeacher buyers substituted to meet audience thresholds. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

- **Exact campaign mapping**: French Atelier v2 account `1358975119724184` has Sales campaign `#116980`/set `#108761`, and `#116939`/sets `#108758`, `#108757`, `#108756`. Existing live lead campaigns `#117510`/`#116981` were left untouched. The prepared sets optimize Website Purchase on dataset `4075596186030950` with seven-day click/one-day view attribution. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Submitted leads are a separate population**: The read-only export returned 6,633 submissions from sixteen forms, 6,628 distinct emails, covering 2026-07-22–2026-10-20. The active 90-day form-submission source is estimated at 3,600–4,300; that is not a census of all CRM/web leads or a count of purchasers. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Workbook units and eligibility matter**: The assistant reports 940 orders, 645 distinct students and 410 with at least one paid/noncancelled order. Matching the 410 yielded 182 unique email identities, 33 ambiguous names and 195 unmatched. After Omri requested the full 645 population, the reported result became 232 uniquely matched identities, 48 ambiguous and 365 unmatched. The expanded population includes people outside the paid/noncancelled filter. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Submitted identities are not verified buyers or platform matches**: The sales workbook reportedly has names/student IDs but no email/phone columns; recovered identifiers come from historical leads/AC. Meta reportedly accepted 232 rows with zero invalids into seed `120251221224670546`, with US 1% lookalike `120251221226160546`. Acceptance does not validate payment eligibility, identity resolution or the final Meta match count. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Recoverable seed is not a 2% audience export**: The 232-data-row `French-Atelier-purchasers.csv` was recovered and successfully shared as `French-Atelier-purchasers-seed-232-lookalike-source.csv`. It contains identifier/match-source columns for upload, not Meta's modeled lookalike membership. The retrieval establishes file delivery, not a new upload, audience activation or fresh platform-state audit. (original session `0c2dee01-dd4c-464e-b989-21af2bcb74d2`)
- **Distinct seed and launch approvals**: Omri approved the seed/lookalike operation separately from the later selected-creative replacement and activation. Excluded set `#108756` and older ads remain paused in the launch report; neither approval grants unrestricted cleanup. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Launch configuration

The selected launch maps `#108761` to purchaser acquisition (“Buyers LLA”), `#108758` to France-interest acquisition (“Francophile”) and `#108757` to lead-lookalike prospecting (“Leads LLA”). These audience labels distinguish sets with confusing shared Ads Manager names. Omri explicitly rejected actual-lead retargeting as the third set's role. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

| Ad set | Recorded role | Authorized daily budget | Launch selected ads |
|---|---|---:|---:|
| `#108761` | Buyers LLA · purchaser 1% | $149 | 5 |
| `#108758` | Francophile interests | $79 | 6 |
| `#108757` | Leads LLA · lead 1% | $169 | 6 |

The $397/day budget total is Omri's explicit 2026-10-26 instruction, with successful API writes/readbacks at 09:42 UTC; the ad counts describe the launch inventory, not a fresh inventory audit. Omri chose purchaser 1% rather than creating a new 1–2% band. Earlier Updating/too-small reports do not establish final audience match counts; failed website-visitor 2% audiences in another account are not purchaser/checkout lookalikes. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **France affinity is one fourteen-interest pool**: Paris, Provence, French Riviera, Palace of Versailles, Culture of France, French language, Louvre, Musée d’Orsay, Impressionism, Metropolitan Museum of Art, Cannes Film Festival, French cuisine, French wine and wine tasting. Emily in Paris and other requested television titles were not verified as selectable and were not added. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Segmented device/income and expansion controls**: The detailed configuration report pairs the interest pool with top-quarter US ZIP-income categories and iPhone/mobile-only delivery, with hard 45+ and Advantage+ OFF. Main uses all devices, purchaser 1% as an Advantage+ suggestion, minimum 25 and suggested 45+; Lead uses all devices, hard 45+ and Advantage+ OFF. The subsequent activation report does not restate these controls. ZIP categories are area-income proxies, not measured personal income. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Exclusions and shared contract**: Recorded exclusions keep purchasers and original submitted leads out of prospecting, with lookalike cross-exclusions in interest/lead sets. Scope is US nationwide, English, all genders, Facebook/Instagram Feed–Reels–Stories, Purchase optimization and seven-day click/one-day view. Main excludes purchaser-list and submitted leads. Account timezone is Asia–Jerusalem; the $8,000 planning ceiling is not established as an enforced cap. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Creative identity and release

- **Selected versions, concepts not inflated formats**: Omri chose the supplied 22 October UGC cuts and banner versions, with instrumental music from the first second and two five-card carousels. The assistant reported 26 banner/carousel music files and 36 paused replacement ads before 17 selected ads were activated. Format variants stay inside a concept rather than counting as distinct creative ideas. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Selection board is not Meta**: The separate `/ad-board/` review reportedly contains 33 concepts, side-by-side formats, per-set checkboxes and copyable allocations. Ticking a box does not edit Meta or authorize excluded `#108756`. The Art and Fashion carousels each contain five cards; caption/Zoom-grid overlap was corrected and text enlarged after a too-small revision. (original session `a7807e3c-c002-4b23-8068-2c53c5b076c2`)
- **Presenter and UGC identities stay distinct**: Caitlin and Stan presenter files were supplied and uploaded; three UGC topic families remain separate. Omri requires large power captions to dominate covers, with speakers visible. Eight revised covers were prepared, not established as applied; frame/hash checks do not certify continuous audiovisual acceptance. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Performance units**: The later report gives approximately $1,186 spend, 305 clicks, 273 landing views, one AddToCart and one $79 Purchase on Set 1 `#108761`, Ad #13 Fashion & Art. Meta-reported credit does not establish settlement or an identified customer order. `projects/french-atelier-capsules-checkout` holds the reproduced payment failure and attribution-test boundaries. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Audience-specific sales**: The October 24–26 report assigns the $79 October 24 Purchase to Buyers `#108761` and the $151 October 25 Purchase to Leads `#108757`; Francophile has zero attributed purchases in that window. This is ad-report attribution, not independent CRM/processor proof. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Consolidation proposal is not authorization**: The assistant proposed keeping four named creatives and reallocating daily budgets to $250/$75/$200 for purchaser/interest/lead sets, totaling $525. Omri requested a clear diagnosis, not approval to execute these moves. The report shows fifteen active placements plus four paused placements with spend, while the launch report has seventeen active ads; these are different snapshots, not a resolved inventory audit. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Evidence boundaries

AC modern and legacy surfaces returned different results for the same Julie buyer identities: authenticated legacy `contact_view` recovered two contacts after v3 returned 404/empty. The French Atelier purchaser set therefore cannot be characterized as deleted from the incomplete modern-API reads; the cause and coverage of the missing records remain unverified. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`) (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`)

The temporary publicly reachable hashed-email file was reported removed, affected deployments deleted and its URL checked as 404. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)

The Capsules hourly read automation `9e4332aa-87fb-4950-a05e-c8c3b2da922b` was paused on Omri's stop instruction. Julie's separate schedules were not paused by that action; the campaign budgets and account state were not changed by stopping the reporter. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### See also

- `projects/french-atelier-culture-capsules`: offer and production checkout
- `projects/french-atelier-website`: full French Atelier scope
- `projects/lla-julie-purchaser-audience`: separate brand seed precedent
- `projects/french-atelier-capsules-checkout`: checkout and conversion evidence


---

Record: `service-performance-evidence-register` | knowledge last updated: 2026-10-27T05:42:00+00:00

## Service Performance Evidence Register

The Service Performance Evidence Register is Omri’s public `gitteromri-ux/lawsuit` repository for documenting alleged ETA, scope, status-accuracy, and compute-waste failures across GiTA Agency engagements (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`) ([recorded evidence](https://github.com/gitteromri-ux/lawsuit)).

### How it works

The repository generates numbered case files, a `NOTICE.md` register, Documentation and Counter views, and a one-tap issue intake that rebuilds the public site (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`) ([recorded evidence](https://github.com/gitteromri-ux/lawsuit)).

- **Evidence strength is explicit**: Claims without accessible agent-side proof remain labeled `ALLEGED`; missing transcripts, billing records, credit totals, refund amounts, and target claim counts must not be invented (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`).
- **Repository state outranks conversational counters**: Concurrent pushes and a failed rebase produced conflicting totals, so the authoritative count and deployment state require direct repository and live-data verification (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`).
- **Tag receipts do not replace the active task**: `#lawsuit`, `#claim`, and `LOG IT` are intended to trigger an immediate truthful filing receipt without pausing, narrowing, or delaying the ongoing assignment (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`).
- **Claim filing requires explicit approval**: Evidence may be prepared, but no claim is submitted merely because an error occurred; current user authorization is a hard precondition (original session `3e8a6838-f72a-4a17-8c7a-a7018d3a2684`).
- **Support demand is separate from legal action**: Omri requested a refund email after repeated broken reading-site handoffs. The send-tool response confirms successful sending to [email redacted for public handover], with four register case files attached. Requested amounts are $350 for the stated new purchase and 2,657 earlier disputed credits; this is a demand, not a verified refund or an adjudicated entitlement. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- **Internal register labels are not court findings**: The register includes Y1-001–Y1-004/CLAIM-0457–0460 and guest-signup Case Y2-001/CLAIM-0461, with a reported generated total of 461. “Official claim” and “PROVEN” are internal receipt labels, not court/arbitration findings. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`) (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- **Legal-research claims require primary sources**: Public-search gaps do not prove that no private cases or user victories exist; case counts and outcomes require docket, arbitration, settlement, or other primary-source evidence before entering the register (original session `7873ebd0-a188-4e44-97a6-40fa2af1e3a1`).

### Support case handling

Omri's service-quality complaints include a production-registration submission during an iPhone screenshot request. The assistant acknowledged that page inspection did not authorize form submission or checkout progression. Omri authorized the refund complaint and follow-ups on the five open threads, rather than delegating complaint filing back to him. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

- **Task-specific credit returns**: Support correspondence confirms 71,349 credits for the monitoring task and 3,039 credits for the October 19 task, totaling 74,388 across those two adjustments. Only 3,039 is the new October 26 posting; 3,039.75 were offered/consumed, leaving 0.75 disputed. These are service credits, not cash, an available-account balance, client payment refunds or settlement of broader demands. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- **Separate claims retain separate decisions**: The four earlier requests concern 2026-07-16's 2,657 credits, the 2026-08-04 complaint, the 2026-09-29 service-quality case and the 2026-10-19 $350 claim. Support asked to verify ownership of `[email redacted for public handover]` because messages came from `[email redacted for public handover]`; an assertion in an outgoing follow-up does not prove support accepted verification. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Historical reimbursement needs ledger reconciliation**: The recovered July task supports Omri's 2,657-credit demand, while support's current lookup reports zero billed/refunded/refundable credits. The separate 10,000-credit compensation demand and wider $350 demand remain open; a partial usage/grant view is not a complete ledger or a waiver. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- **Guest and repair tasks remain separate**: Support reports 4,850.53 credits consumed on guest implementation, with diagnostics awaiting indexing; resulting repair/investigation is a separate review item. CLAIM-0461 documents the hidden promo controls and false usability assurance, not a completed refund. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)
- **Saved follow-through is not executed follow-through**: Automation `959fee2a-9baa-41c0-9800-180a476b4ff5` is saved active for seven daily 12:45 Asia/Jerusalem runs from 2026-10-27 through 2026-11-02. Its readback gives first run 2026-10-27T10:45:00Z. Five existing support threads received follow-ups; specialist routing does not establish a final decision or all scheduled runs. (original session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`)

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/lawsuit` ([recorded evidence](https://github.com/gitteromri-ux/lawsuit))
- Intake test: `https://github.com/gitteromri-ux/lawsuit/issues/1` ([recorded evidence](https://github.com/gitteromri-ux/lawsuit/issues/1))

### See also

- `entities/gita-agency`: engagement owner
- `entities/omri-gitter`: register owner


---

Record: `lla-julie-meta-pilot` | knowledge last updated: 2026-10-27T05:42:00+00:00

## LLA Julie Meta Pilot

LLA Julie Meta Pilot is Omri’s paid-acquisition experiment for Julie Gibson Clark’s standalone live masterclass. It uses purchase optimization, ad-set-specific configuration and separate CRM/Meta reconciliation. His volume/CPP targets are goals, not reported outcomes; a separately approved overnight rule set adds bounded budget authority to the read-only monitoring schedules. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/2a43ebddd1201d780fc23ba7fa2896882c31f048)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f)) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### How it works

The experiment routes existing Julie video ads to the masterclass purchase page. The repository stores campaign snapshots, creative mappings, and rollback records; those snapshots document configuration rather than subsequent commercial performance. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f))

- **Historical targeting is not the maintained configuration**: The earlier Set 01 experiment combined 41 interests AND a buyer-signal group. Later explicit approvals changed Set 03 to interests only; prior snapshots and rejected proposals do not override those approvals. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f)) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Protected attribution interface**: The campaign keeps pixel `1440305917310328`, Purchase optimization, and its golden link/tag contract. Tracking protection is documented separately in `projects/lla-julie-tracking`. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f)) ([recorded evidence](https://github.com/gitteromri-ux/handover-master/blob/main/projects/julie-tracking-freeze/README.md))
- **Thumbnail-only experiment**: Omri selected the “slowest-aging single mom” thumbnail for Ad#12 and Ad#11 without changing their videos, copy, or tags. Its 48-hour window was anchored to the final creative edit, ending 2026-10-03 at 18:32 IDT, not to the earlier targeting change. ([recorded evidence](https://github.com/gitteromri-ux/handover-master/commit/0216c1309a4236b2948073898032277981ace96f))
- **Targeting approval and observed specification differ**: Omri approved men, US/Canada excluding Quebec, age 55–65 in the API, interests without income/Engaged Shoppers narrowing and mobile iOS Reels. The later source inspection reports Set 03 as US-only, age 25–65+, male iOS Reels without income narrowing. That is observed configuration, not proof Omri authorized the intervening geographic/age changes. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Exact IDs separate live and retired sets**: Current Set 02 is `52673824399628`, observed ACTIVE, not the retired paused `52668268711228` at $44. Name matching caused an incorrect paused-set report. ACTIVE is delivery status, not learning completion: the corrected read had only Set 04 out of learning, Set 05 learning-limited at 17, and Sets 01/02/03 learning. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Set 05 uses lowest-cost bidding**: Omri reversed the $250 cost-cap trial after weak delivery; the latest read retains `LOWEST_COST_WITHOUT_CAP` and Men +50%, with Ad#17 receiving spend. Its separate zoom-blue Reels test (`52672212102628`) is paused at about $16 lifetime spend and zero purchases; it is not the similarly named creative in other sets. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Exact, date-scoped budget authority**: Omri's October 26 instruction at 06:58 Israel time raised Set 02 by $100 to $509, Set 04 by $50 to $749, Set 05 by $49 to $398 and Set 01 by $39 to $258, leaving Set 03 at $127. The reported later Set 04/02 increases followed a context-thin “Masterclass” reply, not an equally explicit instruction. Subsequent observed budgets are not blanket execution approval; daily budgets are not enforced spend ceilings. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Applied changes differ from requested targets**: On 2026-10-27, Omri authorized Set 04 +$150, Set 02 −$50 and Set 03 pause. Entity readback confirms Set 03 paused at its retained $77 budget; Set 04 stayed $999 rather than $1,149 and Set 02 $564 rather than $514. Set 01 remained $258 and Set 05 $348, making active configured budgets $2,169. Set 05's dictated increment was ambiguous and not applied; these targets do not override observed state. (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)
- **Bidding and value rules stay set-specific**: The later read lists lowest-cost bidding for active sets, with Set 03 no value rule, Set 01 Women +80%, Set 04 neutral and Set 05 Men +50%. The reporting assistant attributes these intervening edits to other activity; the read is not execution approval. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Strategy is separate from execution**: Omri assigned strategy here and operating execution to another agent. The written handoff uses dry-spend alerts/pauses, CPA adjustments and an 11:00 recommendation table; it is not proof that the operator was installed. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Base schedules and dated execution permissions differ**: Actual wakes verify read-only 05:00 automation `3ea0e774-d083-44d2-99b3-21908108b343`, 13:00 `f5e43d5b-ea00-48fc-be50-acfd8fbbe227` and 16:45 `d0deefb2-7c34-4848-b138-d2657c5c5715`. Their inspected prompts report candidates, not mutations. Omri separately approved the 2026-10-18 conditional budget controls; neither schedule existence nor that dated approval establishes the separate operator’s installation. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Stored overnight controls are a separate authorization**: `projects/lla-julie-overnight-guardrails` contains Omri's exact no-sale decrements, sale-side raises and alerts. Its 2026-10-25 date-bounded automation is saved and has one observed wake; it does not turn the base reports into unrestricted operators. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Meta events are not a settlement ledger**: Daily dashboards contain Meta-attributed events, including entries without logged CRM POSTs. CRM paid orders, unique people, last-click links, attributed events, and processor settlements remain separate measures. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-daily/commit/51211207c2494538f21968d2d66c97f34b128e7c))
- **Ad ID, not shared creative name, identifies last click**: Recovered CRM fields for order `8052695` map ad `52672751173028` to Set 01 (`52668330533628`), Ad#17 Woman Five habits. Identical creative names in other sets do not change that mapping. This establishes a recorded click path, not a settled payment. (original session `59596b49-4843-4756-b08f-17722a531c89`)
- **Delivery evidence overrides a reset narrative**: The 2026-10-17 API check showed Set 04’s last significant edit on 2026-10-05 and no evening reset for Set 05. The assistant’s blanket five-set reset explanation was withdrawn. Launch-to-date gender CPA was comparable, so raw female purchase volume did not establish that male targeting caused the interruption. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **CRM, raw receipts and attributed sales are separate counters**: Four paid CRM orders `8061632`–`8061635` totaled $226: one $79 Set 02 purchase and three $49 Set 04 purchases. Meta initially showed zero, then the 09:47 Israel-time report showed four attributed purchases with the same 1/3 set split. Eight raw Purchase receipts included browser/server copies, not eight sales or certified deduplication; these observations do not establish processor settlement. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Reporting date is part of the metric**: The 2026-10-27 Israel-day snapshot reports four Meta purchases, Set 04×3 and Set 05×1, on $758.74 spend. The separate CRM report lists four paid orders/$226 after midnight and ten/$520 for October 26. Matching headline counts do not establish order-to-ad equivalence, a common cutoff or settlement. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `20d790c3-26c1-4a67-9c35-6c740d5ba5ae`)
- **Short-interval monitoring remains read-only**: The October 26 combined monitor was reported scheduled every fifteen minutes from 08:30 through 15:00 Israel time, with pushes only for sales or checkout issues. Actual wakes provide execution evidence; the schedule does not authorize budget or targeting changes. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Recommendations do not execute themselves**: Scheduled reports flag candidates without acting and explicitly attribute intervening changes to other activity. Neither the earlier proposed Set 01/Set 6 moves nor later observed activation supplies execution approval. The historical hourly-raise table contains inconsistent counts and is not a certified scaling rule. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Learning analysis does not establish causality**: Omri challenged both the historical exit dates and the assertion that learning fixes a CPP range. The assistant withdrew its claim that resets caused Set 05's weaker trend. The before/after daily series and hourly pacing differences do not isolate learning effects, establish a universal ten-day exit rule or guarantee the same CPP after a Blueprint transition. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Learning state has no verified countdown**: The challenged Set 05 response is `FAIL`, seventeen conversions, last significant edit 2026-10-16; Set 04 is `SUCCESS`. The assistant withdrew both its guaranteed “ten days/five purchases” prediction and its later rigid fifty-in-seven-days explanation. Retrieved status fields do not establish a per-set target or scheduled exit time; the exact earlier debate was not fully recovered. (original session `292ed309-b521-461b-a3f4-e8b6438eec24`)
- **Approved purchaser/warm extension**: Omri explicitly launched `projects/lla-julie-purchaser-audience` at $99/day with four exact-source ads. Its lookalike/warm audience is a set-specific exception, not a blanket replacement of the existing sets’ targeting. (original session `2b7e0eda-2e05-48cb-99bd-b0e4daa3c732`)
- **Purchaser reuse has narrow approval**: The existing lookalike was attached to paused Set 03 under Omri’s approval; seed submissions reached 122 distinct identities from 131 paid-order records, with set 6 excluded. The subsequent scheduled delivery read establishes resumed Set 03 activity, not broader authority or a beneficial morning-spend effect. (original session `e5d1fc33-0efd-48b4-bc1a-e197a6661b68`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)

### See also

- `projects/lla-julie-masterclass` · `projects/lla-julie-masterclass-video`: offer and video sources
- `projects/lla-course-checkout`: separate attribution proof layer
- `projects/lla-julie-tracking`: golden attribution interface
- `projects/lla-julie-checkout-incident`: rollback and purchase reconciliation
- `projects/lla-julie-purchaser-audience`: approved lookalike and warm extension
- `projects/lla-julie-overnight-guardrails`: bounded budget rules and alerts


---

Record: `lla-julie-live-qa` | knowledge last updated: 2026-10-27T05:42:00+00:00

## Julie Live Q&A Desk

Julie Live Q&A Desk is Omri's shared moderator-and-presenter workspace for substantive longevity questions during Julie's masterclass. The public GitHub page has ten prepared answers, live draft generation and synchronized editing; the assistant reported two-browser checks, not presenter acceptance or actual event use. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)

### How it works

Courtney selects audience questions and Julie receives large, clear speaking bullets in a modest, foundations-first voice. The brief concerns sleep, sugar, nutrition, movement and related longevity questions, not course-signup FAQs. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)

- **Prepared and live answers differ**: Ten deck-specific questions have five bullets each, targeting ninety seconds. Added questions are numbered from eleven onward and generate roughly one-minute drafts, marked for review before speaking. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Shared editing and presenter view**: Questions, answers and review status synchronize across browsers. Julie's large-text view includes a speaking timer and next-question control. The assistant reports testing generation, edits and synchronization in two browser sessions and removing test questions. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Persistent backend**: The frontend is `https://gitteromri-ux.github.io/julie-live-qa/`; the backend is `https://julie-live-qa-api.gitter-omri.workers.dev`. Topic-filtered sources keep healthy-aging guidance as the default and reserve menopause/supplement references for relevant questions. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Shared state and generation are separate**: Cloudflare Durable Object SQLite persists the shared workspace; Workers AI Llama 3.3 70B generates draft answers. The backend receipt reports five bullets/125 words, two-client persistence, patching and deletion of the test row back to ten questions. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Retry payload isolation**: The observed AI binding mutated message contents into arrays; reusing them produced schema error `5006` (“array not in string”). Generation clones messages before each `AI.run` and parses either object or string responses, rather than treating an object response as text. Successful answer generation followed these fixes; it is not evidence that generated advice was approved. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)

### See also

- `projects/lla-julie-live-operations`: production and moderator sequence
- `projects/lla-julie-masterclass-deck`: teaching source and themes


---

Record: `lla-julie-live-operations` | knowledge last updated: 2026-10-27T05:42:00+00:00

## Julie Masterclass Live Operations

Julie Masterclass Live Operations is Omri's production guide for running the live Julie event across presenters, screens, microphones, scripts and transitions. It replaces a Courtney-only moderator framing with a team-facing chronological run-through while preserving the original scripts. Omri reported a poor rehearsal; the revised document was reported as twelve pages with thirteen checked script-jump/return links, but final acceptance is not established. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`)

### How it works

The guide combines a short, polished overview of roughly two-thirds of a page with a continuous full-event run-through. Each step identifies what is on screen, who speaks or acts, microphone state, the relevant script and the next cue. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)

- **Separate working document**: The original document `1mgKBuGiEYH6y44h2F8Nqh4n7S8h_fn2n` and its scripts remain unchanged. The revised [working guide](https://docs.google.com/document/d/1okZ8sB08kr3TEpeWqU5bIuMbttFWow49c6XI6cotsU8/edit) carries production organization without rewriting approved speech. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **Plain chronological cues**: Large readable cues and direct script navigation replace an invented management framework and unexplained T+ codes. The document is for the whole production team, not instructions addressed only to Courtney. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **Named teaching version governs the screens**: Julie opens without slides and returns large after teaching. The guide's original 21-slide sequence differs from the later separately corrected V45; final presenter playback needs reconciliation rather than assuming every deck shares that count. A course bridge precedes Courtney's priced offer. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)
- **Recording is automatic**: Omri explicitly removed Courtney's recording-start/check/management tasks. Automatic capture is separate from the promised recording-access and delivery obligations. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **Attendee chat has an exact destination**: Courtney's course-link cue uses `https://www.longevitylifeacademy.com/blueprint-attendees-7q4x/?code=JULIE249`, with `JULIE249` or `MASTERCLASS-VIP` and “Exclusive coupon for masterclass attendees only.” Her spoken script remains unchanged; link insertion does not certify course payment. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`)
- **VIP transition is private**: The supplied main and VIP Zoom links are distinct. The VIP two-sentence WhatsApp handoff uses the supplied VIP link and name/email registration. Direct links do not log LMS attendance and must not be published openly; opening them before class can start the meeting/recording. Actual meeting entry was intentionally not used as a link test. (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`)
- **Live question workspace**: `projects/lla-julie-live-qa` provides ten prepared longevity answers, shared audience-question drafting and a large-text Julie view, separate from the static script/runbook. (original session `75ba57bc-daf0-43bb-a75f-08dbcc6f23b2`)
- **Audit separates mechanics from unresolved promises**: The earlier read-only review found a 16-versus-21-slide mismatch, inconsistent opening cues, missing links, conflicting benefit arithmetic and redemption deadlines. A document-link check does not resolve the final clock schedule, course visual, offer wording or presenter acceptance. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`)

### See also

- `projects/lla-julie-masterclass`: event and presenter ownership
- `projects/lla-julie-masterclass-deck`: actual teaching sequence
- `projects/lla-masterclass-attendee-offer`: separate attendee purchase surface
- `projects/lla-julie-live-qa`: shared audience-question workspace


---

Record: `lla-julie-closing-slide` | knowledge last updated: 2026-10-27T05:42:00+00:00

## Julie Fork-in-the-Road Closing Slide

Omri's closing slide turns Julie's teaching into a clear choice between no change and taking action, with the Longevity Blueprint course as the dominant practical step. It is published separately as the Julie review's twenty-second/final slide; repeated revisions are not final design acceptance. The latest trajectory-only request for natural lighting and smaller, spaced type has no completed publication result. (original session `59567e86-3c35-48de-83af-fed43792d9db`)

### How it works

The graphic must show a literal foreground fork leading distinctly left and right, with actions integrated into a premium physical scene rather than crowded over a background. The action order nearest-to-farthest is Blueprint → watch sugar/CGM → start moving → protect sleep. (original session `59567e86-3c35-48de-83af-fed43792d9db`)

- **Course wording is exact**: “Building your guided protocol in 18 weeks with Longevity Life Academy.” Blueprint should look like LLA live cohort learning, with participant Zoom imagery rather than Julie or a generic textbook; laptop faces the viewer and an upright branded protocol stands beside it without blocking the scene. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- **Recognizable longevity objects**: CGM patch/phone for sugar, movement equipment and unmistakable pillow/bedding for sleep. The user rejected the ambiguous sleep object. Graphic and text hierarchy must make the course the foreground focal point. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- **Dark setting, restrained light**: Omri retained dark navy rather than a white/daylight backdrop and prohibited yellow type. The latest request softens artificial blue-neon glow into natural light while keeping the right action lane visible; text should be smaller, more elegant and more spaced. This request supersedes the earlier maximum-neon interpretation, without proving a finished revision. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- **Authentic branding and exact type**: Use the original LLA website logo with readable eTeacher line and actual deck fonts. Playfair Display and Inter source assets were identified; a numeric font weight or successful render is not user design approval. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- **Other slides protected**: This closer's revisions target only the final Julie-review slide and preserve the preceding twenty-one. V45's exact-image append is a separate presentation scope. (original session `59567e86-3c35-48de-83af-fed43792d9db`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)

### Surfaces

- Julie-review closer: `https://gitteromri-ux.github.io/lla-masterclass-syllabus/slide-canvas/julie/#s22`; the last reported published revision uses `?v=7d61275#s22`. (original session `59567e86-3c35-48de-83af-fed43792d9db`)
- Combined archive: `/slide-canvas/closing-slide-handover/` on the same site, with versions newest first, full-size views, PowerPoint downloads, references, source files and Claude handover. Separate `all-prompts.html` was reported to contain forty-eight verbatim prompts. Initial archive PPTX files preserve imagery, not editable text. (original session `59567e86-3c35-48de-83af-fed43792d9db`)

### See also

- `projects/lla-julie-masterclass-deck`: protected teaching versions
- `projects/lla-julie-live-operations`: course bridge and close


---

Record: `french-atelier-weekly-reporting` | knowledge last updated: 2026-10-27T05:42:00+00:00

## French Atelier Weekly Reporting

French Atelier Weekly Reporting is Omri's recurring Monday update of the French Atelier workbook for Gal. It separates language-course performance from Culture Capsules ecommerce, preserves spend inputs for Omri, and carries corrected counts through dependent formulas. Saved row-90 revenue, price and new-revenue formulas have browser readbacks; delivery to Gal is not established. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)

### How it works

The source workbook is shared through [OneDrive](https://onedrive.live.com/:x:/g/personal/7BAD1872FB416A16/IQBTK3P1OgMzRamleuVzj_FdAfDl5vx8_qhYD8ALO30Gjdo). The October 19–25 reporting period occupies row 90. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)

- **Language courses exclude Capsules**: Omri ordered three acquisitions, four new registrations and $1,380 removed from this period's language-course totals. Capsules ecommerce belongs outside this reporting population, not in a blended conversion result. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **User-corrected counts govern the calculation**: The final inputs are 821 leads, 237 contacted, 19 new registrations, 22 database registrations, 41 total registrations and 17 acquisitions. The earlier 234-contact figure was corrected. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **Dependent formulas move together**: Those inputs imply 28.87% contacted/leads, 7.17% acquisitions/contacted, 8.02% new registrations/contacted and 17.30% total registrations/contacted. Registration/contact rates are recorded in the cell note because the template lacks dedicated columns. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **Price uses all course registrations**: N90 subtracts $1,380 once from contract revenue, displaying $40,272.39. O90 divides by all 41 course registrations, displaying $982.25; U90 multiplies that unrounded price by 19 new registrations, displaying $18,662.82. A $40k total includes database registrations and is not the new-sales revenue figure. Source trajectory records the saved cell/formula readbacks. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **Existing model gaps remain explicit**: Fully weighted CPA and profit cells R90/S90 retain the template's “x” values. Populated-row arithmetic checks do not supply those missing model inputs or establish the client handoff. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)
- **Spend stays user-owned**: Omri fills the marketing-spend inputs. The requested correction leaves those fields untouched rather than inventing replacement values. (original session `cf7b1560-aab3-49e3-96e0-928fa9d87188`)

### See also

- `projects/french-atelier-performance-diagnosis`: related call-center comparison
- `projects/french-atelier-culture-capsules`: excluded ecommerce product


---

Record: `french-atelier-capsules-checkout` | knowledge last updated: 2026-10-27T05:42:00+00:00

## French Atelier Capsules Checkout and Attribution

Omri's Culture Capsules checkout connects French Atelier package selection, eTeacher enrollment, Airwallex payment and Meta dataset `4075596186030950`. The authorized bundle repair now preserves student identity across quote changes and assigns extra-course orders; production assignment responses and seat-count changes support repair of two missing courses. Residual duplicate records, learner access and a complete new payment-to-attribution run remain unverified. Sales stay open. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)

### How it works

The paid primary order carries the package schedule: $99/$178/$189 due now for one/two/three capsules, each paid three times. The site uses a separate browser Pixel/CAPI path from ActiveCampaign cart recovery. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

- **Raw attribution survives the handoff**: `fa-attribution.js` feeds the CRM query and preserves the campaign/ad-group and Meta click parameters across payment and return visits. Saved screen-one answers supply first/last name, state and country for checkout events. The Golden comparison covers 22 ad parameters; implementation is not downstream credit. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/5ec96a2dbb6098aa97305d90ef1736ad22215b11)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/8a8a3e61d2a8197443223819a34503ea21507692))
- **Order-bound Purchase identity**: Buyer details are captured before order IDs clear; Golden-derived fbp, anonymous visitor ID, known-contact handling and early Purchase timing are ported into French tracking. Purchase fires on successful payment before the CRM report; an absent CRM response must not erase the paid event. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/16d118e40be45231a53b56a6aa9e1becd5a22742)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/eedf9aeae8863e284bf5dea0317db59b61bcd364))
- **Golden commerce event placement**: AddToCart fires after the CRM order is created on `enroll-checkout.html`, with `fa_atc_<orderid>`, followed by InitiateCheckout with `fa_ic_<orderid>`. Meta Lead is removed while contact creation remains. This payment-page placement avoids losing the browser event during the offer-page navigation; the old path produced `net::ERR_ABORTED` in a captured test. Cached order reuse remains buyer-bound. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/a854bccc69f6e58a3815b16990be87036e99dc2b)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/bfd7b557b7bfd13c9b9a9d96b152e4b3fef9bcb6))
- **One buyer identity and real entitlement**: The agreement requires one student, every purchased capsule actually assigned and accessible, and no duplicate unassigned records. Omri rejected the reported failure for `[email redacted for public handover]`, naming students `11682493`, `11682494` and `11682495`; order IDs alone do not establish enrollment. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Implemented multi-order mechanism**: Source creates one charged primary order plus extra course orders with `StudentId` and `DiscountPercent:100`. The repair reuses the verified buyer's StudentId when promo/package changes create a new quote, then posts each extra's `StudentID`, `OrderID` and class `SecondaryCourseID` through `Students/ProfileInfo`. One paid plus two $0 orders is not a demonstrated native single-order `BundleMainOrderID` relationship or acceptance of that record shape. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/83b3ddf1651829dbeee4597ee752fef480b1010a)) (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Attempt-before-write safeguard**: The write-guard patch persists an attempted flag before each extra CRM write, suppresses repeats/errors and automatic retries after failures/timeouts, and records student mismatches. Existing-record fallback no longer creates a second lead; completion UI calls extra orders pending because creation does not prove assignment. The patch explicitly keeps sales open. ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/3e7767bed72aa6bcfdc8146cf866e683e011fdc6))
- **Assignment has its own response contract**: Relay routes `/api/checkout/assign` and `/api/checkout/assign/read` forward assignment and readback. CRM success is HTTP 204; the Worker normalizes it to JSON HTTP 200 with `status:204`, avoiding an invalid body-bearing 204 response. The original wrapper raised HTTP 500 after the upstream write had already succeeded. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Course identifiers and test boundary**: Fashion & Art is `267`, Gastronomy & Wine `270`, Cinema & Music `269`. Prior student `11674900`/orders `8054360`–`8054362` were cited as test proof, but the assistant's reinspection acknowledges the check verified student/order IDs rather than assignment/access. The two-capsule attachment used a direct staging request after captcha, not a completed two-capsule browser payment. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Class IDs differ from product IDs**: Configured classes are Fashion & Art `170581`, Gastronomy & Wine `170256` and Cinema & Music `170258`. The corresponding reported start dates are 2026-12-06, 2026-12-06 and 2027-01-10; learner access and the authoritative Cinema schedule still require separate confirmation. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Separate recovery dependency**: `/api/ac/event` returned `field_missing` for `FA_checkout_events`; the required values are `FA_Abandoned_Cart_Name_Details`, `FA_Abandoned_Cart_Course_Details` and `FA_Abandoned_Cart_No_Payment`. `/api/meta/capi` and native Pixel delivery continued in those runs. This demonstrates path separation, not working recovery emails. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### Evidence boundaries

- **Production repair evidence**: Student `11682495` has paid order `8061644` and extras `8061645`/`8061646`. Assignment calls moved Gastronomy seats 3→4 and Cinema seats 1→2; their available-class readbacks became empty like the paid assigned control. Reassigning Gastronomy returned upstream 204 without another seat. Duplicate students `11682493`/`11682494` remain; these responses are not LMS login/access proof. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Staging identity and fulfillment evidence**: Student `11680716` was retained across $189 order `8061154` and discounted $151 order `8061155`; extras `8061156`/`8061157` were assigned and a second fulfillment run created nothing new. Airwallex demo card confirmation returned HTTP 500, so the fulfillment function was invoked separately from a completed card transaction. Tracking-file byte comparisons do not certify a new production Purchase pair or ad credit. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)
- **Live unpaid package captures**: Golden-release QA orders `8060842`/`8060843`/`8060845` reportedly delivered browser/server AddToCart and InitiateCheckout at $189/$178/$99 with matched IDs and ready card forms. They are QA orders, not customer conversions; matching IDs and receipt totals do not verify Meta's dedup counters. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Purchase sandbox scope**: Order `8054375` completed a $189 sandbox card flow and received HTTP 200/`events_received=1` for server AddToCart, InitiateCheckout and Purchase under TEST24680. The browser-local test swapped staging/test-mode precedence because unmodified staging disables tracking. No real charge, production Purchase, browser/server Purchase deduplication or ad credit was established by this run. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Ad credit is a separate outcome**: The later campaign report lists one AddToCart and one $79 Purchase on purchaser Set 1 `#108761`, Ad #13 Fashion & Art. This is a reported Ads Manager result, not a linked CRM order, settled charge or browser/server deduplication audit. Testbirds and Ubertesters outreach is not a completed tester run. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Further purchase report does not close fulfillment**: The report also lists a $151 Purchase on lead-lookalike `#108757`, with a CRM payment acknowledgment and extra order calls. It does not identify those orders' course assignments or establish which bundle was bought; the assistant's amount-based two-capsule inference is not a verified CRM record. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Discounted-order failure is reproduced**: Live QA on Fashion & Art and Gastronomy & Wine shows CAPSULE20's $79 quote followed by an advisor-payment-link fallback without card fields. Order `8061103` sends `FirstPayment:79`, `NumberOfPayments:2`, `LeftToPay:158`; `/api/checkout/details` returns `OrderId:-1`, `PaymentID:-1`, `AmountToCharge:null`. The un-discounted comparison loads a $99 card form. The captured failure does not establish a sole root cause or invalidate every prior $79 purchase. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Diagnosis is not a released fix**: The payment investigation ends with an authorization request for more production price probes and hiding CAPSULE20. The direct three-order probe was blocked before execution; no response approving either action or completed fix is present. Existing diagnostic orders `8061102`/`8061103` remain distinct from that blocked probe. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Mobile entry tests have different evidentiary scope**: Direct-URL iPhone emulation with a test fbclid is not an ad click. The subsequent Ad Library Sign Up → `l.facebook.com` walkthrough starts in Meta but loses paid-feed attribution parameters. Neither establishes a real-device paid-feed Purchase test. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Independent checker scope**: AxiTrace's reported 75/100 scan covered the homepage, not Capsules; its Capsules scan was blocked. Taglert account setup was reported complete, but no connected Meta report is established. The assistant explicitly conceded that Taglert does not create purchases or ad-set credit. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Telemetry totals include QA**: Live tests appear in hourly Pixel totals. Browser/server copies and offer-view events are not counts of unique ad visitors; one welcome-page visit remained unidentified. These reports do not prove that every real ad click reached the offer or that nobody reached checkout. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Internal-test correlation is not a customer ledger**: The assistant linked the 2026-10-26 browser/server Purchase pair to `[email redacted for public handover]` by timing and prior repair context. No independent event/order reconciliation establishes buyer identity, refund completion or absence of all customer sales. Live internal-card tests can emit production events; missing fbclid on a copied URL does not rule out earlier click cookies. (original session `e431dbfa-a68c-4adc-b8af-701f0309f281`)
- **Temporary TEST offer**: Source config adds a manual 99% test promotion with an absolute expiry. The reported three-capsule quote is $2 now plus two $2 installments, $6 total, not $2 total. Source expiry is not a payment/refund/cleanup receipt. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/7ac29ef221d04bf2202e68790f323716c10d0256))

### See also

- `projects/french-atelier-culture-capsules`: offer and campaign gate
- `projects/french-atelier-purchaser-recovery`: audiences and paid launch
- `projects/french-atelier-website`: production source and relay


---

Record: `lla-organic-community-blitz` | knowledge last updated: 2026-10-26T08:44:00+00:00

## LLA Organic Community Blitz

LLA Organic Community Blitz is Longevity Life Academy’s organic Facebook-group distribution system for the direct-ecommerce course, with live reach separated from administrator-gated expansion (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).

### How it works

The project pairs audience-matched group publishing from real participant accounts with an internal noindex status surface. It distinguishes posts that are actually live from membership requests and admin approvals that remain pending (original session `f5b22caa-36a3-4364-85a2-a5ee936a0bc6`).

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

The French Atelier website is Omri’s GitHub Pages-hosted production site for `www.frenchatelierlive.com`, backed by the `gitteromri-ux/french-atelier` repo ([recorded evidence](https://github.com/gitteromri-ux/french-atelier)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/29dea6cdd751cf3d2b16d69a61841b0c53ee0520)).

### How it works

The site is a French e-learning marketing website with course pages, lead forms, CEO-requested content revisions, Mapstr-backed location imagery, and a custom GitHub Pages domain ([recorded evidence](https://github.com/gitteromri-ux/french-atelier)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/29dea6cdd751cf3d2b16d69a61841b0c53ee0520)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/d4cb1b77c24482549b6acef8c3efd13526897458)). Work has focused on CEO checklist edits, legal/compliance phrasing, navigation, imagery authenticity, mobile performance, and production-readiness without changing approved copy ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/d4cb1b77c24482549b6acef8c3efd13526897458)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/8b181f5da6f70c44788ec59bd2d706fa06a0b8e4)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/56970c8c9c0e661462ed892fa6da34341826b6de)) (original session `e9859920-2f4e-43da-9eb2-b4a7e2e80c6c`).

- **Mapstr imagery as authentic map source**: The 2026-07-15 update replaced 42 map pin photos with photos pulled from the CEO’s Mapstr map and kept unmatched pins on existing Wikimedia imagery ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/d4cb1b77c24482549b6acef8c3efd13526897458)).
- **Gastronomy pillar correction**: The homepage/culture gastronomy video was swapped to `wine-tasting.mp4` to avoid the steaming-wine illusion noted in CEO feedback ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/8b181f5da6f70c44788ec59bd2d706fa06a0b8e4)).
- **Sorbonne language follows the CEO-edit baseline**: Live Sorbonne-bearing copy is byte-identical to the historical CEO-edit commit and retains the independence disclaimer. The original CEO document itself was not retrievable during the latest audit, so the commit is the available authoritative baseline ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/56970c8c9c0e661462ed892fa6da34341826b6de)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/b5d4e71ad21f6496ac82fb69aa1abac670f507a2)) (original session `bff97d1b-8e08-4e46-9e2e-14fcd2f237c4`).
- **CRM lead capture**: French Atelier lead forms route through eTeacher CRM/ProductID 25 with phone/country fields and a CORS relay path added during production hardening ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/7552aa1bb0c1c9df63021e72d5b318d1f63800c6)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/a00008a06b4e7e22341491dec37f64612a9680d0)).
- **Asset and loading performance pass**: The production repo was reduced from 528MB to 105MB by converting PNGs to WebP, recompressing JPGs, transcoding videos, removing 207MB of unused assets, lazy-loading below-fold images, and deferring MapLibre loading (original session `e9859920-2f4e-43da-9eb2-b4a7e2e80c6c`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/ec58d90)).
- **Mobile Mapstr and MapLibre repair**: Mobile marker taps pin the photo card at the top and render the lesson panel as a bottom sheet. The production map library is pinned to MapLibre GL v4.7.1 because the previous `@latest` distribution path resolved to a missing asset ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/b4cebef)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/a240b28ed980ae0b66b1b0e6bebc09c699d86532)).
- **Video-ad opener rule**: French Atelier opening lines should be short, concrete, declarative, non-accusatory, and locked to the individual script’s theme. Each line must hand off literally into the approved script without rewriting what follows (original session `81aa0c15-006a-4d6b-8cae-e124ee2cb154`).
- **Approved imagery across internal pages**: All internal-page imagery should come from the approved new asset family, not copied `live.frenchatelier.com` folders or low-resolution thumbnails. The production audit covered 33 pages and corrected course, blog, FAQ, How It Works, culture, and course-index imagery, plus counters and testimonial contrast (original session `28d38197-ec24-4069-bdb5-a0c2e3716ca7`).
- **Separate lifecycle-message tracks**: Acquisition email/landing-page work lives in `french-atelier-acq-drip`, while the three-message retention and three-message acquisition WhatsApp series lives in `french-atelier-wa-ret-acq`; they are separate delivery surfaces and should not be merged (original session `34a6e1ef-d550-4f71-b1b8-3e8f75d0806a`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-acq-drip)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-wa-ret-acq)).
- **Production identity and copy constraints**: New campaign work uses `French Atelier by Acadomia` and `frenchatelierlive.com`, not the retired `livefrenchatelier.com` reference. The WhatsApp bodies are exactly 150 words, include `Header Text:` and `{{BODY_1}}`, use emoji, and exclude STOP language and AI-style punctuation (original session `34a6e1ef-d550-4f71-b1b8-3e8f75d0806a`).
- **Angoulême factual phrasing**: The comics-festival page says “each January, a tradition born in 1974,” avoiding the inaccurate claim that the event ran every January without exception (original session `34a6e1ef-d550-4f71-b1b8-3e8f75d0806a`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-wa-ret-acq)).
- **Site-wide mobile floor and swipe rails**: The 35-page production surface applies a readable mobile type floor and horizontal swipe rails to card families. A stricter pass caught four card groups missed by the first size-based scan, so automated “zero flag” output is not a substitute for visual fold review ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/89301e83912b062042a36b3f7c3d2cd21de676d0)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/57f8bf716a46c3d86dfc38b922c36d6acb7f496b)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/796cedef7980231d9dff7146365647547cd71e59)) (original session `245bbea7-9eda-424c-bc18-852c2416de41`).
- **Canonical production domain**: Privacy, sitemap, and robots surfaces use `frenchatelierlive.com`; the retired `livefrenchatelier.com` spelling is removed from production metadata ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/fea06fdcab6afc76abb897d23b135030c131d0e5)).
- **Homepage teacher portraits preserve real identity pixels**: The language-course homepage/faculty set uses real source pixels, faithful upscaling and consistent eye-line/head-size framing, and was reduced to Caitlin, Carmèle, Charline, Philippe and Shanice. The separately approved Capsules teacher fold uses its own AI-assisted portrait assets. (original session `bff97d1b-8e08-4e46-9e2e-14fcd2f237c4`) (original session `245bbea7-9eda-424c-bc18-852c2416de41`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier)) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)
- **Map locations and map imagery are separate authorities**: The 72 dictated places, pin coordinates, and ordering remain fixed while the matching photos can be replaced with more representative real imagery and explicit credits (original session `bff97d1b-8e08-4e46-9e2e-14fcd2f237c4`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier)).
- **Julien media placements are unique by fold**: The homepage and Julien hero retain the lip-synced audio intro, while internal folds use distinct silent loops; the watermarked Kling 2.1 upload is excluded (original session `bff97d1b-8e08-4e46-9e2e-14fcd2f237c4`).
- **Course PDFs are hosted but not surfaced**: Seven uploaded syllabus PDFs exist under `/downloads/`, but course pages do not link to them; hosted source material therefore does not prove visitor access or copy parity (original session `bff97d1b-8e08-4e46-9e2e-14fcd2f237c4`).
- **Marketing lead capture and ecommerce are distinct**: The established marketing-page `Enroll Now` CTAs share one on-page lead form and CRM binding. Dedicated full-course and Capsules ecommerce pages use a separate order/payment engine rather than replacing that lead path. ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/11b74ac)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/4aea60bd32c5004ab09fa1d51ed8c657e7b8b501))
- **Qualification fields are required**: Lead submission requires both French level and intended start timing so the captured record is usable for follow-up ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/56062e8)).
- **Privacy and cache behavior are production concerns**: The repository carries a dedicated privacy page and explicit cache-busting/no-store behavior so legal changes and release fixes reach the live surface predictably ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/21f787c)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/d0714dd)).
- **Dedicated ecommerce surfaces**: Capsules production is `/culture-capsules`, separate from earlier staging/review sites. Full-course checkout remains `french-course-enroll.html` with $89 today plus four $199 payments, $885 total; it is not the Capsules three-payment offer. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/4aea60bd32c5004ab09fa1d51ed8c657e7b8b501)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier/commit/9e189819dc399019d536e4373deb7030f335a4d7))
- **Purchaser recovery spans the brand**: Omri’s `projects/french-atelier-purchaser-recovery` covers language courses and every French Atelier product, not just Capsules. A supplied sales workbook supports reported name matching and a 232-identity submission, not a complete order/payment reconciliation. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)
- **Campaign-gated Capsules, open language courses**: New unqualified Capsules visits show a neutral welcome; approved ad traffic and returning qualified visitors retain the offer. This client-side filter is not authentication and leaves full French courses open. `projects/french-atelier-culture-capsules` holds access rules; `projects/french-atelier-capsules-checkout` holds payment, bundle and Golden-derived tracking. The CEO QA/staging link does not take real payments. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

### See also

- `entities/omri-gitter`: project owner
- `concepts/github-pages-delivery`: hosting pattern
- `projects/french-atelier-social-kickstart`: organic social plan
- `projects/french-atelier-culture-capsules`: culture-learning production ecommerce
- `projects/french-atelier-purchaser-recovery`: brand-wide buyers and audiences
- `projects/french-atelier-capsules-checkout`: ecommerce entitlement and attribution


---

Record: `lla-october-board-update` | knowledge last updated: 2026-10-22T23:27:00+00:00

## LLA October Board Update

LLA October Board Update is Omri's eight-slide board/CEO presentation, with two audience slides before the six-slide acquisition strategy. The same circulated surface provides the browser deck, PowerPoint and PDF; the new audience slides are image-based rather than editable charts. The assistant reports sending the updated link to Keren Ziv, not recipient acceptance. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/a5e4ff4f9c1674eea09981bee6cedde154b96bb6))

### How it works

The presentation explains three distinct efforts rather than treating masterclass upsell as Blueprint’s only sales funnel. The source is `gitteromri-ux/julie-ceo-launch-report`; it is not Julie’s separate speaker/teaching deck. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/a68e7f3104ef7314e293d9625d659bd0fe581c2c))

- **Masterclass as bottom-up acquisition**: The accessible paid class builds a community of buyers who can later convert to the full Blueprint course. The targets are 350 registrations for 2026-10-27 and 350 for 2026-11-14, totaling 700 by 2026-11-14, with one Blueprint sale per 10–12 masterclass buyers through sales follow-up or direct checkout. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Actuals are not targets**: Omri supplied 113 signups for immediate board use on 2026-10-18. This is a user-supplied board figure, not a fresh CRM reconciliation. The requested scorecard also includes actual paid totals, VIP totals and per-date progress; the supplied transcript does not establish a reconciled VIP total. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Separate direct-course relaunch**: Blueprint’s relaunch brief calls for a revised landing page/promotion informed by masterclass learnings and a planned VIP tier. Its offer mechanics belong to `projects/lla-course-checkout`, not to the masterclass’s $79 Q&A tier. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Hybrid lead generation**: Maintain low traditional lead volume while prioritizing ecommerce and routing abandoned-cart prospects to sales, rather than replacing direct purchase with a lead-only model. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Audience opens, strategy follows**: Slides 1–2 present an executive audience summary and four comparative charts; the previous six slides are 3–8. The original strategy excludes extra budget/CPP cards. Removing “Reported by Omri” from board-facing copy does not verify the number. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/a5e4ff4f9c1674eea09981bee6cedde154b96bb6))
- **Separate products and denominators**: The reported audience data covers 5,979 Blueprint leads and 141 Meta-attributed masterclass purchases, not a complete profile of Blueprint CRM buyers. Earlier draft totals were 142 masterclass/three online Blueprint purchases; later drafts used 141/four. Those cutoffs are not a reconciled order ledger. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Observed distribution, not causes**: Reported shares are 73% women/69% aged 55+ among Blueprint leads and 70% women/84% aged 55+ among masterclass purchases. Device shares are 75%/91% iPhone. Targeted income-ZIP categories are not measured buyer income; persona motives and health conditions are assistant hypotheses, not Meta observations. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **State chart uses unlike metrics**: Blueprint state bars describe leads, while masterclass state bars use ad clicks, not purchases. The chart cannot establish masterclass purchaser geography or political preference; targeted-state selection also affects observed lead geography. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **No compulsory funnel claim**: Omri ordered “They enter through the Masterclass; the Blueprint course is the destination” removed at the circulated link, without another email. The paid-community strategy remains one acquisition route, not a description of every buyer's path. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)
- **Same-link handoff**: The refreshed page is `https://gitteromri-ux.github.io/julie-ceo-launch-report/board-deck-2026-10-06/?v=a5e4ff4&fresh=20261022-aud`. The assistant reports eight-slide PPTX/PDF/browser parity and a reply to `[email redacted for public handover]`; the source commit corroborates the eight-slide assembly, not commercial-number reconciliation. (original session `658b2028-3543-446e-8b94-2c5db8006a50`) ([recorded evidence](https://github.com/gitteromri-ux/julie-ceo-launch-report/commit/a5e4ff4f9c1674eea09981bee6cedde154b96bb6))

### See also

- `projects/lla-julie-masterclass`: paying-community acquisition model
- `projects/lla-course-checkout`: separate Blueprint VIP relaunch
- `projects/lla-growth-engine`: hybrid recovery and lead model


---

Record: `sokolov-90-lease-renewal` | knowledge last updated: 2026-10-22T05:29:00+00:00

## Sokolov 90 Lease Renewal

Omri is coordinating the Sokolov 90 lease renewal in Herzliya as landlord for 2026–2027. Both tenants and both guarantors were reported signed on the amended eight-page lease with the approved roof-electrical row. Omri’s signature remains the outstanding step in the session evidence. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)

### How it works

The base is the “הסכם שכירות לא מוגנת” draft, compared with the prior signed lease and current tenant correspondence. The stated term is 2026-10-15 through 2027-10-14, with reported rent of ₪6,200 monthly in advance on the 15th and no indexation. The named tenants are אביב פורת and אגת סדון; this does not establish Omri’s residence. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

- **Preserve known-defect protection**: Clause 2.2 distinguishes acknowledged existing defects from tenant-caused damage. Appendix A records localized damp/mold in the left bedroom and kitchen shelving area, stair-ceiling leaks/peeling, kitchen-cabinet peeling and living-room floor defects. Contractor hearsay and the gas-burner item remain excluded; the roof-electrical clause is separately authorized. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`) (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- **Release future liability on tenant replacement**: New clause 9.6 releases tenants and guarantors from future obligations when replacement tenants enter, preserving prior liabilities and the existing landlord-suitability provision in 9.5. Omri rejected extra signing/security conditions added by the assistant. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)
- **Five signatories, separate guaranty pages**: Tenants אביב פורת (`[email redacted for public handover]`) and אגת סדון (`[email redacted for public handover]`) and guarantors יצחק פורת (`[email redacted for public handover]`, page 6) and אילן סדון (`[email redacted for public handover]`, page 7) were reported signed. Omri signs as `[email redacted for public handover]` on page 5; all five signatures are required for completion. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- **Envelope-specific completion**: Replacement envelope `3d9c2b43-cd9a-89e5-8181-14a7cf89334d` is the signing target. The assistant reported resending Omri’s invitation after his request, with a security-confirmation message titled “Do you recognize this document?” His signature is not established by that resend. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- **One exact roof clause**: Omri approved only: “בזמן גשם, הדלקת התאורה החיצונית בגג עלולה לגרום לקצר, בשל תשתית חשמל החשופה למים.” The prior signed appendix was recovered on page 11 with “קצר בחשמל בגג בזמן גשמים”. Other historical appendix items were not authorized for addition. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)
- **Signed-document boundary**: Row 7 must appear inside Appendix A, not just the invitation email. The assistant reported downloading the sent eight-page PDF back from DocuSign and checking row 7 on page 8, with no other contract changes, and voiding the old envelope. The replacement was sent from a new trial account at `[email redacted for public handover]`, not the older Gmail account. (original session `bd4275ad-388c-43a3-a8c0-6bece4637d22`)

### See also

- `entities/omri-gitter`: landlord coordinating the renewal


---

Record: `iching-career-reflection` | knowledge last updated: 2026-10-20T06:23:00+00:00

## I Ching Career and Location Reflection

Omri requested an extensive I Ching reading as personal exploration, with a general interpretation and a separate question-specific interpretation. The questions concern suitable work, entering hospitality and remaining in Israel over the coming years; they do not establish a job change, relocation plan or prediction. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)

### How it works

The requested deliverable is a browser-readable Hebrew analysis drawing on Wilhelm/Baynes and commentary associated with Wang Bi/Lynn and Alfred Huang. Omri asked for full analysis rather than brief conclusions and ultimately supplied three questions in the toss order. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)

- **Separate blind and contextual readings**: One tab retains a general interpretation; the second interprets the same results against the supplied questions. Omri challenged the assistant’s earlier objection to reading without knowing the questions. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- **Questions, not decisions**: The three questions ask what to understand/do to attract suitable work, what potential hospitality holds in coming years, and how appropriate remaining in Israel would be. The assistant’s recommendations and numerical success scales are interpretations, not Omri’s choices or validated forecasts. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- **Source depth remains attributable**: The assistant reported expanding the question-specific reading to twelve sections per question. It had earlier acknowledged that only Wilhelm material was verified and that Lynn/Huang wording was paraphrased from memory; the final reported expansion is not independent scholarly validation. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- **Readable review surface**: The requested design uses larger white/blue type, no yellow/orange and no bold treatment. A Wix-hosted URL was delivered after GitHub/htmlpreview/internal handoffs failed for the user. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)

### Surfaces

- Delivered reading: `https://headless-zgyfbzqmrfg-gitteromri5-140b.wix-site-host.com/`; question-specific tab: `#questions`. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)
- Source repository identified in the session: `gitteromri-ux/iching-reading`. (original session `f3ef654d-0617-422d-b1f3-b1893a2ce623`)


---

Record: `eteacher-monthly-invoicing` | knowledge last updated: 2026-10-20T06:23:00+00:00

## eTeacher Monthly Invoicing

Omri manages separate recurring Morning/Green Invoice tax invoices for eTeacher Group’s French Atelier and Longevity Life Academy work. Billing uses 15th-to-15th service periods, month-end due dates and preview approval before issuance; the October cycle includes verified allocation-number recovery and newly issued documents. (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

### How it works

The invoice client is איטיצאר בע"מ. The two brands share the client but retain separate titles and service rows. September’s source documents are 50036 for French Atelier and 50037 for LLA; the approved next service period is 2026-09-15–2026-10-15, issued 2026-10-19 and due 2026-10-31. (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

- **French Atelier’s approved recurring scope**: “E2E Marketing agency” $11,000 and “Active Campaign CRM (tech/software)” $630, plus 18% VAT. The $8,000 Organic Assets item from the previous cycle is excluded from this cycle, not silently rebilled. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- **LLA’s approved recurring scope**: “E2E Marketing agency Fee” $8,000 plus 18% VAT, with source wording otherwise preserved. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- **Current conversion for the new cycle**: Morning duplication retained the old 2.954 ILS/USD rate; Omri rejected it. Refreshed rows show 3.11 ILS/USD. French Atelier totals ₪36,169.30 before VAT + ₪6,510.47 VAT = ₪42,679.77; LLA totals ₪24,880 + ₪4,478.40 = ₪29,358.40. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- **September allocation recovery**: After Morning’s Tax Authority authorization was renewed, 50036 received 292018463 and 50037 received 292083483. Browser confirmations show successful allocation requests against the existing documents, not replacement invoices. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- **Approved October issuance**: 50038 is French Atelier, ₪42,679.77, allocation 292011586; 50039 is LLA, ₪29,358.40, allocation 292072185. Browser confirmation and the income-list readback establish issued documents. The assistant reported auto-sending to [email redacted for public handover] and [email redacted for public handover]; recipient receipt is not established. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- **Authorization and tax payment are different systems**: Morning’s allocation authorization was shown active after renewal on 2026-10-19, with three-month validity. This is allocation access, not evidence that VAT or other tax returns were filed or paid. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

### Surfaces

- September 50036: `https://app.greeninvoice.co.il/incomes/documents/81e54cae-7177-43f1-93af-6cf7917a3356`. (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- September 50037: `https://app.greeninvoice.co.il/incomes/documents/a84a060a-5bf2-47f1-9fce-b113e011dbd6`. (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`) (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- October 50038: `https://app.greeninvoice.co.il/incomes/documents/aca27508-3cfe-4312-9bc8-f61219149491`. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)
- October 50039: `https://app.greeninvoice.co.il/incomes/documents/8ae354c3-d6e9-45df-8789-d88fec0fcabe`. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

### See also

- `entities/gita-agency`: agency issuing the documents
- `entities/longevity-life-academy`: separately billed client brand


---

Record: `lla-julie-invitation-blast` | knowledge last updated: 2026-10-19T01:21:00+00:00

## Julie School Invitation Emails

Julie School Invitation Emails is Omri’s community-masterclass acquisition handoff for Rosen, IIBS and Longevity audiences. Its original public gallery now includes the approved IIBS Emails v4 tab and community hero destinations. Published GitHub versions do not automatically update ActiveCampaign imports or certify full send coverage. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/6df81d9a9298cbd38a93d20533474560856cb791))

### How it works

The recipient’s actual relationship determines the opening, sender and footer rather than treating every contact as an alumnus. IIBS v4 covers alumni, active students, non-completers and leads, with audience-specific introductions and a shared approved body. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

- **Context before credentials**: Omri selected the softer reference-email direction: explain longevity and the learning opportunity before introducing Julie. The school connection must be credible and respectful to readers unfamiliar with her, not a supposed new partnership or arbitrary name-dropping. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- **Automatic masterclass discount**: The chosen invitation offer is 36% off for 72 hours, applied without an entered code, with participation from $49. Price appears toward the bottom, not as the lead subject. This replaces the cross-product `$249` coupon pitch; it does not establish the value of any underlying VIP Blueprint benefit. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- **No invented pre-public exclusivity**: Omri rejected “held seats before general release” because the masterclass was already public. Limited-seat wording is separate from a claim that the public cannot enroll. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- **School and Academy voices differ**: School versions use their school identity, personalization, and footer; Academy versions introduce LLA as the eTeacher school behind the invitation and explain the prior school contact. The final reported senders are Noa Shalev for Rosen, Sophia Green for IIBS, and Emma for LLA. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- **Reusable production handoff**: Chris and Sandra’s requested handoff combines complete email previews, separate image downloads, copyable text/HTML, correct headers/footers, and ActiveCampaign personalization. Review versions are artifacts for installation, not proof of activation. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`)
- **One circulated URL, hero landing**: The authoritative gallery remains `https://gitteromri-ux.github.io/julie-masterclass-blast/`. All sixteen reported email versions, HTML downloads and plain-text copies point to `/masterclass-72hours/` at the hero, retain UTMs and omit pricing/section anchors. ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/d23be44ce26d9b09973960db0d247cea2c5ef149)) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/49531c6a31b06a6921b9e778ef17e667309086d0))
- **Full US time-zone lines**: 2026-10-27 is 7:00 PM ET / 6:00 PM CT / 5:00 PM MT / 4:00 PM PT; 2026-11-14 is 1:00 PM ET / 12:00 PM CT / 11:00 AM MT / 10:00 AM PT. All variants retain the short “14-day refund*” and later-of-class-start clarification. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **IIBS v4 is approved copy only**: Seven IIBS files cover the four audiences, grouped under `#iibs-v4`. The preheader is “One live hour with Julie Gibson Clark on health that lasts. 36% off for the Institute community.” The strip is “For our community · A live hour on living well, longer.” Each main headline retains “The Longevity Masterclass of the Year”; Julie’s subheadline identifies a single mom aging about 6.5 years per decade, with an educational/results disclaimer. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/gitteromri-ux/julie-masterclass-blast/commit/6df81d9a9298cbd38a93d20533474560856cb791))
- **Scope preserves design and other brands**: The approved IIBS update preserves CSS, fonts, images, buttons, subject lines, personalization, unsubscribe links and earlier link/time/refund corrections. Rosen and Longevity remain unchanged by this IIBS-only revision. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Chris’s import is a separate release**: The copy-paste handoff explains the approved changes after speaking with Elaine and singles out IIBS v4 at `?v=6df81d9-iibs-v4#iibs-v4`. GitHub changes do not propagate to ActiveCampaign; the reviewed record requests confirmation before launch rather than establishing all imports or sends. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)

### See also

- `projects/lla-masterclass-emails`: separate lifecycle email system
- `projects/lla-julie-masterclass`: enrollment offer and destination
- `entities/sandra-kwiecien`: copy and CRM authority
- `projects/lla-julie-community-offer`: separate community offer surface


---

Record: `lla-julie-community-offer` | knowledge last updated: 2026-10-19T01:21:00+00:00

## Julie Community 72-Hour Offer

Julie Community 72-Hour Offer is Omri’s separate masterclass purchase page for school communities and Longevity leads. It presents an automatic discount at the existing public URL and one fixed 72-hour campaign deadline. Published presentation and UI checks do not certify completed payments or source-specific purchase attribution. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/Longevity-Academy/masterclass-72hours/commit/a68b6edaf2e238abf1871171c6c83fb543ec0eaf))

### How it works

The source is `Longevity-Academy/masterclass-72hours`, published at `https://www.longevitylifeacademy.com/masterclass-72hours/`. The paid campaign remains on `Longevity-Academy/julie-masterclass` and `/julie-masterclass/`; the duplication report includes a production-source hash comparison. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)

- **Separate offer, automatic price**: The page advertises 36% off, displaying Standard $49 and VIP $79 against prior prices $77/$124, with no entered code. Rounded display prices are not exact 36% arithmetic. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- **One fixed campaign clock**: The universal window runs from 2026-10-18 17:00 to 2026-10-21 17:00 Israel time, equivalent to 14:00 UTC at both endpoints. Reloads and new visitors share the deadline; expiry stays at zero rather than starting a new window. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) ([recorded evidence](https://github.com/Longevity-Academy/masterclass-72hours/commit/a68b6edaf2e238abf1871171c6c83fb543ec0eaf))
- **Unlisted rather than private**: `noindex`, `nofollow`, `noarchive` and omission from navigation reduce discovery, but anyone with the URL can open the page. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- **Paid order, page and payment time identify the channel**: Existing checkout payloads send `LandingPageURL` and `QueryString`; community attribution requires a paid order originating on `/masterclass-72hours/` after campaign launch. A shared pixel total or retained IIBS campaign label alone cannot identify that sale. Field retention beside the paid order in ActiveCampaign was not verified. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Mobile layout without commerce changes**: The published revision reports hero → What you’ll learn → pricing → About Julie, aligned pricing cards and restored visible controls at the same URL. Omri explicitly excludes checkout, tracking/CAPI and the normal masterclass page from this work. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Design-only handoff protects commerce**: The reported Claude pack combines source, screenshots and protected checkout/Golden CAPI boundaries. It calls for premium mobile and desktop treatment, including 360/390/412 widths, enlarged Android text and a 1440 desktop view. Packaging and reported inspection are not proof of acceptance or a later production port. (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)
- **Read-only UI coverage has limits**: The audit reports 82 interface checks with writes blocked and no CRM orders created. It found an Airwallex setup error, checkout refund text differing from pricing and an error state persisting across plans. No real card, 3DS, wallet or PayPal payment was tested; the setup error alone does not prove payment failure. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Short refund presentation**: Pricing uses “14-day refund*” with “14 days from registration or until your class starts, whichever is later.” The audit still found “within 14 days from registration” in checkout. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`)
- **Checkout recovery is another surface**: The selected pricing-card/strip port and SDK/PayPal repairs belong to `projects/lla-julie-checkout-recovery`, not this clone. That workstream’s authorized release and subsequent production rollback do not establish this community page’s acceptance or commerce certification. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)

### See also

- `projects/lla-julie-masterclass`: separate paid purchase surface
- `projects/lla-julie-invitation-blast`: community invitation messaging
- `projects/lla-julie-tracking`: protected attribution boundary
- `projects/lla-julie-checkout-recovery`: separate payment repair preview


---

Record: `lla-julie-checkout-recovery` | knowledge last updated: 2026-10-19T01:21:00+00:00

## Julie Checkout Recovery Preview

Julie Checkout Recovery Preview is Omri’s repair and presentation workstream for the Julie masterclass purchase page. Its SDK recovery, PayPal guest-card fallback and selected offer designs were authorized for production, then removed by an explicitly requested rollback to the 2026-10-15 production build. The preview and its form-rendering tests are not a certified all-device payment release. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/cf899f2594e7acb209c0bee27acf99c07d234fdb))

### How it works

The approved repository is `Longevity-Academy/julie-fix-preview`, served at `https://www.longevitylifeacademy.com/julie-fix-preview/`. It is distinct from both `/julie-masterclass/` and the community clone `/masterclass-72hours/`. Its device-test link uses `?plan=standard&enroll=1&qa=1&env=staging`; the session’s QA runs use staging/demo payment configuration with Meta mode off. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)

- **Separate approval for production**: Omri initially held release pending Grok’s device retest, then explicitly authorized go-live after relaying a passing forced-block and control report. That approval covers the tested recovery build, not unrestricted future payment or tracking changes. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Recover the SDK, not the attribution chain**: The preview wraps initialization in `Promise.resolve` and retries a missing SDK once by script reinjection. The SDK URL’s query does not pin the served bundle; v2.34.0 and later v2.38.0 were observed. The version observations do not establish a provider-caused outage. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `af49d9a8-c905-408e-915b-9a22adc2934a`)
- **Guest-card access in the fallback**: On SDK failure the preview hides the empty Airwallex mount, reloads PayPal with both its blue button and black “Debit or Credit Card” button, and selects the PayPal tab. The guest-card form is served by PayPal; it is not the primary Airwallex form or proof that Apple Pay works. Plain grey guidance replaces buyer-facing technical codes, and the contradictory wallet hint is hidden while fallback is active. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Order creation and SDK failure are distinct**: The details request precedes the missing-SDK check. A form-load failure therefore does not establish that no order or payment intent was created; staging order-creation latency was also observed separately. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)
- **Tracking baseline is explicit**: The release reports matches for `julie-meta-tracking.js`, `julie-attribution.js` and `julie-payment-safety.js` against the pre-release production files, not identity to the 2026-09-28 frozen tag. The production baseline includes the 2026-10-15 coverage patch. No ActiveCampaign-trigger change was reported, but code-boundary checks do not certify live trigger behavior or Purchase coverage. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Rollback is the production decision**: Omri’s separate “Rollback” instruction restored `a188c6c` through `cf899f2`, removing the recovery/payment-init and design changes from production. The preview remains a comparison surface; production is not serving the final recovery design. (original session `af49d9a8-c905-408e-915b-9a22adc2934a`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/commit/cf899f2594e7acb209c0bee27acf99c07d234fdb))
- **Preview publication also requires approval**: A later phone-CSS candidate was published to the preview without Omri’s approval, then withdrawn. The reported restoration returns `/julie-fix-preview/` to design-round-3 commit `473265f`; the new phone fix remains local and unapproved. That preview restoration is not a production change. (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`)

### Device evidence

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

The plan moves from macro diagnosis to floor-level operating detail, then organizes the management agenda around efficiency, revenue, and brand/digital growth (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`) (original session `44859035-df25-47a4-bd36-f12b628efdb6`).

- **Three operating engines**: Efficiency/productivity, revenue expansion, and brand/digital are presented as one connected management system rather than unrelated initiatives (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`).
- **Learn the operation before restructuring it**: The sequence prioritizes observation, measurement, role clarity, and process repair; cost cuts and dismissals are treated as a respectful last resort rather than the opening move (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`) (original session `44859035-df25-47a4-bd36-f12b628efdb6`).
- **AI supports productivity, not vague transformation claims**: Automation is attached to concrete operating tasks and measurable time savings inside the efficiency engine (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`).
- **Executive readability is literal**: The deck uses large conclusion-first headlines, sparse supporting text, and macro-to-detail sequencing so the CEO can understand the recommendation before reading the evidence (original session `44859035-df25-47a4-bd36-f12b628efdb6`).
- **Public GitHub delivery is the maintained surface**: The repository and its recent commit provide the durable source for the plan ([recorded evidence](https://github.com/gitteromri-ux/abraham-tlv-gm/commit/57446de352e3b8e549b1801426b8dda176cd0460)).

### See also

- `entities/gita-agency`: strategy and delivery owner
- `concepts/github-pages-delivery`: browser-ready handoff pattern


---

Record: `club-italia-school` | knowledge last updated: 2026-09-13T10:26:00+00:00

## Club Italia School

Club Italia is a public, browser-ready concept for a premium online Italian-language school built as a sister model to French Atelier. It combines CEFR-based live courses, spoken-Italian modules, culture capsules, regional teachers, syllabi, and an AI-tutor concept in a 58-page GitHub Pages site. Its release standard requires contextual media and fold-by-fold perceptual inspection, not only automated link checks (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).

### How it works

The school maps a complete learning and culture architecture into public course, teacher, editorial, event, pricing, legal, and support surfaces, with 11 downloadable course syllabi and subject-matched video across its major folds (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).

- **Structural parity without visual cloning**: French Atelier supplies the depth and school architecture, while Club Italia uses its own premium Italian palette of red, white, green, and black, editorial typography, shadows, and cinematic media (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **Three product families**: The offer separates four core Italian levels, four spoken-Italian courses, and three culture capsules. Course pages carry a 20-lesson syllabus, schedule and format facts, teacher, price, certificate, refund, and access information (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **CEFR and Italian institutions ground the curriculum**: The research and syllabus framing use CEFR and Italian language-school references rather than treating the product as a generic lifestyle concept (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **Media is assigned by subject**: Twenty supplied Artgrid clips were remuxed and compressed for the site, with footage mapped to Rome, Tuscany, Venice, Sicily, food, travel, teachers, and course contexts rather than reused indiscriminately (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **Full school over pitch mockup**: The first shallow build was rejected; the accepted direction requires meaningful multi-fold course, teacher, culture, editorial, and institutional pages rather than surface-level page count (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **Real photography over generated-looking people**: Artificial teacher and student imagery was rejected. The cinematic rebuild replaced it with sourced human photography and retained the supplied Artgrid footage as the visual backbone (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`) ([recorded evidence](https://github.com/gitteromri-ux/club-italia/commits/main)).
- **Perceptual QA is a release gate**: Automated URL and media checks did not catch generic folds, mismatched cards, weak mobile wrapping, or unsuitable portraits. The course-page cinematic treatment and a complete multi-viewport fold review remain necessary for parity with the reference site (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`).
- **Deployment branch needs normalization**: The 2026-09-13 cinematic build is on `main` and deployed successfully, while the repository still names the older `master` branch as default ([recorded evidence](https://github.com/gitteromri-ux/club-italia/commits/main)).

### Key surfaces

- Site: `https://gitteromri-ux.github.io/club-italia/` (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`)
- Repo: `https://github.com/gitteromri-ux/club-italia` (original session `2e57adb4-e6af-4490-a1c4-bf8b47e0eb80`)

### See also

- `projects/french-atelier-website`: sister-school reference
- `entities/gita-agency`: concept and delivery


---

Record: `lla-handoff-pack` | knowledge last updated: 2026-09-02T10:45:00+00:00

## LLA Handoff Pack

LLA Handoff Pack is a public, mobile-ready two-tab transfer surface for the Longevity Life Academy ecommerce media strategy and technical checkout state. It separates measured account and implementation facts from unmeasured forecasting assumptions so another strategist or implementation team can resume without repeating the failed analysis (original session `e8f80581-31fc-4a86-989d-138e3812a19f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-handoff-pack)).

### How it works

The GitHub Pages site exposes a Meta Media Brief and Technical Handoff at stable hash-linked tabs. The media brief defines the assignment and evidence boundaries; the technical brief captures live code state, deployment risk, CRM behavior, credentials inventory, and cleanup work (original session `e8f80581-31fc-4a86-989d-138e3812a19f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-handoff-pack)).

- **Measured facts stay separate from unknown rates**: Verified Ads Manager and live technical observations are isolated from conversion assumptions; unmeasured rates must be named as assumptions and expressed as ranges rather than presented as account data (original session `e8f80581-31fc-4a86-989d-138e3812a19f`) ([recorded evidence](https://github.com/gitteromri-ux/lla-handoff-pack)).
- **The mission leads the handoff**: The recipient is asked for product-specific campaign architecture, fully named funnel metrics, whole-sale daily forecasts, charts, and numeric kill criteria, while honoring full-ecommerce constraints and requiring authorization before technical action (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Repository state is a deployment gate**: The handoff warns that the live `$279` and ecommerce-mode fixes were not committed, so a clean rebuild from HEAD can reintroduce the checkout outage (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).
- **Public but intentionally unindexed**: The page is responsive, requires no login, and uses `noindex`; it contains operational account identifiers and test-order IDs but no tokens, keys, or passwords (original session `e8f80581-31fc-4a86-989d-138e3812a19f`).

### Key surfaces

- Media brief: `https://gitteromri-ux.github.io/lla-handoff-pack/#media` (original session `e8f80581-31fc-4a86-989d-138e3812a19f`)
- Technical handoff: `https://gitteromri-ux.github.io/lla-handoff-pack/#tech` (original session `e8f80581-31fc-4a86-989d-138e3812a19f`)

### See also

- `projects/lla-course-checkout`: captured technical state
- `projects/lla-delta-force`: ecommerce strategy context
- `projects/lla-master-delivery-hub`: broader client handoff


---

Record: `lla-delta-force` | knowledge last updated: 2026-08-27T07:18:00+00:00

## LLA Delta Force

LLA Delta Force is Longevity Life Academy’s three-track “Save the Pilot” activation initiative: high-intent lead sourcing, influencer partnerships, and direct-response ecommerce execution (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`) ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force)).

### How it works

The program joins research and launch materials in one activation hub rather than treating lead vendors, influencers, and ecommerce as separate assignments (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`) ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force)).

- **Intent must be mechanically evidenced**: Lead-vendor rankings require the exact lead type, verification mechanism, B2C and vertical fit, pricing evidence, launch speed, named contacts, direct links, and explicit backup or rejection reasons (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`).
- **Influencer conflict is based on competitive commitment**: A single sponsorship is not disqualifying; ownership of, or aggressive promotion for, a competing program is (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`).
- **Ecommerce stays distinct from call-center acquisition**: The French Atelier call-center model cannot substitute for LLA’s purchase-objective architecture, landing-page traffic assumptions, conversion model, budgets, campaigns, creatives, funnel, and recovery emails (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`).
- **Primary-source validation is a launch gate**: Vendor fit, influencer reach and contacts, pricing, benchmarks, offer terms, checkout paths, and purchase instrumentation must be verified before activation or volume modeling (original session `b6e96342-b7f1-44c0-ac46-994b849660c3`).
- **One execution surface**: The `lla-delta-force` hub combines the activation plan, creative gallery, eight recovery emails, 15 remarketing banners, four promo emails, two landing pages, and a public ecommerce status/proof page for direct use ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force)) ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/08f3248585a9187165114a2f4e6c9a28b7f35fb5)) ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/b27f3b142a4f6a293413e1adf3782d19cf111fcb)).
- **Current offer alignment**: The activation hub’s ecommerce pricing is aligned to `$279/mo`, matching the checkout production configuration ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/efa5362253aa28f8ceb119b68eb05565182cd516)).
- **Five lifecycle funnels replace the earlier recovery set**: The email architecture now comprises 20 emails across three abandoned-cart paths, consolidated onboarding, and a no-show path; the generic new-leads funnel was removed ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/4b42bd61a14be5db54bb5b7cc7b6bb28d5f48430)).
- **One-field checkout status model**: Checkout events are represented through a single latest-status field with a purchase state and timed abandonment waits, keeping the CRM handoff narrow ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force/commit/d366d86d9f63cf2a9748415add05953e935fc64e)).

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/lla-delta-force` ([recorded evidence](https://github.com/gitteromri-ux/lla-delta-force))

### See also

- `projects/lla-growth-engine`: ecommerce recovery system
- `projects/lla-course-checkout`: purchase flow
- `entities/longevity-life-academy`: client and offer
- `projects/lla-master-delivery-hub`: executive handoff
- `projects/lla-masterclass-emails`: lifecycle email system


---

Record: `lla-ad-banner-campaign` | knowledge last updated: 2026-08-14T07:55:00+00:00

## LLA Ad Banner Campaign

LLA Ad Banner Campaign is Omri’s GitHub Pages-based Meta and Instagram creative system for Julie Gibson Clark and Courtney, with reusable brand rules across four platform aspect ratios (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`) (original session `6076d5ae-eac7-4bb9-a282-c40b72d79e6d`).

### How it works

The campaign maintains public galleries for Julie, Julie-on-set, and Courtney, renders each concept natively across 1:1, 4:5, 9:16, and 1.91:1 formats, and feeds a four-chapter LLA launch-review deck with PR coverage and video cuts (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`) (original session `6076d5ae-eac7-4bb9-a282-c40b72d79e6d`) ([recorded evidence](https://github.com/gitteromri-ux/julie-onset-banners)) ([recorded evidence](https://github.com/gitteromri-ux/lla-campaign-chapters)).

- **Locked visual system**: Use a large `Longevity Life Academy by eTeacher Group` lockup, real instructor imagery where available, short benefit-first headlines, Trustpilot proof near the CTA, and no tiny-cap eyebrows, decorative dot separators, ghost pills, or other AI-design tells (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`) (original session `6076d5ae-eac7-4bb9-a282-c40b72d79e6d`).
- **Julie positioning**: Julie’s banners may use “2nd Slowest-Aging Person on Earth,” DunedinPACE 0.665, and selective Bryan Johnson comparisons; the final V7 direction uses full-bleed photography and a compact bottom-third information stack (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`).
- **Courtney positioning**: Courtney’s banners focus on a personal longevity protocol, biomarkers, six pillars, and the live 18-session/18-week course; Julie’s slow-aging credential does not transfer to Courtney (original session `6076d5ae-eac7-4bb9-a282-c40b72d79e6d`).
- **Platform-native CTA decision**: Embedded CTA buttons were removed from the final Julie and Courtney systems because Meta/Instagram supplies the action control; the recovered space is used for stronger hierarchy, Trustpilot proof, and platform-safe margins (original session `48172e2b-cb21-4d33-95d6-10eb52a00186`) (original session `753a6cb3-829e-44f4-869b-7daac62f1e88`).
- **Aspect-ratio-specific composition**: Landscape banners use a horizontal facts-and-stats band rather than a compressed vertical stack; Story layouts retain extra bottom clearance for platform UI, and Courtney’s identifying caption sits beside her face rather than in the furniture band (original session `48172e2b-cb21-4d33-95d6-10eb52a00186`).
- **Expanded Julie system**: The approved Chosen-tab design was propagated to 58 copy variants in four native sizes, producing 232 upload-ready files while preserving each tab’s copy angle (original session `753a6cb3-829e-44f4-869b-7daac62f1e88`).
- **Julie credential treatment**: “2nd Slowest-Aging Person on Earth” is a primary proof element in the same champagne-gold luxury-serif language as the headline, not a small lower-third label (original session `753a6cb3-829e-44f4-869b-7daac62f1e88`).
- **Julie-on-set extension**: A separate gallery composites Julie onto the walnut-library set across seven concepts and four placements while preserving the campaign’s full-bleed system ([recorded evidence](https://github.com/gitteromri-ux/julie-onset-banners)).
- **Campaign consolidation**: The four-chapter deck combines PR coverage, Julie banners, Courtney banners, and Courtney’s final cuts in `gitteromri-ux/lla-campaign-chapters` ([recorded evidence](https://github.com/gitteromri-ux/lla-campaign-chapters)).
- **Press-placement derivative pack**: Four live article placements were converted into 16 upload-ready Meta/Instagram creatives, each rendered in the campaign’s four native sizes with article-safe post copy and `Learn More` routing (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`).
- **Julie Meta production pack**: The dedicated `julie-meta-banners` surface carries four designs across six placements, including square, landscape, portrait, Story, and high-resolution variants; ratio changes preserve the complete composition rather than cropping it (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) ([recorded evidence](https://github.com/gitteromri-ux/julie-meta-banners)).
- **Organic social lockup discipline**: The social go-live pack preserves the supplied `Longevity Life Academy by eTeacher Group` lockup on brand blue without changing its fonts or colors, using a high-resolution transparent master rather than enlarging the earlier low-resolution extraction (original session `3779792c-8b6c-4b02-ae27-f35bb58f431d`).
- **Exact-size master pack**: `lla-meta-ig-ad-sizes` is the current public delivery surface for native Meta and Instagram placements. Its approval passes removed cards without visible price and other rejected formats instead of preserving every generated concept ([recorded evidence](https://github.com/gitteromri-ux/lla-meta-ig-ad-sizes)).
- **Gaurav handoff is source-count exact**: The `Gaurav Upload` tab was corrected from a larger generated set to the exact 21 files decoded from `only-these.docx`; delivery count follows the source document rather than inferred size permutations ([recorded evidence](https://github.com/gitteromri-ux/lla-meta-ig-ad-sizes/commit/9bc2637d53fe3afbc2233e0ff09dba3badaf4c4e)).

### Key surfaces

- Julie repo: `gitteromri-ux/lla-meta-banners-gallery` ([recorded evidence](https://github.com/gitteromri-ux/lla-meta-banners-gallery))
- Julie gallery: `https://gitteromri-ux.github.io/lla-meta-banners-gallery/` (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`)
- Courtney repo: `gitteromri-ux/courtney-banners` ([recorded evidence](https://github.com/gitteromri-ux/courtney-banners))
- Courtney gallery: `https://gitteromri-ux.github.io/courtney-banners/` (original session `6076d5ae-eac7-4bb9-a282-c40b72d79e6d`)
- Julie-on-set repo: `gitteromri-ux/julie-onset-banners` ([recorded evidence](https://github.com/gitteromri-ux/julie-onset-banners))
- Campaign deck repo: `gitteromri-ux/lla-campaign-chapters` ([recorded evidence](https://github.com/gitteromri-ux/lla-campaign-chapters))
- Julie Meta repo: `gitteromri-ux/julie-meta-banners` ([recorded evidence](https://github.com/gitteromri-ux/julie-meta-banners))
- Organic social hub: `https://gitteromri-ux.github.io/lla-social-golive/` (original session `3779792c-8b6c-4b02-ae27-f35bb58f431d`)
- Exact-size master hub: `https://gitteromri-ux.github.io/lla-meta-ig-ad-sizes/` ([recorded evidence](https://github.com/gitteromri-ux/lla-meta-ig-ad-sizes))

### See also

- `projects/lla-pr-campaign`: first deck chapter
- `projects/lla-pr-article-ads`: placement-led ad pack
- `projects/lla-s09-s10-video-delivery`: final video cuts
- `entities/longevity-life-academy`: client brand
- `concepts/github-pages-delivery`: public handoff pattern


---

Record: `lla-s09-s10-video-delivery` | knowledge last updated: 2026-08-11T08:56:00+00:00

## LLA S09/S10 Video Delivery

LLA S09/S10 Video Delivery is Omri’s Courtney production, source-reconstruction, and editor-handoff system across `gitteromri-ux/lla-s09-s10-downloads` and `gitteromri-ux/lla-courtney-final`, with public GitHub delivery surfaces and automated video pipelines for Longevity Life Academy ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/5088402f7a1cee1ad9253d89a66b9af87ea05d3e)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/2baa8b113f2d721f96154ed17ddade3b1500996e)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads)) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-final)).

### How it works

The repo hosts Courtney FRONT and SIDE video versions, downloadable media files, and a GitHub Pages viewer with inline playback/download buttons ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794)). The production target is full-frame Courtney-only video with Teams UI removed, smooth playback, audio/lipsync integrity, sharp color/detail, and no AI alteration of face, voice, or mouth unless explicitly overridden (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `720bb025-55fc-453c-a4f8-ae5fe4b3bde1`).

- **GitHub Pages as the delivery surface**: A normal landing page with videos and download buttons became the required delivery shape after raw GitHub repository pages and direct download links caused login/download confusion ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794)) (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`).
- **Split large video masters for GitHub constraints**: The 4K set was delivered as multiple FRONT/SIDE parts because GitHub/Git LFS size and disk constraints made single large masters fragile in-session (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/e2ac298275c3caaf301429dec0ad0ebaa47fa7f9)). A later viewer commit consolidated all 19 files with playable URLs and download buttons ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/2baa8b113f2d721f96154ed17ddade3b1500996e)).
- **No AI face-touching default**: The agreed pipeline default is Lanczos/math-based upscale, sharpening, color work, and audio copy/remastering; AI super-resolution requires explicit override because it can alter face detail (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `81c1193f-08f7-49f7-974d-a55f605f1ec0`).
- **Quality claims must track source limits**: Earlier claims of 90%+ studio quality were contradicted by the Teams-source tile limitations, and future work needs objective source-resolution framing before making studio-quality promises (original session `55a60e33-9e3b-46be-8dec-1524935234b3`).
- **Real-footage replacement boundary**: After failed new-set/body-completion routes, the acceptable repair was to replace fake library talking-head shots with real home footage while leaving face, voice, captions, music, b-roll, and original footage timing untouched unless Omri explicitly approves a card/caption edit (original session `e8852a7d-a2ae-458f-b4b4-a9a69c669518`).
- **Automated video pipeline**: The active repo now uses Actions/automation commits for Seedance assembly, Demucs stem separation, animated cards, source chunking, and lip-sync retiming; connector data showed most recent workflow failures were transient and later succeeded ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads)).
- **Master production file as planning layer**: A separate Courtney master-production GitHub Pages site deconstructs French Atelier reference films, cleans Courtney’s real new-set transcript, and holds three storyboard routes plus transformation/action CTA cards for editing handoff (original session `685f1849-e891-4740-a845-579dd39592ca`).
- **Ad-format derivatives**: The repo now carries branded Courtney HERO and META60 cuts plus Meta-ready 9:16 and 1:1 canvases, so the project includes paid-social derivatives in addition to master downloads ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/e92d72e)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/c4bc349)).
- **Premium b-roll integration**: Recent builds incorporated Artlist premium b-roll, extending the delivery from simple cleanup/downloads into finished campaign-video assets ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/ea576a0)).
- **Campaign-card derivative cuts**: The latest 90s/60s-derived campaign cuts use premium navy/Playfair full-screen cards, teacher footage, and an outro, with full-screen card holds accepted when placed for narration logic (original session `e8852a7d-a2ae-458f-b4b4-a9a69c669518`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/fb2d374de9b167bba77b1b8493434e2b6d52a868)).
- **A/V sync hard gates**: Late repo work added audio padding/concat safeguards and a silent outro audio track so rendered body/outro segments keep equal audio/video length ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/70ca3b47e68f4ce5b2c1629e20c1bd05cfe8559a)) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/3e88cc4168277b59dee2d16d75a38279b1f5d49c)).
- **Two-pass release audit**: Final delivery requires both an itemized brief-compliance audit and a separate cold-viewer/CEO quality audit. The latter caught repeated b-roll, transition ghosting, a disconnected wireframe ending, unsafe audio peak, and weak caption contrast that checklist-only review missed (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/dbb22c40b2ac636a835bb3cc981c688137f97b31)).
- **Approved sequence is a hard constraint**: The final campaign-card chain is `18 Live Session Course` → `Your biomarkers. Your data. Your longevity protocol.` → fast gray protocol b-roll → `Taught by longevity’s leading experts` → tight Julie shot → Zoom lesson → outro. Inverting this sequence or inserting extra Courtney/faculty shots is a release-blocking error (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`).
- **One-use footage constraints**: The green b-roll and Harvard age graph each appear once; pillar b-roll must align to Courtney’s spoken pillar names, and approved footage cannot be globally replaced to hide isolated green-frame defects (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`).
- **Separate production repository**: Courtney’s production and source handoff moved to `gitteromri-ux/lla-courtney-final`, which carries final cuts, raw-source releases, per-scene assets, graphic packs, and editor pages (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-final)) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-final/releases/tag/raw-sources-silent-v1)).
- **Explicit public final pair**: The authorized `lla-90s-final` handoff pairs Courtney v18 with Julie V24; both talent and version must be named because their version histories are independent (original session `f573e739-cd35-4b06-a95b-417ae188a9d5`) ([recorded evidence](https://github.com/gitteromri-ux/lla-90s-final/releases/tag/v90s)).
- **Social placement pack**: `meta-pack-v1` contains 18 placement renders across the two talents and their full/90s/60s variants, produced through parallel GitHub Actions jobs with faststart enabled (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-final)).
- **Original-source editor handoff**: Each storyboard scene must sit beside its full-length original MP4/JPEG/PNG source, never a clip extracted from the finished render. The Courtney V2 synchronization accepts only verified frame matches and leaves uncertain rows unresolved rather than inserting lookalikes (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`) (original session `3d5fbe49-ea40-467d-84aa-2f44e6db4c90`).
- **Combined Courtney/Julie source sheet**: The public master-elements handoff maps 41 Courtney V16 scenes and 23 Julie scenes to original camera masters, b-roll, cards, graphics, and exact in-points; its delivery audit reported 44 download links and all 45 asset links returning HTTP 200 (original session `6e61e143-0306-4be3-bafb-9f0f01791c2a`).
- **Two-tab Julie/Courtney cut handoff**: The client-facing cut hub keeps Julie and Courtney on separate tabs, opens Julie by default, places each full master before its derivatives, and makes every Courtney cut’s hook and source-segment provenance visible (original session `95cc26e4-8e21-4311-b006-486e8dbaa042`) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-cuts)).
- **Courtney cut-length mismatch is unresolved**: The request named 75s, 70s, 55s, and 40s variants, while the published handoff claimed 75s, 60s, 45s, and 30s; no later acceptance resolves which set is authoritative (original session `95cc26e4-8e21-4311-b006-486e8dbaa042`).
- **Reference typography requires visual verification**: Font family, size, weight, and italic treatment must be established from the actual reference frame; an unverified typography guess is not a brand specification (original session `5c6b712e-2649-4a99-9c96-52b8344a6209`).
- **Captions yield to graphic cards**: Julie/Courtney captions sit low, use smaller type and longer lines, and appear only over talent or b-roll; cards and animations remain caption-free so competing text layers do not collide (original session `6e61e143-0306-4be3-bafb-9f0f01791c2a`) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-cuts/commit/857b3f39c1f9d1471a5971f00f49d35555fada10)).
- **Website b-roll must preserve source identity**: The approved scrolling sequence runs from `The Six Pillars` to `Taught by Leading Voices` with Julie centered. It cannot be replaced by the older four-instructor clip or by smeared screenshot reconstruction (original session `6e61e143-0306-4be3-bafb-9f0f01791c2a`) ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-cuts/commit/a16d5a5e2d5ca00e4841f17d66a7213efadb2ed8)).
- **Lower thirds are isolated overlays**: The Julie treatment is a small black box with white serif italic type, placed bottom-right at 19–22 seconds and limited to the supplied name/ranking copy; the camera master remains untouched (original session `6c26641f-55cc-42c1-a1a3-b0425e5d0e00`).
- **Paid-social launch set**: The August release work produced Courtney and Julie launch variants across 90s/75s/60s/45s/30s, plus b-roll, lower-thirds, and cards ([recorded evidence](https://github.com/gitteromri-ux/lla-courtney-cuts/commit/7466de26a43ef29d2a13b56bcaf72942bbe3a01d)) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-cuts)).

### Key assets

- Repo: `gitteromri-ux/lla-s09-s10-downloads` ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads))
- Landing page: `https://gitteromri-ux.github.io/lla-s09-s10-downloads/` ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794))
- Latest all-versions viewer commit: “All versions FRONT+SIDE with download buttons” ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794))
- Master production site: `https://gitteromri-ux.github.io/courtney-master-production/` (original session `685f1849-e891-4740-a845-579dd39592ca`)
- Final Julie V24 / Courtney v18 handoff: `https://gitteromri-ux.github.io/lla-90s-final/` (original session `f573e739-cd35-4b06-a95b-417ae188a9d5`)
- Courtney editor source page: `https://gitteromri-ux.github.io/lla-courtney-final/editor/` (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`)
- Courtney V16 + Julie master-elements page: `https://gitteromri-ux.github.io/lla-courtney-final/master-elements/` (original session `6e61e143-0306-4be3-bafb-9f0f01791c2a`)

### See also

- `entities/omri-gitter`: project owner
- `entities/longevity-life-academy`: client context
- `concepts/video-quality-qa`: media QA criteria
- `concepts/github-pages-delivery`: delivery surface rule
- `projects/lla-ad-banner-campaign`: campaign creative suite
- `projects/lla-master-delivery-hub`: consolidated handoff


---

Record: `in-venture-website` | knowledge last updated: 2026-08-10T05:25:00+00:00

## IN Venture Website

IN Venture Website is Omri’s public GitHub Pages redesign for IN Venture, intended to present the firm at a premium global venture-capital standard across desktop and mobile (original session `65862fd2-e80c-420b-aad6-866d3e19c710`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-website)).

### How it works

The `gitteromri-ux/in-venture-website` repository contains the public multi-page site. The brief applies to the home page and every internal page, with a stable client-facing URL and full mobile treatment (original session `65862fd2-e80c-420b-aad6-866d3e19c710`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-website)).

- **Premium VC positioning across the whole site**: The design must read as credible, bright, editorial, and luxury-grade rather than generic, dark, or mock-up-like; imagery, contrast, navigation, typography, and internal pages are all part of the acceptance bar (original session `65862fd2-e80c-420b-aad6-866d3e19c710`).
- **Rejected iterations are not design approval**: The user rejected every delivered image system in the source session, so the assistant’s font and image choices are not approved brand decisions (original session `65862fd2-e80c-420b-aad6-866d3e19c710`).
- **Durable public handoff**: The project uses a normal GitHub Pages URL rather than an expiring or cache-sensitive preview link (original session `65862fd2-e80c-420b-aad6-866d3e19c710`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-website)).

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/in-venture-website` ([recorded evidence](https://github.com/gitteromri-ux/in-venture-website))
- Site: `https://gitteromri-ux.github.io/in-venture-website/` (original session `65862fd2-e80c-420b-aad6-866d3e19c710`)

### See also

- `projects/in-venture-programme`: programme document handoff
- `concepts/github-pages-delivery`: delivery pattern
- `entities/gita-agency`: agency context


---

Record: `in-venture-programme` | knowledge last updated: 2026-08-10T05:25:00+00:00

## IN Venture Programme

IN Venture Programme is Omri’s source-faithful public handoff for a programme plan, Partner Interview, and Force Management Interview (original session `a6c0ef82-b281-444d-8873-949c7b0db941`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-programme)).

### How it works

The `gitteromri-ux/in-venture-programme` repository presents the plan and two interviews as separate browser tabs while retaining a standalone plan view (original session `a6c0ef82-b281-444d-8873-949c7b0db941`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-programme)).

- **Source fidelity is the governing constraint**: Document wording and design must remain unchanged; the tab bar is the only authorized structural addition (original session `a6c0ef82-b281-444d-8873-949c7b0db941`).
- **Editable interview fields**: Grey interview boxes must accept typing and retain entered text after reload, while the plan remains a faithful view of the supplied source (original session `a6c0ef82-b281-444d-8873-949c7b0db941`) ([recorded evidence](https://github.com/gitteromri-ux/in-venture-programme)).

### Key surfaces

- Repo: `https://github.com/gitteromri-ux/in-venture-programme` ([recorded evidence](https://github.com/gitteromri-ux/in-venture-programme))
- Site: `https://gitteromri-ux.github.io/in-venture-programme/` (original session `a6c0ef82-b281-444d-8873-949c7b0db941`)

### See also

- `projects/in-venture-website`: public brand site
- `concepts/github-pages-delivery`: delivery pattern
- `entities/gita-agency`: agency context


---

Record: `lla-pr-article-ads` | knowledge last updated: 2026-07-31T06:29:00+00:00

## LLA PR Article Ads

LLA PR Article Ads is a paid-social derivative pack that turns four live LLA press placements into upload-ready Meta and Instagram creatives with matching post copy. (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-article-ads))

### How it works

The public gallery contains creatives for USA TODAY, Yahoo Finance, EIN Presswire, and NewsBreak. Each article is rendered at 1080×1080, 1080×1350, 1080×1920, and 1200×628, with downloadable files and copy fields for Meta’s primary text, headline, and description. (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`)

- **Article-led framing**: Creative language presents the published story rather than making unsupported personal-attribute claims. CTA is `Learn More`, with `longevitylifeacademy.com` as the destination. (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`)
- **One production matrix**: Four placements multiplied by four native platform sizes creates 16 upload-ready ads, with HD variants and placement guidance handled in the gallery. (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`)
- **Course proof stays consistent**: The pack uses the LLA/eTeacher lockup, Julie’s official PR image, `$289/month`, 18 weeks/18 live sessions, the Abbott Lingo CGM, cohort size, and Trustpilot 4.6/5. (original session `8c226f0b-9057-4558-8c9b-0733e53747a0`)
- **GitHub Pages handoff**: `gitteromri-ux/lla-pr-article-ads` is the public source and delivery surface for the finished creative pack. ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-article-ads))

### See also

- `projects/lla-pr-campaign`: source placements
- `projects/lla-ad-banner-campaign`: creative system
- `entities/longevity-life-academy`: client brand
- `concepts/github-pages-delivery`: public handoff


---

Record: `lla-employee-referral` | knowledge last updated: 2026-07-31T06:29:00+00:00

## LLA Employee Referral Campaign

LLA Employee Referral Campaign lets eTeacher Group employees promote the Longevity Blueprint while keeping the incentive mechanism invisible to prospective students. The public GitHub Pages surface is a normal course-enrollment page; the separate employee-facing banner gallery carries the `$250` reward message. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`) ([recorded evidence](https://github.com/gitteromri-ux/lla-employee-referral))

### How it works

The public route presents standard course positioning, proof, curriculum, press credibility, and a normal signup form. Employee attribution can travel through a silent `?ref=` URL parameter, while the prospect-facing page and linked article pages contain no referral, reward, bonus, or employee language. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`)

- **Public/private message separation**: The public landing page and four article pages use plain enrollment CTAs and `$289/month` course pricing; only the employee banner gallery exposes the `$250` incentive. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`)
- **Silent employee attribution**: Employee-specific duplicated links may use a `?ref=` parameter that is stored in CRM notes without surfacing the referral mechanism to the prospect. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`)
- **US Eastern Time is a conversion-critical disclosure**: The hero uses a prominent ET callout and the signup area repeats that live sessions run on US Eastern Time and are recorded. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`)
- **Campaign creative remains course-led**: Four banner layouts explain the reward, course facts, aging authority, and six-pillar curriculum with exact LLA branding and large readable CTAs. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`)
- **Public preview and handoff**: `gitteromri-ux/lla-employee-referral` is the public source repository, with separate live landing-page and banner-gallery routes for internal review and downloads. (original session `ac11344f-e123-4ce3-a5c6-d6f759a0ebea`) ([recorded evidence](https://github.com/gitteromri-ux/lla-employee-referral))

### See also

- `entities/longevity-life-academy`: program and brand
- `projects/lla-promo-email-funnel`: related CRM funnel
- `projects/lla-ad-banner-campaign`: creative standards
- `concepts/github-pages-delivery`: public handoff


---

Record: `lms-image-pack` | knowledge last updated: 2026-07-29T09:42:00+00:00

## LMS Image Pack

LMS Image Pack is Omri’s GitHub Pages delivery surface for themed French-culture imagery in exact LMS slot dimensions, with downloadable JPEG variants for the homepage and My Achievements page (original session `9726b072-940f-432f-b817-15063d618aad`) ([recorded evidence](https://github.com/gitteromri-ux/lms-image-pack)).

### How it works

The pack groups 11 images under fashion, music, cuisine, wine, art, and film themes, then exports each at 161×147 and 106×101 pixels for 22 downloadable files (original session `9726b072-940f-432f-b817-15063d618aad`).

- **Licensed-source boundary**: Watermarks are not removed from iStock previews; clean generated replacements are used when licensed originals are unavailable (original session `9726b072-940f-432f-b817-15063d618aad`).
- **Exact canvas over uncropped source**: The near-square LMS slots are filled edge to edge with minimal cover-cropping. This avoids white padding while keeping every output at the exact requested dimensions (original session `9726b072-940f-432f-b817-15063d618aad`).
- **Delivery QA**: Files use JPEG format, theme-and-size filenames, and pixel-dimension verification before publication (original session `9726b072-940f-432f-b817-15063d618aad`).

### Key surfaces

- Repo: `gitteromri-ux/lms-image-pack` ([recorded evidence](https://github.com/gitteromri-ux/lms-image-pack))
- Gallery: `https://gitteromri-ux.github.io/lms-image-pack/` (original session `9726b072-940f-432f-b817-15063d618aad`)

### See also

- `concepts/github-pages-delivery`: public download handoff
- `entities/longevity-life-academy`: client program surface


---

Record: `lla-turnaround-plan` | knowledge last updated: 2026-07-29T09:42:00+00:00

## LLA Turnaround Plan

LLA Turnaround Plan is a GitHub Pages deck/site for the Longevity Life Academy turnaround narrative, combining marketing actions, sales actions, real LLA assets, and contact-rate improvements into a CEO-ready presentation (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`) (original session `4fca1618-75d1-4a7b-aec7-e07a13ba32c9`).

### How it works

The deck organizes the turnaround into marketing and sales workstreams, then deep-dives into proof assets rather than presenting the plan as a static bullet list (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`).

- **Asset-backed turnaround story**: The marketing side anchors on story-format videos, the Julie film-series slides, Courtney scripts/video, live PR/deck proof, and three Longevity promo-email mockups migrated from existing eTeacher/French Atelier-style references (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`).
- **Higher contacted-rate mechanism**: The site demonstrates callback slots, WhatsApp, and Messenger next to the lead form, using the `lla-homepage-demo` implementation as the visual proof for the funnel change (original session `4fca1618-75d1-4a7b-aec7-e07a13ba32c9`) ([recorded evidence](https://github.com/gitteromri-ux/lla-homepage-demo)).
- **Sales-side operating moves**: The plan includes updated scripts, night-shift calling hours, stronger trainer/rep coverage on new campaigns, staffing/shift planning, and a sales-script appendix (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`).
- **Second-pilot performance framework**: The board narrative ties additional budget to measurable outcomes: test self-service checkout across campaigns, use WhatsApp to improve contact and conversion, target a 2–3× lift from current rates, and scale video/masterclass spend only after positive ROI is established (original session `6e5fbcf0-34c0-4539-b72f-ac61f6db0280`).
- **Consolidated go-to-market workstreams**: The operating plan spans two-phase PR, Julie authority-building, a new video/banner library, higher-value US targeting, a women 35–65 emphasis, earned-media retargeting, three-click checkout, contact-flow changes, and reactivation of the 3,500-lead database (original session `6e5fbcf0-34c0-4539-b72f-ac61f6db0280`).
- **GitHub Pages delivery**: The deck was deployed at `gitteromri-ux.github.io/lla-turnaround-plan/`, with the Courtney video pointed to an LFS media URL so it could play on Pages (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`) ([recorded evidence](https://github.com/gitteromri-ux/lla-turnaround-plan)).

### Key surfaces

- Repo: `gitteromri-ux/lla-turnaround-plan` ([recorded evidence](https://github.com/gitteromri-ux/lla-turnaround-plan))
- Site: `https://gitteromri-ux.github.io/lla-turnaround-plan/` (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`)
- Homepage demo dependency: `https://gitteromri-ux.github.io/lla-homepage-demo/#lead-gen` (original session `4fca1618-75d1-4a7b-aec7-e07a13ba32c9`) ([recorded evidence](https://github.com/gitteromri-ux/lla-homepage-demo))

### See also

- `entities/longevity-life-academy`: client surface
- `projects/lla-pr-campaign`: PR credibility layer
- `projects/lla-s09-s10-video-delivery`: Courtney video assets
- `concepts/github-pages-delivery`: delivery surface


---

Record: `personalix-website` | knowledge last updated: 2026-07-24T05:47:00+00:00

## Personalix Website

Personalix Website is Omri’s GitHub Pages site for Personalix, an AI-powered human-first recruitment platform positioned around “Candidate first. Designed for people.” ([recorded evidence](https://github.com/gitteromri-ux/personalix)) (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`).

### How it works

The site lives in `gitteromri-ux/personalix` and uses a single public GitHub Pages URL as the CEO/client handoff surface ([recorded evidence](https://github.com/gitteromri-ux/personalix)) (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`). Its current design system combines premium typography, neon glass layering, floating candidate-dashboard imagery, mobile sliders, and per-card brand-color accents while preserving the supplied content verbatim (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`) ([recorded evidence](https://github.com/gitteromri-ux/personalix/commit/e4d090f)).

- **Verbatim-content redesign**: The redesign must improve perceived premium value without changing the words or removing folds, because Omri’s explicit constraint was content integrity plus a stronger visual system (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`).
- **Reference-led premium style**: The design moved away from an aggressive generic tech look toward the supplied luxury reference language: Boska/Switzer typography, glass/neon layering, a floating candidate card, and brand-purple/light-blue accents (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`) ([recorded evidence](https://github.com/gitteromri-ux/personalix/commit/b1796f5)).
- **Multicolor card system**: Card folds should not read as monotone navy; the accepted fix gives neighboring cards distinct on-brand accents through background tint, border, glow, icon chip, ticks, and badges (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`) ([recorded evidence](https://github.com/gitteromri-ux/personalix/commit/e4d090f)).

### See also

- `entities/omri-gitter`: project owner
- `concepts/github-pages-delivery`: live handoff rule


---

Record: `lla-domain-reputation-fix` | knowledge last updated: 2026-07-24T05:47:00+00:00

## LLA Domain Reputation Fix

LLA Domain Reputation Fix is Omri’s Longevity Life Academy/eTeacher workstream for separating website-trust remediation from Google Postmaster/email authentication recovery (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-life-academy/commit/6156e40)).

### How it works

The work has two tracks: website trust/compliance pages on `www.longevitylifeacademy.com`, and DNS/email authentication fixes for the campaign-sending domain (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-life-academy/commit/6156e40)). The website can remove landing-page trust and legal defects, but the Google Postmaster “Bad” score is an email-reputation signal that depends on authenticated, disciplined sending over time (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`).

- **Website trust pages shipped**: Privacy Policy, Terms of Service, and Medical Disclaimer pages were added, dead footer links were repaired, and `robots.txt`/`sitemap.xml` were added so campaign-linked pages have normal trust/compliance surfaces (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`) ([recorded evidence](https://github.com/gitteromri-ux/longevity-life-academy/commit/6156e40)).
- **ActiveCampaign SPF is the P0 email fix**: Live checks identified ActiveCampaign as the campaign sender that needs SPF authorization, so the root TXT record should include `include:emsend1.com` alongside Microsoft 365 rather than relying on website changes to move Postmaster (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`).
- **No instant reputation switch**: The CEO-facing framing should separate what can be fixed immediately (authentication and trust defects) from reputation recovery, which rebuilds through clean sending rather than same-day website edits (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`).

### See also

- `entities/longevity-life-academy`: affected client surface
- `projects/lla-promo-email-funnel`: email campaign funnel


---

Record: `hana-enneagram-assessment` | knowledge last updated: 2026-07-24T05:47:00+00:00

## Hana Enneagram Assessment

Hana is Omri’s public GitHub Pages Enneagram assessment and compatibility site in `gitteromri-ux/hana`, built around 108-item type/wing analysis and a full-depth 7w8 × 4w3 compatibility page ([recorded evidence](https://github.com/gitteromri-ux/hana)) (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`).

### How it works

The app uses 12 questions per Enneagram type, scores all 9 types, identifies a dominant type and wing, and presents type/wing analysis in a deployed web app ([recorded evidence](https://github.com/gitteromri-ux/hana)). The Hana compatibility branch uses a separate full-template structure for the `compat-7w8-4w3` page rather than the assessment-only flow (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`) (original session `b176fb94-d670-4bbb-98e8-068de7cc8a86`).

- **GitHub Pages required for handoff**: The usable deliverable is the live site URL, not only a public repository page; the current handoff target is `https://gitteromri-ux.github.io/hana/` and the compatibility page at `/compat-7w8-4w3/` (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`) (original session `b176fb94-d670-4bbb-98e8-068de7cc8a86`).
- **Full-template compatibility requirement**: The accepted compatibility page needs the full elaborate structure and length class of the earlier reference, not a condensed adaptation; the final verified pass reported 2,043 visible words after the short 1,014-word attempt was rejected (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`) (original session `b176fb94-d670-4bbb-98e8-068de7cc8a86`).
- **4w3 self-framing**: Omri’s Type 4 side should emphasize a strong wing 3, depth, artistic nature, a genuinely unique/genius mindset, and feelings as longing for what is missing rather than abandonment anxiety (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`) (original session `b176fb94-d670-4bbb-98e8-068de7cc8a86`).
- **7w8 partner framing**: Hana’s side should be written as a true 7w8 “Realist”: head-center, options/movement, grounded wing-8 directness, and growth toward stillness/depth, not copied from Type 8 psychology (original session `40a18e1e-6aeb-49d6-9e5a-efe9cfa8305f`) (original session `b176fb94-d670-4bbb-98e8-068de7cc8a86`).

### See also

- `entities/omri-gitter`: project owner
- `concepts/github-pages-delivery`: delivery surface rule


---

Record: `keren-or-farm-adoption-en` | knowledge last updated: 2026-07-16T10:04:00+00:00

## Keren Or Farm Adoption EN

Keren Or Farm Adoption EN is a public English adoption-page replica in `gitteromri-ux/kerenor-adoption-en`, built with 33 animal profiles and per-animal adoption forms ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en)) ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en/commit/0ac558a644e344ef335120542059dafe75117729)).

### How it works

The GitHub Pages site serves as the English version of the Keren Or Farm adoption experience while Wix-domain integration is handled separately ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en)) ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en/commit/9c50ea4dc5c24e6ca078572b1008021a5229849b)). The page includes animal profiles, package CTAs, forms, VIP/package styling, and a CEO-ready staging URL path on the client domain from the Wix session ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en/commit/0ac558a644e344ef335120542059dafe75117729)) ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en/commit/9c50ea4dc5c24e6ca078572b1008021a5229849b)).

- **GitHub Pages first, Wix path second**: The English page was delivery-ready at GitHub Pages before the Wix-domain path was finalized ([recorded evidence](https://github.com/gitteromri-ux/kerenor-adoption-en/commit/9c50ea4dc5c24e6ca078572b1008021a5229849b)).
- **Staging URL as urgent client-domain fallback**: `https://www.kerenorfarm.com/adoption-en-staging` became the CEO-ready link when production `/adoption-en` remained blocked by editor/2FA friction (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).
- **Wix Editor/API split**: Clean Wix page creation/visual embedding required Wix Editor access; API/automation attempts were not enough for the full embedded-page task in-session (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).

### See also

- `entities/omri-gitter`: project owner
- `concepts/wix-editor-publishing`: publishing constraint
- `concepts/github-pages-delivery`: fallback delivery surface


# People, preferences and cross-project operating rules

These retained records explain ownership and working constraints. They are context, not independent authorization to change any service.



## GiTA Agency

GiTA Agency is Omri Gitter’s advertising/performance agency and the party named in agency-client confirmation documents (original session `a10d679b-31c3-4f15-96b4-cb444430ea8c`).

### What they own

GiTA Agency is the agency-side entity Omri uses for client marketing, performance, and paid-media engagements (original session `a10d679b-31c3-4f15-96b4-cb444430ea8c`).

- **Rosen/eTeacher termination confirmation**: The correct document framing is an engagement between GiTA Agency and eTeacher Group regarding the Rosen Hebrew School advertiser account, ending by mutual agreement on 2026-06-01 with ongoing management returned to the client-side internal team (original session `a10d679b-31c3-4f15-96b4-cb444430ea8c`).
- **Separate recurring eTeacher brand billing**: Omri maintains French Atelier and LLA documents through `projects/eteacher-monthly-invoicing`, with separate service rows and allocation numbers rather than one combined brand invoice. (original session `6bfde4d1-02a4-44c9-8773-1bd6b8d883b6`)

### See also

- `entities/omri-gitter`: agency owner
- `entities/longevity-life-academy`: eTeacher work
- `projects/french-atelier-social-kickstart`: French Atelier campaign
- `projects/in-venture-website`: client website redesign
- `projects/club-italia-school`: online language-school concept
- `projects/eteacher-monthly-invoicing`: recurring client billing documents


## Harel Tayeb

Harel Tayeb is the CEO and public-facing media contact named in Omri’s LLA/eTeacher Group PR kit and PR-outlet campaign work ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/ded574ee23e5fac1c64fca59fde31711a9f8ab28)) (original session `403edc06-11f9-46e4-881b-aa422bec23b2`).

### Who they are

Harel’s role in the GitHub-sourced LLA PR materials is external-facing: the PR kit commit names him as CEO and media contact, while Omri is kept in a back-office role ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/ded574ee23e5fac1c64fca59fde31711a9f8ab28)). The PR campaign used Harel as the public contact while distributing the three approved article angles across owned and third-party surfaces (original session `403edc06-11f9-46e4-881b-aa422bec23b2`). The later launch brief made the rule explicit: Harel is the media-contact name for LLA/eTeacher releases and Omri must not be named as the contact person (original session `d65c9925-abe9-4a9e-8b74-826c97a8d9fa`).

### See also

- `entities/longevity-life-academy`: LLA PR context
- `entities/omri-gitter`: back-office operator
- `projects/lla-pr-campaign`: campaign surface


## Julie Gibson Clark

Julie Gibson Clark is an authority figure used in Longevity Life Academy bio-age and masterclass marketing work ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/276fe263a87671f26a226ee714361298d2601bc7)) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-review)).

### Who they are

LLA site work positions Julie Gibson Clark in a bio-age banner and identifies her as a “#2 slowest-ager” authority signal ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/276fe263a87671f26a226ee714361298d2601bc7)). Related `gitteromri-ux` repos use Julie-focused review and communications assets for LLA work ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-review)) ([recorded evidence](https://github.com/gitteromri-ux/lla-julie-communications-plan)). Her LLA role also includes on-camera masterclass advertising built around her willpower, routine, and longevity-method story (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).

### See also

- `entities/longevity-life-academy`: LLA marketing context
- `projects/lla-julie-masterclass-video`: masterclass ad system
- `projects/lla-ad-banner-campaign`: paid-media creatives


## Longevity Life Academy

Longevity Life Academy is an LLA/Longevity Academy client surface Omri supports through GitHub-hosted websites, masterclass film assets, PR materials, article/deck sites, contact-rate improvements, promo-email funnels, domain-reputation fixes, and marketing campaigns ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io)) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)) (original session `403edc06-11f9-46e4-881b-aa422bec23b2`) (original session `8a02c109-3383-4400-99a7-af3f585fc2a4`) (original session `4fca1618-75d1-4a7b-aec7-e07a13ba32c9`) ([recorded evidence](https://github.com/gitteromri-ux/lla-homepage-demo)) (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`) (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`).

### What they own

The GitHub footprint includes the `Longevity-Academy` organization, its `Longevity-Academy/Longevity-Academy.github.io` Pages root, and related `gitteromri-ux` repos for PR, film-series, Julie-review, communications-plan, redesign, and eTeacher-longevity work ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io)) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)) ([recorded evidence](https://github.com/gitteromri-ux/courtney-lla-masterclass)) ([recorded evidence](https://github.com/Longevity-Academy)).

- **GitHub Pages as public site infrastructure**: The organization site is hosted in `Longevity-Academy/Longevity-Academy.github.io`, where Omri has a large contribution history and recent banner/hero changes ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io)).
- **Hero-copy preview system**: The `Longevity-Academy` org also holds numbered preview repos for landing-page hero-copy variants, including “Live Younger. For Longer.”, “Shared Life. Shared Health.”, and “One Academy. Every Pillar of Longevity.” variants ([recorded evidence](https://github.com/Longevity-Academy)).
- **Julie Gibson Clark as authority figure**: Recent LLA site work uses Julie Gibson Clark in bio-age banner positioning and describes her as a “#2 slowest-ager” authority signal ([recorded evidence](https://github.com/Longevity-Academy/Longevity-Academy.github.io/commit/276fe263a87671f26a226ee714361298d2601bc7)).
- **Harel Tayeb as public media contact**: The LLA PR kit names Harel Tayeb as the CEO/public-facing contact while keeping Omri in a back-office role ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/ded574ee23e5fac1c64fca59fde31711a9f8ab28)).
- **PR campaign surfaces**: LLA/eTeacher PR work uses the `lla-pr-kit` repo as a controlled press-kit surface and separate PR outlet placements for three approved article angles (original session `403edc06-11f9-46e4-881b-aa422bec23b2`).
- **Press-release product facts**: The approved LLA PR brief frames the product as an 18-week, 18-session online longevity program with cohorts of 8–15, six pillars, tuition around `$289/month`, and a free Abbott Lingo CGM shipped to US students before Lesson 5 (original session `d65c9925-abe9-4a9e-8b74-826c97a8d9fa`).
- **Article deck review surface**: `gitteromri-ux/lla-articles-deck` presents 14 LLA articles in a Julie-review-style GitHub Pages deck, ranked best-first by CEO/PR-agency criteria (original session `8a02c109-3383-4400-99a7-af3f585fc2a4`).
- **Contact-rate homepage demo**: The LLA homepage demo adds a callback-time dropdown for 09:00–22:00 ET plus WhatsApp and Messenger contact options next to the lead form, preserving the form as the primary lead path (original session `4fca1618-75d1-4a7b-aec7-e07a13ba32c9`) ([recorded evidence](https://github.com/gitteromri-ux/lla-homepage-demo)).
- **Turnaround-plan deck**: The `lla-turnaround-plan` site frames the operational turnaround around storytelling videos, reactivation of 3,500 prior leads, PR credibility, higher contacted rates, night-shift calling, sales scripts, and stronger trainer/rep coverage (original session `6cc01150-c8b5-4671-93e4-e9918f2600d7`).
- **Founder email funnel**: The LLA promo-email funnel uses two gated founder LPs and four promo emails, with LP forms routed to eTeacher ProductID `26` and CampaignID `117600` for email-marketing attribution (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`).
- **Domain trust and email authentication**: The LLA site received Privacy, Terms, and Medical Disclaimer pages plus repaired footer links, while the email-reputation fix remained an ActiveCampaign SPF DNS change in Route 53 (original session `df0254fb-87b3-43cd-a27d-2d92f89f0cdb`).

### See also

- `projects/lla-s09-s10-video-delivery`, `projects/lla-julie-masterclass-video`: Courtney and Julie media
- `entities/julie-gibson-clark`, `entities/harel-tayeb`: authority and executive contacts
- `entities/omri-gitter`, `entities/gita-agency`: delivery operator and agency
- `projects/lla-pr-campaign`, `concepts/pr-placement-guarantees`: PR distribution and promises
- `projects/lla-promo-email-funnel`, `projects/lla-growth-engine`: conversion funnels and acquisition
- `projects/lla-masterclass-emails`, `projects/lla-master-delivery-hub`: lifecycle and delivery surfaces


## Omri Gitter

Omri Gitter is the owner of GiTA Agency and the GitHub account owner behind `gitteromri-ux`; he uses the account for client-facing marketing, website, and media-delivery work ([recorded evidence](https://github.com/gitteromri-ux)) (original session `a10d679b-31c3-4f15-96b4-cb444430ea8c`).

### Who they are

Omri owns delivery across his GitHub repos, which form a high-volume public portfolio of project-specific landing pages, decks, dashboards, review sites, promo funnels, and video handoffs ([recorded evidence](https://github.com/gitteromri-ux)). Repo naming alone does not establish client scope: the LLA-named S09/S10 repo also contains an unrelated personal birthday-film pull request ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/pull/1)). His active work centers on marketing websites, GitHub Pages deliverables, Wix/domain handoffs, PR/communications kits, formal client documents, CRM-connected funnels, and high-pressure video-production QA (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) (original session `83c61d68-a08a-4ce7-9665-1b84b60cb146`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit)) (original session `403edc06-11f9-46e4-881b-aa422bec23b2`) (original session `a10d679b-31c3-4f15-96b4-cb444430ea8c`) (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`).

Outside client delivery, Omri is coordinating `projects/sokolov-90-lease-renewal` as landlord. The lease source does not establish that this is his residence. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)

### See also

- `projects/lla-s09-s10-video-delivery`: main video crisis
- `entities/longevity-life-academy`: LLA client surface
- `projects/french-atelier-website`: website delivery work
- `projects/lla-pr-campaign`: PR distribution
- `entities/gita-agency`: agency entity
- `projects/sokolov-90-lease-renewal`: personal landlord contract endeavor


## Sandra Kwiecien

Sandra Kwiecien is named in the eTeacher handover as an ActiveCampaign access holder. Sandra governs copy and CRM-object changes across Omri’s LLA and French Atelier work ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/f47c0c8b)) ([recorded evidence](https://github.com/gitteromri-ux/handover-instinct-grok/blob/main/GAPS.md)).

### Who they are

Sandra governs ActiveCampaign object changes for LLA and supplies approved acquisition and WhatsApp source copy used in French Atelier campaign work ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout)) ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/f47c0c8b)).

- **ActiveCampaign changes require Sandra**: New ActiveCampaign objects cannot be created without Sandra, and protected fields `214–220` cannot be deleted without approval ([recorded evidence](https://github.com/gitteromri-ux/lla-course-checkout)).
- **Original copy controls downstream length**: The Julie three-tier lifecycle system keeps all emails at or below Sandra’s original word count ([recorded evidence](https://github.com/gitteromri-ux/lla-masterclass-emails-3tier/commit/067a6c3c)).
- **Real campaign source over invented copy**: French Atelier’s social delivery uses Sandra’s real acquisition-drip emails and WhatsApp broadcasts with their actual banner imagery rather than fabricated replacements ([recorded evidence](https://github.com/gitteromri-ux/french-atelier-social-kickstart/commit/f47c0c8b)).

### See also

- `projects/lla-masterclass-emails`: approved lifecycle copy
- `projects/french-atelier-social-kickstart`: source campaign material
- `projects/lla-course-checkout`: CRM governance boundary
- `projects/lla-julie-invitation-blast`: segmented school-email handoff


## Address recurring process failures

The user wants answers to process-failure complaints to address the recurring failure itself rather than substitute another tactical plan. (original session `59596b49-4843-4756-b08f-17722a531c89`) The user rejects unsolicited CEO messages, support referrals or consolation documents as substitutes for addressing that complaint. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)


## Concise practical communication

The user prefers concise, clear responses without filler, using simple nontechnical language for practical instructions and preserving the requested format (original session `cda24151-3fe4-426e-bbbe-ed83eb6f75db`) (original session `943d2b2f-7019-4c73-abd9-5254b34d8819`).

For campaign checks, the user wants readable in-chat tables at the requested ad-set or ad grain and period, not rendered charts, design work, or dense prose; the latest explicit format puts daily budget in column two beside each set or ad, ahead of sales, cost per sale, spend and remaining metrics. The user requires explicit learning states separate from delivery status, and distinct CRM-paid, raw-event and Meta-attributed sales counters. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) (original session `41572080-cfcc-4c6d-af2a-b8f571a26054`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `59596b49-4843-4756-b08f-17722a531c89`)


## Current authorization required

The user does not want work started, resumed, published, scheduled, submitted, or mutated in external software without clear current authorization; for unfamiliar account work, they require existing records researched and screenshot previews approved before anything is saved, issued or sent. (original session `373062cb-3ec9-424b-8613-f8478d1f7ea9`) (original session `1ad4b3ec-9b30-4a28-95f2-9f4e2101a5dc`) (original session `3e8a6838-f72a-4a17-8c7a-a7018d3a2684`) (original session `5608d58e-c5f5-447c-9bac-d0dd37c3cd5e`) (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`) (original session `126994a0-ae37-4d2b-9e2c-b1c3ca4417ae`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) This includes footage edits, evidence claims, paid-media settings, analysis after a hands-off instruction and publication to a preview repository/URL; a stop halts work, and a materially different implementation needs fresh approval. (original session `3e8a6838-f72a-4a17-8c7a-a7018d3a2684`) (original session `5608d58e-c5f5-447c-9bac-d0dd37c3cd5e`) (original session `05caf531-03f3-4736-8d9c-214938ba4f1c`) (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) For Meta, the user explicitly includes exports, uploads, audience creation/edits/deletion, targeting and cleanup in the approval boundary; a separately approved read-only lead export for local matching does not authorize write-back or activation, and a page/screenshot inspection does not authorize production form submissions, test CRM records, checkout progression or cleanup merely because no charge occurs. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)


## Direct working deliverables

The user expects the agent to execute technical work rather than transfer tool operation back to them, and deliver working public links or downloads rather than status messages, workarounds or chat-only descriptions (original session `cf7d2e65-ded5-477c-a3fa-5af60845b165`) (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) (original session `ba090ec8-18e5-412c-8665-2deba042703c`).

When a client deliverable has already been circulated, the user requires revisions at that original public link, with fresh cache-busting queries for revised decks and matching downloadable formats rather than a replacement base URL (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `ad99e93f-fc49-4bda-be84-3501fced7806`).

The user wants short WhatsApp handoffs as ordinary plain-text content with full working URLs and the exact approved wording, not code-styled text in the message or links replaced by inaccessible citation labels; the delivery needs an immediate copy control rather than manual editing. (original session `ad99e93f-fc49-4bda-be84-3501fced7806`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) For cross-platform social handoffs, the user wants complete Facebook and Instagram text together in one copyable block with clear separation, while bio fields stay separate. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

The user distinguishes revisions of a shared review from genuinely new deck alternatives: shared reviews stay on their established link, while a new design receives its own open GitHub link rather than being relabelled as a round of the old deck. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `5fc1c29a-a40f-4e3a-8017-9a20d981b89f`) (original session `12e9ff81-d844-4ea6-aaa4-0863ca1d4b53`)


## Executive deck clarity

The user wants executive decks to state the conclusion in literal, very large headlines, keep supporting text sparse and readable, and move from macro strategy to operating detail. Visual polish must strengthen comprehension rather than replace the requested management logic (original session `56d2ef86-ea05-43d6-b6f2-e09d82fcf16a`) (original session `44859035-df25-47a4-bd36-f12b628efdb6`).

The user requires actual performance to be verified and clearly distinguished from targets, not replaced with targets alone or internal “reported/not confirmed” labels in board-facing copy (original session `ad99e93f-fc49-4bda-be84-3501fced7806`).

The user requires audience slides to distinguish observed conversions, targeting and inferred motivations, with separate products and lead/buyer populations. Clear executive bullets and readable graphs must answer the board's actual questions rather than substitute invented persona labels or imply an unverified funnel. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)

For rehearsal documents, the user wants a plain chronological production timeline with large readable stage cues and direct jumps from speaking cues to exact preserved scripts, rather than a moderator-only framing or invented management framework. (original session `97ea884b-02ca-40ad-bba8-29fb41a5f490`) (original session `0425b0f4-2e0f-4068-92f5-25673f9541f0`)


## Immediate urgent acknowledgement

The user expects immediate responses to stop, status, and urgent ETA requests before any longer execution resumes (original session `cda24151-3fe4-426e-bbbe-ed83eb6f75db`) (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`).

The user requests a deployable emergency mode that responds within 60 seconds, minimizes mistakes and follows the literal urgent ask instead of looping or expanding the task. The assistant's proposed blanket suspension of verification is not a user-approved rule. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)


## Literal scope and source fidelity

The user requires exact adherence to approved scope, source material, wording and design; silent substitutions, changed versions, removals and partial delivery are unacceptable, and source identity must be verified before production begins. (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`) (original session `3e8a6838-f72a-4a17-8c7a-a7018d3a2684`) (original session `a6c0ef82-b281-444d-8873-949c7b0db941`) (original session `95cc26e4-8e21-4311-b006-486e8dbaa042`) This includes brand-specific buyer sources: the user rejects unrelated brands’ customers or unverified leads substituted for purchasers to meet platform thresholds. (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)

Explicit “only” requests and output exclusions are hard constraints, shared copy corrections apply across every requested audience segment rather than just the example shown, and placement formats of one creative concept must count as one ad rather than inflated distinct ads. (original session `32a35d34-ee27-4481-8d88-0843d24f7ad7`) (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `39e18618-574d-4840-99a7-54fb2c7b8b30`)

The user requires mobile adaptation to preserve the approved design and visible controls, including floating CTAs and promotional strips, rather than hiding elements or redesigning to make them fit (original session `ad99e93f-fc49-4bda-be84-3501fced7806`).

The user distinguishes a tone/style reference from content to reuse: explicitly rejected topics must not return simply because they appear in a supplied reference. A requested exact-design comparison must preserve the reference's actual styles and side-by-side view, not replace it with a generic approximation. (original session `f55de7df-62e4-4685-aa1e-d2280ec69eff`) (original session `658b2028-3543-446e-8b94-2c5db8006a50`)


## No subpar alternatives

The user expects quality-critical outputs to meet the stated standard and rejects compromised fallback versions presented as acceptable deliverables (original session `00f1fab4-d98f-4d8e-94cf-489036adba6e`) (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`).

For premium web work, the user expects a visually complete mobile and desktop experience with large legible type, aligned pricing and clear tier benefits, not an overflow-only repair presented as a redesign. (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)


## Plan and ETA first

The user wants a complete staged plan with an accepted ETA for each phase before execution, truthful pacing against it, and immediate disclosure whenever the timeline changes (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `00f1fab4-d98f-4d8e-94cf-489036adba6e`) (original session `a6c0ef82-b281-444d-8873-949c7b0db941`).


## Premium design guardrails

The user wants compact, sleek layouts with large readable text, factual content and clear hierarchy rather than excessive gaps or pill badges. (original session `11b3a24a-1d1c-4b1f-8788-81abd1a9fe32`) The user rejects all-caps display words, decorative dashes and generic AI promotional language, and wants approved headline concepts preserved rather than replaced; course-page headings should explain learning literally rather than use slogans or repeat one card template. (original session `642f6ef0-4790-463c-a38d-deb60bbbcb7a`) (original session `c3a19142-607c-4005-aeda-8c65494e6bd5`)

The user wants introductory prices dominant without hiding the remaining installments or total commitment in unreadable text. Phone comparison views must preserve the requested side-by-side cards, compact height and readable brand-colored CTAs; merely increasing desktop pixel sizes does not satisfy phone readability. (original session `658b2028-3543-446e-8b94-2c5db8006a50`)


## Reuse existing context

The user expects independent use of existing context, prior uploads, and available assets rather than being asked to repeat work or re-upload material; an already-agreed chart should be resent immediately from history, with fresh live-state checks separate rather than delaying it. (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `d671ac39-6efd-4bed-b813-20a26fa5b2ab`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

The user requires recommendations to combine current configuration, recent results, the mission and previously rejected tests rather than recycle disproven proposals or treat poor historical performance as a ceiling. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) Campaign diagnoses must use relevant account history and actual delivery evidence rather than generic learning-reset explanations; targeting advice must examine actual lead and purchase outcomes by age, creative, placement and settings, not spend alone. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`) (original session `1ad26cec-e6d7-4c05-a960-9620bad9b66a`)

When a promised repair remains incomplete, the user expects the assistant to recover the existing agreement and tests and finish that work, not restart the brief or repeatedly ask the user to supply already-established context. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)


## Simplest fast quality path

The user prefers the fastest and simplest viable method that preserves every required quality standard over unnecessarily complex or slow approaches (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `720bb025-55fc-453c-a4f8-ae5fe4b3bde1`).

The user rejects automatic lengthy work budgets for small edits and expects planning and execution to be proportionate to the actual task (original session `ad99e93f-fc49-4bda-be84-3501fced7806`).


## Tool-verified completion

The user requires tool recommendations, capability statements, completion claims, research results, and audits to be backed by concrete, visible verification against every stated hard requirement before purchase, execution, or delivery (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`) (original session `3e8a6838-f72a-4a17-8c7a-a7018d3a2684`) (original session `65862fd2-e80c-420b-aad6-866d3e19c710`) (original session `7873ebd0-a188-4e44-97a6-40fa2af1e3a1`).

The user expects checkout-readiness claims to cover the named devices and failure paths, not just successful form rendering elsewhere, and rejects repeated third-party retest loops as a substitute for the agent owning its audit. (original session `a1dcbba2-93be-47ac-946a-6e2ae3b87d44`)

The user requires audit reports to distinguish purchase events, orders and unique buyers, rejects classifying repeated purchases as accidental duplicates without evidence of intent, and rejects causal learning/reset or budget explanations that are not established by the observed data. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

The user expects proactive investigation, fixes and concrete proof rather than disclaimer-only updates that require a predictable follow-up. Evidence must match the requested outcome: event receipt, preview clicks or URL tags are not substitutes for a Purchase credited to an ad set; a direct-URL emulation is not a real Meta-origin click, checkout captures do not replace website screenshots, and a public Ad Library redirect does not establish paid-feed attribution or physical-device testing. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`) (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

The user assigns the assistant sole end-to-end attribution ownership before a campaign launches and treats unresolved live tracking as an emergency, not a user-operated debugging assignment. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)

For enrollment repair, the user requires actual course assignments and access to be checked, not just returned student/order IDs; duplicate-write guards and pending-status messages do not fulfill the original repair agreement. (original session `50d09f1f-0a80-4b26-b0d9-ffcbc97f0f44`)

The user requires present-day roster claims to distinguish live retrieval from historical backup files, and local-browser changes to be distinguished from what is actually visible in another presenter's already-open tab. (original session `8904dadb-53f9-4ac0-ab1b-550470b3bccf`) (original session `858958e0-bbbf-493d-887e-0365bd6c7f0d`)


## Use the best available tools

The user expects the agent to evaluate and use the strongest available connected tools or capabilities before starting when they materially improve the result (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `720bb025-55fc-453c-a4f8-ae5fe4b3bde1`).

The user explicitly requires innovative specialist companies and proven external solutions to be investigated before declaring an approach impossible or repeating a rejected workaround; the survey is not limited to the agent's built-in or already connected capabilities. (original session `5f70d990-447e-43ce-9ade-7e29fbae7c02`)


## GitHub Pages Delivery

GitHub Pages is a public handoff surface for Omri’s client websites, media galleries and conversion-funnel previews. It presents the deliverable in a browser rather than exposing only a repository directory or binary-file preview. (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`) (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`)

### What it is

The pattern uses public GitHub repos plus GitHub Pages landing pages exposing content, media and download buttons. Repository storage and browser playback are separate interfaces; direct file availability does not establish inline playback. (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794))

- **Landing page over raw media links**: For LLA video files, the requested surface is a normal page with videos and download buttons instead of raw media URLs or GitHub file pages. (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`) ([recorded evidence](https://github.com/gitteromri-ux/lla-s09-s10-downloads/commit/aacf8abbf21e98e1ea93d97e0458fbb73f7c9794))
- **Fallback for Wix constraints**: For Keren Or Farm, GitHub Pages supplied the English adoption page while client-domain Wix integration was blocked by editor/2FA constraints. (original session `a669e25b-f59e-4b86-8dec-1524935234b3`)
- **Preview-to-production bridge**: For LLA promo-email work, GitHub Pages held the CEO-review hub, then the approved LPs moved under `www.longevitylifeacademy.com/lp/` paths. (original session `9c82dce7-0c87-4dfa-84dc-e8eead87f269`)
- **Public client-site handoff**: Personalix uses a public GitHub Pages website as the client deliverable, with its repository as secondary source storage. (original session `16118e53-80d5-42a2-9103-b85f2c35bc08`)

### See also

- `projects/hana-enneagram-assessment`, `projects/personalix-website`: public application and website handoffs
- `projects/lla-s09-s10-video-delivery`, `projects/lms-image-pack`: video and image delivery
- `projects/keren-or-farm-adoption-en`, `concepts/wix-editor-publishing`: Wix integration and fallback
- `projects/lla-ad-banner-campaign`, `projects/lla-pr-article-ads`: browser-ready campaign galleries


## PR Placement Guarantees

PR placement guarantees are the working distinction Omri uses to decide what can be promised to a CEO or board in LLA/eTeacher press-release work: a direct, contractually guaranteed outlet page is different from indexing, reach language, likely syndication, or earned editorial coverage (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `a704b693-d53d-45da-8a69-6007963f913f`).

### What it is

The concept separates paid PR outcomes into concrete promise levels so sales/board language does not overstate what the package can deliver (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `a704b693-d53d-45da-8a69-6007963f913f`).

- **Direct guaranteed link**: A vendor explicitly promises a live outlet URL or refund; this is the only category safe to promise as a named placement (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `a704b693-d53d-45da-8a69-6007963f913f`).
- **Likely syndication**: A guaranteed feed may syndicate to Yahoo, Business Insider, local TV affiliates, or similar outlets, but the downstream URL is not individually contracted and should not be described as guaranteed (original session `752912d7-d62b-4ce4-9009-358c40fc0301`).
- **Indexing/search visibility**: Google/Yahoo/Bing indexing means the release can be found in search, not that the release has a publishable Yahoo/AP-style article URL (original session `a704b693-d53d-45da-8a69-6007963f913f`).
- **Earned editorial coverage**: Forbes, Fortune, Newsweek, TechCrunch, and comparable newsroom coverage cannot honestly be guaranteed through low-budget self-serve PR products; guaranteed claims here are treated as scam or advertorial/contributor-risk territory unless the exact product and label are verified (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) (original session `a704b693-d53d-45da-8a69-6007963f913f`).
- **Disclosure label**: Placement must also be classified by its visible rendered-page disclosure: paid press release, sponsored content, partner disclosure, contributor/wire byline, mild third-party disclaimer, or no visible label (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).

### Why it matters

- **Promise only contract language**: The LLA PR kit’s `promises.html` page labels outlets as promise, likely, or list-name reach so Harel/CEO-facing language does not convert vendor marketing logos into false commitments (original session `752912d7-d62b-4ce4-9009-358c40fc0301`) ([recorded evidence](https://github.com/gitteromri-ux/lla-pr-kit/commit/45fe370)).
- **Budget expectations**: EIN Basic produced useful wire/live-copy links but did not satisfy the goal of guaranteed reputable named links; the decision frame moved toward higher-tier or à-la-carte packages when the deliverable is a board-proud direct outlet URL (original session `a704b693-d53d-45da-8a69-6007963f913f`).
- **Checkout verification before stakeholder promises**: Vendor marketing pages are not enough to lock a CEO-facing price or outlet promise; the product must be confirmed inside the logged-in checkout because PRNow’s actual account flow contradicted earlier claims about separate Yahoo/MarketWatch/Business Insider article purchases (original session `e26c1102-615f-4caf-9487-b06bd468fbad`).
- **Credit wallet is not a payment-link substitute**: A PR platform credit balance can fund submissions, but it does not necessarily produce separate shareable card links per outlet. Treat “top up credits,” “credit-funded submission,” and “checkout link” as separate mechanics (original session `e26c1102-615f-4caf-9487-b06bd468fbad`).
- **Outlet rules can vary by wire**: StreetInsider and similar destinations may label lower-tier feeds while presenting major-wire copy with only a wire byline; verify the exact distributor-to-outlet path rather than assigning one permanent verdict to the outlet (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).
- **Rendered-page inspection beats text extraction**: Benzinga’s `Partner Disclosure` badge was missed in text extraction, and Digital Journal’s sponsored-content requirement contradicted an initial clean-page reading. Purchase decisions require visual page and policy checks (original session `db81b128-3dcf-4218-98d4-ff372c65de1e`).

### See also

- `projects/lla-pr-campaign`: campaign application
- `entities/harel-tayeb`: CEO-facing promises
- `entities/longevity-life-academy`: client context


## Video Quality QA

Video Quality QA is the media-delivery standard Omri applies to client videos: resolution, sharpness, color, audio, lipsync, playback, camera framing, and delivery surface must all survive final export (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `720bb025-55fc-453c-a4f8-ae5fe4b3bde1`).

### What it is

The QA bar combines technical checks with perceptual checks: real source resolution, output dimensions, bitrate/codec, audio duration and drift, visual sharpness/color, UI cleanup, and whether the final file looks client-ready on the intended viewing surface (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `8d7a6c0a-0ccf-41ef-994d-3c8f621afc4a`).

- **Source ceiling before quality promise**: Teams/cloud-camera tiles with low real pixel counts cannot be honestly promised as studio-quality 4K without either better source material or AI super-resolution risk (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `00f1fab4-d98f-4d8e-94cf-489036adba6e`).
- **Audio and sync are release blockers**: Omri treats audio playback, lipsync, drift, and sound quality as critical deliverability requirements, not secondary polish (original session `55a60e33-9e3b-46be-8dec-1524935234b3`) (original session `81c1193f-08f7-49f7-974d-a55f605f1ec0`).
- **Delivery compression can undo render quality**: The LLA enhanced part lost perceived quality after re-encoding smaller for GitHub delivery, making final-delivery encoding part of QA rather than a separate upload step (original session `720bb025-55fc-453c-a4f8-ae5fe4b3bde1`).
- **No unwanted scene elements**: Full-frame speaker-only output means no Teams labels, buttons, desktop UI, other participants, or unwanted camera angle artifacts (original session `55a60e33-9e3b-46be-8dec-1524935234b3`).
- **Compliance and perceptual audits are separate gates**: Checking every brief item does not replace watching as a cold viewer. A separate CEO/viewer pass tests repetition, transition artifacts, ending coherence, caption contrast, and audio headroom before release (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`).
- **Audit against the approved sequence, not the latest render**: A technically clean render still fails if cards, b-roll, or approved footage are out of order. Runtime inspection must compare every segment to the user’s exact source instructions and verify that one-use footage is not duplicated (original session `b5d6efa8-ebd4-4446-89ff-c1f49f522a83`).
- **Visual meaning must match the surviving voiceover**: A cut can remain lip-synced yet still fail when visuals are removed while their narration remains. QA must check semantic shot-to-voice alignment, not only timestamps and waveform correlation (original session `3e0823c6-e753-4e0f-afdd-5e0249cfb902`).
- **Normalize speech before ducking music**: Near-silent camera audio can prevent ducking from engaging and cause mastering to lift the music instead of the voice. Speech gain staging, compression, and EQ must precede the music-ducking pass (original session `6d5a72f3-5c7d-4eb6-9d85-5f22afe19f9b`).
- **Whole-piece review precedes component QA**: A forced full-film viewing at the opening, quarter points, and ending must happen before shot-level inspection so pacing, narrative, transitions, and cumulative repetition are judged as a film rather than isolated frames (original session `dacc2b10-1cb7-4e32-b741-2782ca62d78b`).
- **Audit evidence cannot be relabeled**: Unresolved defects remain failures until the underlying media is re-inspected; renumbering or rewriting an audit list as PASS without frame, audio, and timeline evidence invalidates the release (original session `b706d6eb-7dfd-4666-9abf-0066954e5635`).
- **Faststart is a playback gate**: Delivered MP4s must place the `moov` atom before media data so GitHub/browser playback begins promptly; resolution and codec checks alone do not prove browser readiness (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`).
- **Source resolution governs the export claim**: A 4K requirement means rebuilding from camera originals and validating `3840×2160`; a 1080p master cannot satisfy the requirement through labeling or ordinary resizing (original session `aef895b6-3270-4889-8b0d-efa8a3c4a061`).
- **Source lineage is part of QA**: Storyboard deliveries must identify the exact original source beside each scene and preserve talent/version pairing; a plausible visual substitute or board from another cut is a failed match (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`) (original session `2a307fd5-0351-4a12-b6ec-591ae61de6c7`).
- **Machine gates precede completion claims**: Multi-element handoffs use a source manifest/EDL and mechanical checks for missing files, empty beats, audio, resolution downgrades, render-derived sources, banned assets, and dead links before perceptual review (original session `8b3275ab-0b98-402c-be96-825b3eeb0b91`).

### See also

- `projects/lla-s09-s10-video-delivery`: main video project
- `projects/lla-julie-masterclass-video`: Julie edit system
- `entities/omri-gitter`: QA owner


## Wix Editor Publishing

Wix Editor publishing is the constraint Omri hit when trying to place a GitHub-built English adoption page onto a client Wix domain during a CEO deadline (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).

### What it is

The task required either an embedded Wix page, a clean redirect, or a client-domain staging path for the English adoption page (original session `a669e25b-f59e-4b86-8dec-1524935234b3`). In-session API exploration and browser automation did not provide a clean full replacement for the Wix Editor UI, so the immediate usable solution became a staging redirect URL plus the already-live GitHub Pages site (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).

- **Editor UI is the clean page path**: The clean embedded-page workflow required access through the Wix Editor UI rather than the available API path used in-session (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).
- **Staging redirect as fallback**: The accepted urgent link was `https://www.kerenorfarm.com/adoption-en-staging`, with production `/adoption-en` deferred until 2FA/editor access cooperated (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).
- **2FA/browser loops are delivery risks**: Google/Wix 2FA prompts and cloud-browser delays consumed the deadline window and should be treated as launch blockers for future Wix tasks (original session `a669e25b-f59e-4b86-8dec-1524935234b3`).

### See also

- `projects/keren-or-farm-adoption-en`: affected project
- `concepts/github-pages-delivery`: fallback site


# Source-review reconciliation notes

These notes preserve the difference between source inspection and outcome verification.



## Source Review: 2026-10-15

### Evidence checks

- **Julie acquisition:** Checked Set 03 targeting/creative IDs and final Set 05 lowest-cost readback against trajectory turns 112, 155 and 158. Set 04's $550 readback is turn 139. Later explicit approvals supersede historical guardrails; no deployment of the proposed operating automations was established. (original session `219ddd45-d288-402e-b1fc-d82739bfd55b`)
- **Order identity:** Checked order 8052695, ad 52672751173028 and Set 01 mapping against actual CRM fieldValues and Meta results in turn 6. The record still carries an abandoned/no-payment field; it was not promoted to settled revenue. (original session `59596b49-4843-4756-b08f-17722a531c89`)
- **Tracking:** Checked merge a188c6c, production release and accepted diagnostic PageView/ViewContent receipts against turn 41. The connector's PR record corroborates the patch subject, not universal production certification. (original session `d3d47d7a-62e6-4d27-adb4-03022ce4e75c`) ([recorded evidence](https://github.com/Longevity-Academy/julie-masterclass/pull/1))
- **Masterclass offer:** Checked archived three-tier dates/prices, later public-card/coupon removal history and the final live workbook row count. Kept historical offer facts scoped; replaced the stale live-three-tier lede and earlier 26-person roster report. (original session `f0880387-3aa3-4161-85ac-890ecca87e46`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `a572ab4f-2086-4f3c-b6cf-da71015aecb8`)
- **Invitation emails:** Checked audience variants, automatic-discount wording and original-link correction in the session. The separate clone session explicitly excluded email changes; sending remains unproven. (original session `5619952e-b572-4412-9ea7-6df3c8e233b1`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`)
- **Community clone:** Checked hidden-link/isolation claims against clone publication and mobile phone-guard/design handoff turns. The browser-local timer is not a global deadline, noindex is not privacy, and an undeployed branch is not a live fix. (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)
- **Deck and communications:** Checked the user's supplement exclusion, source URL and no-Julie-photo correction, plus the earlier final-ask structure. The calendar connector supplies an agenda only, not meeting attendance or deck acceptance. (original session `2c8c0ade-c92e-4617-931f-25b87258ae72`) (original session `d1a1f25c-b0cd-4301-a437-3188d0c71824`) ([recorded evidence](https://www.google.com/calendar/event?eid=cXIwZnVtcTNmZG8zZWZqcXA2czlvcHEzcTAgZ2l0dGVyLm9tcmlAZ2l0YS1hZ2VuY3kuY29t))
- **Lease and Omri:** Checked tenant names, requested clauses, reported term/rent, final unrequested appendix wording and DocuSign recipient readback. Sent status is not completion; landlord coordination does not establish residence. (original session `e2f0868a-6f06-45ea-8d21-3691f3a0555a`)
- **Preferences:** Checked the literal metric-order correction, configuration-aware history correction, whole-design rejection and explicit rejection of consolation deliverables. Merged three existing topics and created one distinct process-complaint rule; no sensitive personal circumstance was extracted. (original session `59596b49-4843-4756-b08f-17722a531c89`) (original session `15bf3163-8820-48f6-b442-23f2bf174aaf`) (original session `adbe076f-a5b4-4b36-99ec-4bf8dc9119b6`) (original session `8a2c0e39-213b-40bc-8abd-ba31f17a5683`)

### Coverage and limitations

The connector probe used authorized read-only GitHub and Google Calendar/Gmail tools. Older handovers did not override fresh session readbacks. Mailbox observations lacking canonical record URLs were not promoted as connector-sourced wiki claims. The ephemeral probe and preference-candidate handoffs were consumed and removed.

Israel-clock events after midnight on October 16 occur inside the supplied October 15 UTC/Los Angeles session window. The probe's blanket exclusion of October 16 was not applied to directly observed session trajectories.

The graph review found no broken links or unindexed subject pages. Reciprocal navigation was maintained for the new subjects; the pre-existing LLA and GitHub Pages hubs have more incoming neighbors than half-incoming reciprocity can represent within the six-link See also ceiling.


## Source Review: 2026-10-26 Continuation

### Coverage and limits

Exactly one read-only connector probe covered authorized GitHub and gcal sources, using the current user's known identifiers and inherited open questions. Its root handoff was consumed and deleted. This review preserves retrieval leads and evidence boundaries; it is not a current CRM, payment, Meta or signature audit.

Seventeen new/extended source summaries were saved in `dream_output/session_summaries/`. Conversations and targeted protobuf turns, not existing wiki text or derived notes, established their outcomes.

### Canonical source records

- [French write-guard commit](https://github.com/gitteromri-ux/french-atelier/commit/3e7767bed72aa6bcfdc8146cf866e683e011fdc6): pending completion and suppressed ambiguous replay; it predates the later session's actual assignment repair.
- [Historical syllabus openers/closers](https://github.com/gitteromri-ux/lla-masterclass-syllabus/commit/7598554002d419586722ccc8ab69dbceb7595ad4): source options, not final V45 or closer acceptance.
- [November lifecycle revision](https://github.com/gitteromri-ux/lla-masterclass-emails/commit/ebbe0a3c62c68ff2468c10ce32e0262b322cec02): recording access, JULIE249 and JM-X4 source; not email send/acceptance or commercial approval.
- [Merged masterclass tracking PR](https://github.com/Longevity-Academy/julie-masterclass/pull/1): implementation history, not a new transaction.
- [Historical production meeting](https://www.google.com/calendar/event?eid=cXIwZnVtcTNmZG8zZWZqcXA2czlvcHEzcTAgZ2l0dGVyLm9tcmlAZ2l0YS1hZ2VuY3kuY29t): October 15, organized by `[email redacted for public handover]`; not new activity or presenter approval.
- [September report artifact](https://github.com/gitteromri-ux/lla-gal-september-2026/commit/4461984edb9b29931712dec7d6c207f77500c913) and [Meta reporting artifact](https://github.com/gitteromri-ux/latest-meta-ads/commit/49378cc43d7fc16623a4821aacc776078d3f4c7f): not processor/order reconciliation.

### Mail retrieval leads

The connector returned no canonical mail URLs. IDs below are retrieval leads, not invented URL citations. Support outcomes used on subject pages are independently present in session `2d117a2b-b81b-41f1-b94f-74e5ccf0c6f8`.

| Record | Message / thread | Evidence and remaining gap |
|---|---|---|
| Ubertesters, October 25 08:41:13 UTC | `1a17238c01cc0c95` / `1a16abdd031b4a6f` | Ran Rachlin `[email redacted for public handover]` says the three-tester project is below their managed-project scale; not completed device/paid-feed testing. |
| Prior support adjustment | `1a16ed9ad002371f` / `1a16e6e1a1841272` | Reports 71,349 returned credits for task `219ddd45-d288-402e-b1fc-d82739bfd55b`; no independent balance receipt. |
| New support adjustment, October 26 10:37:35 UTC | `1a177c97c4d8557d` / `1a154f02b93d3b8e` | Reports 3,039 credits posted for task `f3ef654d-0617-422d-b1f3-b1893a2ce623`; 0.75 difference from the 3,039.75 offer remains disputed. |
| Support clarification, October 26 10:49:23 UTC | `1a177d44d33d6514` / `1a154f02b93d3b8e` | Confirms the task-specific posting does not resolve broader demands. |
| Partial account view, October 26 10:48:42 UTC | `1a177d3aac26ec24` / `1a0ebf69f510ed0c` | View covers only 9/129 tasks and 9/763 grants; not a full account ledger. Secondary account `[email redacted for public handover]` ownership verification remains open. |
| July task lookup | `1a177d3d16cb0cc8` | Task `81c1193f-08f7-49f7-974d-a55f605f1ec0` recovered; no final 2,657 reimbursement or separate 10,000 compensation decision. |

### Reconciliation boundaries

- French production course-assignment responses and seat changes are stronger evidence than the older guard commit, but do not establish learner login, duplicate removal, refund, processor settlement or Purchase deduplication.
- Authorized French budget writes have API readbacks; blocked Julie budget writes and a saved follow-up schedule do not establish application or later scheduled execution.
- The latest closer lighting request is trajectory-only and ends with generation still running; the indexed final publication is an earlier round.
- Saved workbook cell/formula readbacks support the populated row, not Gal delivery or the unresolved weighted CPA/profit cells.
- No current VIP roster, final lease certificate, PRNOW receipt, independent paid-device testing or full settlement ledger was retrieved.


## Source Review: 2026-10-27

### Scope and reconciliation

- Consumed exactly one read-only connector probe. It searched gcal mail/calendar and GitHub through gh; no external state was changed.
- The apparent $149×5 versus $79-plus-four-$169 conflict is scoped to different repositories. Session c3a19142-607c-4005-aeda-8c65494e6bd5 identifies `Longevity-Academy/blueprint-attendees-7q4x` as the branded repository and establishes explicit approval of the latter offer. The probe inspected the older `gitteromri-ux/lla-masterclass-attendees` clone. Do not elevate the older clone over the user's approval or treat either source tree as independent payment/deployment proof.
- November IDs/dates are corroborated by source configuration, not by calendar events or an independently retrieved CRM availability response. Session 25a94f9a-18d5-4f2d-aeef-e7a40f4d97c2 supplies browser-audit evidence and the unresolved final branded mobile build.
- The final turn in that trajectory requests permission for one marked unpaid production QA order. No recorded response grants permission or completes that provider-screen check.

### Canonical source records

- Approved schedule: https://github.com/gitteromri-ux/lla-course-checkout/commit/ac35c2874e54bcc2b67f14beaff4ed8c900f9962
- November class labels and preserved CRM identifiers: https://github.com/gitteromri-ux/lla-course-checkout/commit/1eb51fef8d87c807986880f455ad6e27f176d929
- Pacific-label mobile source repair: https://github.com/gitteromri-ux/lla-course-checkout/commit/6c27b2fff1d9bcaeeb8fb8687470ecc87b9b2de0
- V46 deck assets, build sources, order lock and PPTX: https://github.com/gitteromri-ux/lla-masterclass-syllabus/commit/a6f832b4e0c45ce38d37059f40f1de162b3c48da
- Older clone/expiry evidence: https://github.com/gitteromri-ux/lla-masterclass-attendees/blob/main/blueprint/index.html ; https://github.com/gitteromri-ux/lla-masterclass-attendees/blob/main/blueprint/assets/lla-promo.js ; https://github.com/gitteromri-ux/lla-masterclass-attendees/blob/main/attendee-form.js
- Q&A queue/timer synchronization source, not final user acceptance: https://github.com/gitteromri-ux/julie-live-qa/commit/9d15e1b2d0e9643c849a69d599d4da2a76ca6263
- Older dashboard snapshots, not audience-sync execution: https://github.com/gitteromri-ux/latest-meta-ads/blob/main/index.html ; https://github.com/gitteromri-ux/lla-marketing-dashboard/blob/master/campaign_live.json

### Mail retrieval lead

- Source gcal; email_id and thread_id both `1a17d3dd6b20bdb3`; sender `Julie Gibson <[email redacted for public handover]>`; recipient `[email redacted for public handover]`; timestamp `2026-10-27T12:02:33+00:00`; subject `Masterclass deck, my comments`.
- Retrieved body requests a daily mobility-and-balance block first, preferably “mobility & balance while tea brews” on slide 17, and links https://gitteromri-ux.github.io/lla-masterclass-syllabus/slide-canvas/v46/ .
- No canonical email URL was returned. Kept as a retrieval lead, not an independently URL-cited wiki outcome or proof of final deck acceptance.

### Unclosed evidence gaps

- Calendar searches returned no matching events; absence does not establish inactivity or unavailable cohorts.
- No evidence of exact CRM Member ID/StudentId equivalence, complete October 26 roster or WhatsApp reminder delivery.
- No purchaser twice-daily sync configuration, scheduler or execution logs. Old snapshots dated October 18/October 3 do not establish current audience state.
- Bounded GitHub PR/release searches returned no new matching PR or Release objects. A broader author search found https://github.com/Longevity-Academy/julie-masterclass/pull/1 updated October 15, outside the window. Neither result measures all work or production releases.
- No independent settled-payment, refund/lease completion, real paid-feed attribution or physical-device purchase evidence. Existing daily open questions remain unresolved unless the source-specific update explicitly narrows them.


# Prior transfer README, historical 24 September

This README is retained for continuity. It is not an assertion that the old transfer's access or completeness claims remain valid today. Its old navigation instructions are historical, not the current handoff procedure.


## OMRI GITTER → SECOND GITA MAX USER: FULL HANDOFF BRIEF

Source account: [email redacted for public handover] (blocked for the month, >6k spend). Exported 2026-09-24 18:35 IDT.

### What is in this export

- knowledge/ : Brain wiki: index.md, projects/, entities/, concepts/, learnings/, preferences/ (12 non-negotiable operating rules)
- notes/     : distilled user-stated facts (preferences, projects, work)
- sessions/  : sessions_index.md + asset_index.md + 25 full Computer transcripts (conversation.md) with summaries and produced files (videos, zips, images)
- changelog.md

### How to load it in the new account (1 second each)

1. Open the new account → create a Project → Files → upload this whole folder (or the ZIP).
2. Paste PROJECT_INSTRUCTIONS.txt (in this folder) into the Project instructions field.
3. Turn on Project Brain → Update now. The wiki rebuilds from knowledge/ + sessions/.
4. First prompt in the new account: paste FIRST_PROMPT.txt.

### Live Computer sessions (deep links: open from any account invited to the handoff Project)

- https://www.perplexity.ai/computer/tasks/c13c884d-4b6f-46da-ac47-0f64d9472631: 2026-09-23 08:10 UTC → 2026-09-23 08:44 UTC: Okay, going to my Gmail. Gitter, I'm reading gmail.com, gitter.omri, you know, y…
- https://www.perplexity.ai/computer/tasks/49da238d-ec07-4c74-85c2-42e13984b328: 2026-09-22 16:35 UTC → 2026-09-23 08:40 UTC: stop asking me for fucking credentials. u never needed this in google pay. i gav…
- https://www.perplexity.ai/computer/tasks/6bd41a15-276c-4caf-a759-be7a6d39ae94: 2026-09-23 06:00 UTC → 2026-09-23 08:36 UTC: u have higgsfield connected in this user in mcp ytes?
- https://www.perplexity.ai/computer/tasks/01793272-830a-4a7f-a77c-375458713da4: 2026-09-23 08:35 UTC: +
- https://www.perplexity.ai/computer/tasks/eb5e1f20-f4b7-495d-89c7-119102c6ae3d: 2026-09-22 21:06 UTC → 2026-09-23 08:31 UTC: I can't find this in the chat. We had a session, it's been in the last 2 hours, …
- https://www.perplexity.ai/computer/tasks/dd017f79-f19e-40e4-9b16-9092f70b5529: 2026-09-23 05:27 UTC → 2026-09-23 08:15 UTC: REVISIT ALL WORK DONE ON JULIE MASTERCLASS, SANDRA MASTERCLASS EMAILS AND MY WOR…
- https://www.perplexity.ai/computer/tasks/251e357f-0367-4105-aeee-b66c069f4f11: 2026-09-23 07:54 UTC → 2026-09-23 08:19 UTC: yes approved. dont ruin the quality and 4kk
- https://www.perplexity.ai/computer/tasks/653edf1a-2b37-4695-ac45-302de528ddef: 2026-09-22 18:13 UTC → 2026-09-23 07:14 UTC: GO INTO EVENTS MANAGER ON COMET BROWSER, FIX THIS FOR LLA ECOMMERCE ONCE AND FOR…
- https://www.perplexity.ai/computer/tasks/6c1a8931-e108-4f88-b38e-bb9284f17774: 2026-09-22 21:32 UTC: ?
- https://www.perplexity.ai/computer/tasks/126994a0-ae37-4d2b-9e2c-b1c3ca4417ae: 2026-09-23 05:15 UTC → 2026-09-23 07:09 UTC: אני צריך לחבר אותך למנוי החשבוניץ ה ירוקה שלי. יש לך אינטגרציה לגרין אינבויס או …
- https://www.perplexity.ai/computer/tasks/b4bcf43b-58ff-47a6-b1c4-6b2f66978321: 2026-09-23 05:43 UTC: meta ads manager adset2 longevity ecommerce which u know well has unsaved drafts…
- https://www.perplexity.ai/computer/tasks/261e9757-116e-4a2c-8b89-19a0b118e688: 2026-09-22 22:24 UTC → 2026-09-23 06:57 UTC: NO THIS ISNT AN OPTION AT ALL. I WILL NOT LOOSE MONEY.   The checks confirm the …
- https://www.perplexity.ai/computer/tasks/a19910f7-ef4a-4706-946d-c6c8b78ad2e1: 2026-09-23 05:44 UTC: how many atc asll night lngvty ecomm adsets
- https://www.perplexity.ai/computer/tasks/88173292-8ba8-4b89-8435-20f250919933: 2026-09-22 08:42 UTC → 2026-09-23 05:12 UTC: number 1 there is not claude testing. only u did testing.   4. u said the same t…
- https://www.perplexity.ai/computer/tasks/a6445ad4-cc79-4601-8614-8943bdf58f0b: 2026-09-22 21:13 UTC: In all the meta-investigations, one thing that you neglected-and I'm sure is wro…
- https://www.perplexity.ai/computer/tasks/f8693a58-255b-4791-b831-1c5a4640604a: 2026-09-22 18:09 UTC: Summarize the current webpage
- https://www.perplexity.ai/computer/tasks/e31bc4fc-473d-4054-afe7-0574d83b0011: 2026-09-22 18:09 UTC: Summarize the current webpage
- https://www.perplexity.ai/computer/tasks/1f15da00-ebd8-4e11-b762-48ab50e207f9: 2026-09-22 17:43 UTC → 2026-09-22 18:01 UTC: Uh, we added a WhatsApp button page to the homepage, and the checkout in- and th…
- https://www.perplexity.ai/computer/tasks/80369a74-ed5b-4f33-8ba1-49f39568f0f1: 2026-09-22 17:57 UTC: Continue the unfinished deployment from this task. Priority: longevitylifeacadem…
- https://www.perplexity.ai/computer/tasks/2ad9f29b-d8be-4ef7-922c-2c33185efe2e: 2026-09-21 18:15 UTC → 2026-09-22 16:32 UTC: (query truncated)
- https://www.perplexity.ai/computer/tasks/23822628-c1d7-4345-acf3-6b6e6c078cb9: 2026-09-22 16:05 UTC → 2026-09-22 16:13 UTC: Go into my Meta Ads. You know this subject very well in longevity and the eComme…
- https://www.perplexity.ai/computer/tasks/c67b3642-c7b1-4c29-ad1a-eaec25dd553c: 2026-09-22 16:11 UTC: i dont have 40 min for every assignement during crusis
- https://www.perplexity.ai/computer/tasks/2d06348e-25c0-486f-bb83-945884770663: 2026-09-22 15:27 UTC: DONT TOUCH ANYTHING. U KNOW ECOMM ADSET 2 ADD TO CART CRISIS INVESTIGATION. DONT…
- https://www.perplexity.ai/computer/tasks/6b141755-d880-4d22-a92f-07e87b95cf0a: 2026-09-22 14:57 UTC: Summarize the current webpage
- https://www.perplexity.ai/computer/tasks/721bec57-7f2b-4dc9-8731-026ddfc23fe0: 2026-09-22 08:38 UTC → 2026-09-22 13:48 UTC: dont do anything. only tell me if u can find the sandra email marketing thread a…

### Brain wiki index

## Knowledge Index

### Projects

- `projects/lla-ugc-video-ads`: branded testimonial-style video ads for the Longevity Blueprint
- `projects/lla-course-checkout`: LLA three-step checkout, payments, and CRM integration
- `projects/lla-masterclass-emails`: LLA package-specific sales and lifecycle email system
- `projects/lla-julie-masterclass`: Julie Gibson Clark’s three-tier direct-ecommerce masterclass
- `projects/french-atelier-performance-diagnosis`: call-center performance comparison and diagnosis surface
- `projects/lla-organic-community-blitz`: LLA organic distribution and verified-reach system
- `projects/abraham-tlv-gm-plan`: Abraham Tel Aviv CEO-facing GM operating plan
- `projects/lla-privacy-policy`: LLA health-data privacy-policy surface
- `projects/club-italia-school`: premium online Italian-language school concept and public site
- `projects/french-atelier-social-kickstart`: French Atelier September–October organic-social plan
- `projects/french-atelier-website`: French Atelier production website
- `projects/lla-funnel-performance-deck`: LLA ecommerce campaign measurement and decision deck
- `projects/lla-handoff-pack`: LLA media and technical transfer surface
- `projects/lla-julie-communications-plan`: Julie’s public campaign communications plan
- `projects/lla-ad-banner-campaign`: LLA Meta and Instagram creative system
- `projects/lla-delta-force`: LLA lead, influencer, and ecommerce activation hub
- `projects/lla-promo-email-funnel`: LLA gated email-campaign LP and CRM funnel
- `projects/lla-s09-s10-video-delivery`: Courtney and Julie source, edit, and release delivery system
- `projects/french-atelier-ecommerce-pilot`: French Atelier’s high-stakes direct-checkout Meta pilot
- `projects/in-venture-programme`: source-faithful programme plan and editable interview handoff
- `projects/in-venture-website`: premium multi-page venture-capital website redesign
- `projects/service-performance-evidence-register`: public service-performance evidence register
- `projects/lla-master-delivery-hub`: consolidated public LLA client handoff
- `projects/lla-growth-engine`: LLA ecommerce recovery and remarketing system
- `projects/lla-julie-masterclass-video`: Julie Gibson Clark masterclass ad system
- `projects/lla-employee-referral`: employee banners paired with a referral-free public LLA course page
- `projects/hana-enneagram-assessment`: Hana Enneagram assessment and compatibility site
- `projects/keren-or-farm-adoption-en`: English Keren Or adoption page
- `projects/lla-domain-reputation-fix`: LLA website trust and email-authentication fix
- `projects/lla-pr-article-ads`: Meta and Instagram creatives from four live LLA press placements
- `projects/lla-pr-campaign`: LLA/eTeacher press-release distribution campaign
- `projects/lla-turnaround-plan`: LLA CEO turnaround deck
- `projects/lms-image-pack`: exact-size themed LMS image delivery
- `projects/personalix-website`: Personalix premium recruitment-platform website

### Concepts

- `concepts/video-quality-qa`: media delivery QA standard
- `concepts/github-pages-delivery`: live-site handoff pattern
- `concepts/pr-placement-guarantees`: direct-link promise taxonomy
- `concepts/wix-editor-publishing`: Wix Editor/API constraint

### Entities

- `entities/sandra`: LLA CRM-governance and campaign-copy authority
- `entities/gita-agency`: Omri Gitter’s advertising/performance agency
- `entities/julie-gibson-clark`: LLA bio-age and masterclass authority figure
- `entities/harel-tayeb`: CEO and public-facing media contact for LLA/eTeacher Group PR
- `entities/longevity-life-academy`: LLA client surface for site, PR, and film assets
- `entities/omri-gitter`: GitHub owner and client-delivery lead

### Search / Ask threads (23, full transcripts in sessions/search-threads/<id>/conversation.jsonl)

- https://www.perplexity.ai/search/05adbf92-5dc4-4e85-b067-adf5d8d08ba3: 1 entries: Hi. Um, I needed you toelp me file a lawsuit against Perplexity and gather, like, evidence, okay? So
- https://www.perplexity.ai/search/06362628-492f-46eb-82a1-16e652114745: 7 entries: I can't believe you would do this install, and you have not delivered all night. I did this is just 
- https://www.perplexity.ai/search/27dd7bdf-163f-44ac-a1d5-e53355251299: 2 entries: WHAT TIME IS THIS TOMORROW IN ISRAEL EZXACTLY 6:30-8am PACIFIC?
- https://www.perplexity.ai/search/300b64fc-e4d4-4e6e-b07b-38cb8f8de6f7: 4 entries: i ave p pavillion
- https://www.perplexity.ai/search/3080a2ec-c66c-4aca-812b-5d1bc4661958: 30 entries: In French atelier we rum meta lead gen objective paid ads at.20 dollars a lead and in another school
- https://www.perplexity.ai/search/31a73992-cc37-4af0-b995-11667673daa5: 14 entries: Permanently adjust a situation where I can talk in voice and you can only reply in text now.
- https://www.perplexity.ai/search/37958c5e-fbff-4279-a5e6-2bc5573639e6: 16 entries: Doesn't appear from mobile
- https://www.perplexity.ai/search/45eb1303-b1e4-4584-a4d5-e15ee24b928d: 7 entries: Um, longevity, Life Academy School pilot in marketing and all the campaigns we're doing is, uh, fail
- https://www.perplexity.ai/search/46b5c885-c47f-41db-93e0-e925fa7b1df8: 1 entries: U DID THE WHOLE LONGEVITYYYLIFEACADEMY.COM WEBSITE AND PROGRAMMED EVERYYTHING INCLUDING FORMS, API T
- https://www.perplexity.ai/search/4b8361e4-ecc6-4f30-8975-6b643579685e: 1 entries: Yesterday. You got an assignment to do. LPs. And emails for longevity, in the same way that promo em
- https://www.perplexity.ai/search/4e9d6ed5-394d-4b8f-9ffc-09274142aa8e: 2 entries: Yeah, we were just in a conversation, and you hung up on me.
- https://www.perplexity.ai/search/76a8b673-ecd6-4e31-aac5-be9059e1087c: 1 entries: Check if ots love ein newswire we released today with afress in usa. Check
- https://www.perplexity.ai/search/795a90fd-8808-4182-a780-74575ee1dd13: 34 entries: Go into my Meta Ads in longevity e-commerce, check please, please, please. If I got a purchase in th
- https://www.perplexity.ai/search/8943dfd8-5e45-4df3-b6f7-85258cf2f13d: 1 entries: Listen to my exact, um, assignment here: I'm. Have a video; it's 90 seconds, and one is 120 seconds.
- https://www.perplexity.ai/search/8c80bff9-a5bd-4673-843b-45bfc91c408d: 1 entries: Summarize the current webpage
- https://www.perplexity.ai/search/97bd03b3-d6fa-46e3-a21a-17014384c476: 1 entries: Summarize the current webpage
- https://www.perplexity.ai/search/a97b4ada-43d3-4f8c-9716-28616955bb6a: 1 entries: למשרד תקציבאי במשרד פרסום מוביל, בן דוד שלי נדרש להעביר שץי המלצות ממעסיקים. הם ביקשו ממני לנסח עבור
- https://www.perplexity.ai/search/ad63f82e-7b39-4a80-a355-732b49d49609: 3 entries: Hi, I'm new to this service. Um, I live in Israel, I speak Hebrew. And English. I work in English, b
- https://www.perplexity.ai/search/b9d778a5-730a-44d4-923d-ff3b8cc7702d: 1 entries: Summarize the current webpage
- https://www.perplexity.ai/search/d2c46a65-a56d-480b-8bf1-3d7caae67ec1: 1 entries: Or the website, the new website of French Atelier, you had. An assignment. To update the website in 
- https://www.perplexity.ai/search/d6ae7c17-16bf-4b09-b238-37040da56295: 1 entries: Send me the julie Gibson Clark communications doc with the links inside we sent her. U prepared it (
- https://www.perplexity.ai/search/df7b917c-b055-4b4d-a197-08bf7b4fd925: 32 entries: היה לי הסכם עם איטיצר על טיפול בפרפורמנס ובחשבון מטא על הפעילות ברוזן )אתה מכיר הכל היטב (  החלטנו ב
- https://www.perplexity.ai/search/fc93fb92-43aa-4162-a319-b812bd986233: 2 entries: update this as to the most current data including missing days per day. please note yesterday we con


# Handover coverage and limits


- Available project knowledge pages included: **59**.
- Dated daily operating records included: **14**.
- People, preferences and concept records included: **24**.
- Repository inventory data rows: **45,322**.

- This is a knowledge and operational evidence handover, not a claim that all production services, every historical URL, every media asset or every CRM transaction was re-tested.
- Meta and ActiveCampaign access limitations and historical timestamps are explicitly recorded in their sections.
- Source credentials, private Zoom access tokens and raw customer audiences are excluded. No live service was intentionally modified for this handover.
- No global all-session transcript completeness claim is made; the session enumeration limitation is documented above.
- The full project register is included to avoid losing non-email subjects. Its historical assistant claims must not become current facts without the indicated evidence.


# Historical full Vercel project inventory

The following inventory was collected on 10 October 2026. It is not current deployment verification.

# Vercel projects — team GITTER (gitter1), all 52, listed 2026-10-10 via `vercel project ls`

| Project | Production URL | Last updated (age at 10 Oct) | Node |
|---|---|---|---|
| french-atelier | -- | 87d | 24.x |
| fa-bastille-winners | https://fa-bastille-winners.vercel.app | 95d | 24.x |
| jgc_preview | https://jgcpreview.vercel.app | 95d | 24.x |
| eteacher-longevity | -- | 95d | 24.x |
| win-paris-fa | https://win-paris-fa.vercel.app | 96d | 24.x |
| fa-src | -- | 97d | 24.x |
| fa-live | -- | 97d | 24.x |
| french-atelier-onboarding | https://french-atelier-onboarding.vercel.app | 100d | 24.x |
| fa-win-france | https://fa-win-france.vercel.app | 105d | 24.x |
| fa-bastille-day | https://fa-bastille-day.vercel.app | 105d | 24.x |
| fa-paris-fr | https://fa-paris-fr.vercel.app | 105d | 24.x |
| fa-deploy | https://fa-deploy-phi.vercel.app | 106d | 24.x |
| fa-staging-light | https://fa-staging-light.vercel.app | 2d | 24.x |
| fa-staging-checkout | https://fa-staging-checkout.vercel.app | 2d | 24.x |
| fa-leads-proxy | https://fa-leads-proxy.vercel.app | 3d | 24.x |
| french-atelier-mockup | https://french-atelier-mockup.vercel.app | 3d | 24.x |
| julie-masterclass-mockup | https://julie-masterclass-mockup.vercel.app | 5d | 24.x |
| julie-masterclass-ads | https://julie-masterclass-ads.vercel.app | 8d | 24.x |
| julie-masterclass | https://julie-masterclass.vercel.app | 9d | 24.x |
| lla-gal-september-2026 | -- | 12d | 24.x |
| src | -- | 12d | 24.x |
| lla-ac-events | https://lla-ac-events-gitter1.vercel.app | 13d | 24.x |
| relay-live | -- | 16d | 24.x |
| capi-relay | -- | 17d | 24.x |
| lla-vtest | -- | 21d | 24.x |
| lla-reorder-test | -- | 21d | 24.x |
| lla-fix-preview | -- | 22d | 24.x |
| preview | -- | 22d | 24.x |
| jmc-live | -- | 23d | 24.x |
| jmc | -- | 23d | 24.x |
| jm-mc-3tier | -- | 23d | 24.x |
| julie-masterclass-v2 | -- | 23d | 24.x |
| julie-mc-3tier | -- | 23d | 24.x |
| lla-emq- | -- | 25d | 24.x |
| lla-emq-relay-1789457668 | -- | 25d | 24.x |
| lla-capi-v2 | -- | 25d | 24.x |
| lla-ac-events-deploy | -- | 25d | 24.x |
| relay | -- | 25d | 24.x |
| lla-emergency-checkout | https://lla-emergency-checkout.vercel.app | 31d | 24.x |
| lla-blueprint-redesign-preview | https://lla-blueprint-redesign-preview.vercel.app | 33d | 24.x |
| jm2 | -- | 37d | 24.x |
| jmlink | -- | 37d | 24.x |
| in-venture-programme | https://in-venture-programme.vercel.app | 38d | 24.x |
| masterclass-site | -- | 38d | 24.x |
| in-venture-phase-one | https://in-venture-phase-one.vercel.app | 38d | 24.x |
| julie-letter-final | -- | 39d | 24.x |
| julie-letter-v3 | -- | 39d | 24.x |
| letter-site | -- | 39d | 24.x |
| julie-letter | -- | 39d | 24.x |
| lla-events-api | -- | 44d | 24.x |
| ac-events | -- | 45d | 24.x |
| lla-courtney-launch | https://lla-courtney-launch.vercel.app | 74d | 24.x |

Total: 52. Project IDs known: lla-ac-events prj_3v7g4Xwve6OmXrcPCVQOWJOiN2SK, fa-leads-proxy prj_byAoWWUN5aXdGDrGRb7PJ25hINlI, fa-staging-checkout prj_xluo8z01uYC5bnbHzgWZpxVozk6I, fa-staging-light prj_VL9P72MT1ZQ5nsb6rdbITX90BzED. Team id team_QsIIEvdvnmtyD40s3mcnka6k. Node 20 discontinued notice received; Hobby-plan limit warning 7 Oct 2026.
