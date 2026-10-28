# Immediate operator takeover: connections, infrastructure and acceptance

Updated 28 October 2026. This is the first document the receiving Claude should read, followed by the complete handover parts. Omri is transferring operations immediately for a tool RFP; do not ask him to repeat the history or refer him back to the previous assistant.

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
