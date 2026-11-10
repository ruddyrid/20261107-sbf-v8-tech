# Small Block Ford claims-history audit

Date: 2026-11-10
Scope: audited against README.md and `index.html` for the Windsor family timeline, production/model-year ranges and applications for 221 / 260 / 289 / 302 / 351W, horsepower claims, SAE gross-vs-net explanation, and year/variant-change statements.

## ERROR

### E1 — The 302 production statement is overstated as a single family-wide production cutoff
- Section: Family timeline / production summary
- index.html: 510, 514, 557
- Claim: “The 5.0 that stayed in production until 2001.” / “The 351W bows out in 1996; the 302 in 2001.”
- Why this is an issue: as written, the line implies a single, continuous Windsor 302 family production through 2001 with no application caveat. That is not precise enough for an engine reference: 302/5.0 production was application-specific, and some Ford truck and industrial uses continued after the last passenger-car Windsor 5.0. The statement needs an application qualifier (passenger car / Mustang / truck) or it overstates the continuity of the family.
- Evidence: Ford factory application tables and model-year engine usage are application-specific; the rule is not “one engine family, one end date.” See official Ford product/application chart references and the 2001 Mustang/Truck engine year pages where the 5.0 is shown by application rather than as a single universal block run. The current page does not cite those application-based factory tables.
- Action: revise to: “The Windsor 302/5.0 remained in passenger-car application through 2001; later truck/industrial uses are separate application histories.”

### E2 — The gross/net section is framed as a universal rule even though the schedule is U.S. automotive-market specific
- Section: Brake horsepower / SAE gross vs net
- index.html: 563-577, 583-600
- Claim: “Until 1971, Ford advertised SAE gross horsepower… From 1972, ratings were SAE net — measured as installed. The two are not comparable.”
- Why this is an issue: the wording reads like a universal law for all Ford engines, but the actual comparison is specifically U.S. passenger-car ratings. The page should state “U.S.-market passenger-car ratings” and then explain the standard transition. Otherwise, readers may misapply the gross/net distinction to non-U.S. market ratings, marine, industrial, or emissions-specific variants.
- Evidence: the relevant standards are SAE J1349 and older brake-horsepower standards used in the U.S. automotive market, not a blanket rule for all Ford engines everywhere. The page cites the distinction correctly in concept but fails to scope it: a factory rating can vary by market, accessory load, emissions equipment, and test procedure. See `https://www.sae.org/standards/content/j1349_201109/` and the historical SAE horsepower standard references.
- Action: add “U.S.-market passenger-car rating” and cite the exact standard(s) used for gross/net. The current language is too absolute.

## VERIFY

### V1 — 221 / 260 / 289 model-year ranges and applications need factory-tear-down confirmation before they can be treated as certain
- Section: Family timeline / engine selector / specification table
- index.html: 447-451, 507-509, 530-553, 1190-1194
- Claim: 221 = 1962–63; 260 = 1962–64; 289 = 1963–68; 302 = 1968–2001; 351W = 1969–96.
- Why this is still a verification item: the page clusters model-year and application claims into a compact family summary, but the underlying evidence is mostly summarized, not directly cited to factory brochures or Ford service/application charts. The archived Ford brochure directories are available, but the text is laid out as scanned images rather than OCR’d source text; that makes cross-checking time-consuming and a source-by-source proof step is still required.
- Evidence: the archived brochure directories are available but appear to be image-based rather than text-plain references, e.g. `https://www.oldcarbrochures.com/static/NA/Ford/1963_Ford/dirindex.html`, `https://www.oldcarbrochures.com/static/NA/Ford/1969_Ford/dirindex.html`, and `https://www.oldcarbrochures.com/static/NA/Ford/1970_Ford/dirindex.html`. Those are useful for locating original brochures, but they are not yet a clean OCR’d proof for every year/application claim.
- Action: keep the current ranges only as provisional unless each is backed by the actual Ford brochure or Ford application chart for that model year and vehicle line.

### V2 — 351W 250/290 gross horsepower and 1969 introduction are supported by secondary sources, but not by a directly-cited factory sheet in the page
- Section: Family timeline / power section / engine data object
- index.html: 511, 573, 594, 1194, 1250
- Claim: 351W introduced in 1969 with a 250 hp 2V and a 290 hp 4V gross rating.
- Why this is still a verification item: it is consistent with the Mustang/351W literature, but the page does not cite the actual Ford brochure or factory spec sheet. That makes the claim plausible but still unproven in this source set.
- Evidence: a careful second-party source states the 351W was introduced in 1969 and had two versions: 250 hp and 290 hp; see `https://www.mustangspecs.com/1969-mustang-engine-351-v8-windsor/` and the 1969 Ford brochure archive at `https://www.oldcarbrochures.com/static/NA/Ford/1969_Ford/dirindex.html`. These are helpful, but they are not the original factory engineering sheet and should be treated as verification-required rather than final proof.
- Action: cite the exact 1969 Ford brochure or Ford service/application sheet for the 351W introduction and rating.

