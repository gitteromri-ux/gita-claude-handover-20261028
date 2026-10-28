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

