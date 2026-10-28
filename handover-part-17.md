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