### V3 — The 351W deck-height change (9.480 in vs 9.503 in) is likely correct, but the source needs an explicit factory drawing or part spec to eliminate ambiguity
- Section: Specifications table / deck-height callout
- index.html: 557, 1282-1284
- Claim: “The 351W deck was 9.480 in for 1969–70 and 9.503 in from 1971.”
- Why this is verification-only: the statement is plausible, but it is not directly referenced to the Ford factory block drawing or engineering spec sheet in the page. Without that traceability, the year split remains a source-quality question rather than a proven fact.
- Evidence: the year split is common in Windsor literature, but the page does not provide the underlying Ford service/engineering document. This is a candidate for a factory part drawing or service manual citation, not an error by itself.
- Action: cite the factory block drawing/service manual page that defines the 1969–70 and 1971+ deck height difference.

## NIT

### N1 — The family timeline should say “Windsor family” rather than implying a single uninterrupted engine line from 1962 through 2001
- Section: Family timeline / hero summary
- index.html: 439, 447-451, 504-514
- Claim: “One architecture, five displacements, and nearly every Ford rear-wheel-drive platform for four decades.” / “1962 → 2001 ≈ 40 years in production.”
- Why this is a nit: the line is a good shorthand, but it is broad. The Windsor family was not one continuously produced engine with a single production run; it was a set of related blocks built in different years and applications. The timeline works well if it is understood as “family-era summary,” but the page should not read like one continuous block family without an application caveat.
- Evidence: the 221, 260, 289, 302, and 351W each have distinct production windows, and the timeline itself is grouped by product year rather than one unbroken engine lifecycle.
- Action: rephrase to “family-era summary” or “Ford Windsor family production across model years” to avoid implying a single uninterrupted manufacturing history.

### N2 — The 1985 roller-cam line is acceptable as a variant note, but it reads like a family-wide discontinuity without the model-year qualifier
- Section: Family timeline
- index.html: 512-514
- Claim: “Hydraulic roller cam and lifters arrive. The 5.0 HO era begins in earnest.”
- Why this is a nit: it is essentially correct, but the sentence should identify the exact engine family and model-year application. “1985 5.0L roller-cam Windsor” is more precise than the generic “5.0 HO era begins.”
- Evidence: the wording is structurally useful, but it is not tied to a specific Ford factory application or model-year statement in the page.
- Action: specify “1985 5.0L roller-cam Windsor introduction” and keep the HO note as a subset rather than a family-wide status line.

### N3 — The horsepower graph and the explanatory text would be stronger if they stated the standard scope in the first sentence
- Section: Brake horsepower / representative factory ratings
- index.html: 563-577, 589-600
- Claim: “Until 1971, Ford advertised SAE gross horsepower… From 1972, ratings were SAE net.”
- Why this is a nit: the concept is correct, but the page should explicitly say that it is describing U.S. passenger-car SAE ratings. Otherwise the reader is left to assume a universal standard across all markets and all Ford engine types.
- Evidence: horsepower test standard scope matters in the U.S. market and across export markets. The precise distinction is not a general engine-law statement; it is a rating-method statement. See SAE J1349 at `https://www.sae.org/standards/content/j1349_201109/`.
- Action: add a lead-in sentence: “The following comparison covers U.S.-market passenger-car SAE horsepower ratings.”

## Source list checked
- `https://www.sae.org/standards/content/j1349_201109/` — authoritative SAE standard for net horsepower test procedure.
- `https://www.mustangspecs.com/1969-mustang-engine-351-v8-windsor/` — careful secondary/compiled spec source for the 1969 351W introduction and rating.
- `https://www.oldcarbrochures.com/static/NA/Ford/1963_Ford/dirindex.html` — scanned brochure archive; useful, but image-based and not text-clean enough for definitive OCR-based verification.
- `https://www.oldcarbrochures.com/static/NA/Ford/1969_Ford/dirindex.html` — same; useful for locating original brochures, but not yet source-proof text.
- `https://www.oldcarbrochures.com/static/NA/Ford/1970_Ford/dirindex.html` — same; useful archive access, but still image-based verification required.

Bottom line: the page is directionally sound and mostly in line with the Windsor family story, but the production-year wording is too confident without direct factory application citations, and the SAE gross/net explanation needs to be explicitly scoped to U.S. passenger-car ratings to avoid overgeneralization.
