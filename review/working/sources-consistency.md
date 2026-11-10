# Source and numeric consistency review

Reviewed `README.md` and the complete `index.html` on 2026-11-10. This is a review only; the page and README were not changed. Link status below is the final response to a `curl -L` GET; a successful HTTP status does not mean the response was the intended readable source.

## Link status

| Location | URL | HTTP result | Source access / evidence |
|---|---|---:|---|
| README, lines 5–5 | <https://ruddyrid.github.io/20261107-sbf-v8-tech/> | 200 | Live page responded without a redirect. |
| `index.html`, line 10 | <https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@500;600;700;800&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap> | 200 | Stylesheet responded. The two `preconnect` origins at lines 8–9 are connection hints, not source citations. |
| `index.html`, line 1111 | <https://performanceparts.ford.com/download/instructionsheets/fordinstshtm-6013-b347.pdf> | 200 | Readable Ford Performance PDF; scope is a 347-ci stroker kit, not a general stock-engine specification manual. Relevant evidence is described below. |
| `index.html`, line 1112 | <https://help.summitracing.com/knowledgebase/article/HE-04923/en-us> | 200 | GET returned an Incapsula challenge page, not the cited torque article. **VERIFY** its contents; do not treat the HTTP 200 as source validation. |
| `index.html`, line 1113 | <https://www.enginebuildermag.com/2013/04/revised-cylinder-head-bolt-and-torque-procedures-for-88-95-ford-5-0l-engines/> | 403 | HTTP access denied by GET, but the article text was readable through the page extractor. It gives the bolt-style and torque procedures described below. |
| `index.html`, line 1114 | <https://www.mahle-aftermarket.com/media/local-media-north-america/pdfs-&-thumbnails/torque3.pdf> | 200 | Readable 124-page torque chart, including Ford 302 entries on PDF p. 41 and 351 entries on p. 42. |
| `index.html`, line 1115 | <https://en.wikipedia.org/wiki/Ford_Windsor_engine> | 200 | Readable by GET; page content redirects internally to “Ford small block engine.” It summarizes dimensions and history but is secondary and flags some material as needing references. |
| `index.html`, line 1116 | <https://mainemustang.com/mustang-info/ford-engine-bolt-torque-chart> | 404 | Broken source link (**ERROR**). |

Internal `#...` links are page anchors, not HTTP source links. No other external `href` source citations appear in `index.html`.

## Numeric and internal-consistency checks

### Dimensions, displacement, and conversions — pass

For each listed Windsor, swept volume was recomputed as `π/4 × bore² × stroke × 8`, using the dimensions shown in **01 / Family** and **02 / Specifications** (`index.html` lines 512–519 and 536–555). Results are 220.901, 260.393, 288.524, 301.593, and 351.858 ci for the 221, 260, 289, 302, and 351W, respectively; each rounds to its nominal displacement. The timeline’s 255-ci 3.680 × 3.000 variant at line 518 computes to 255.268 ci. No displacement arithmetic error found.

The note “302 is 4,942 cc” in **02 / Specifications** (`index.html` line 557) is consistent with the displayed nominal 4.000 × 3.000 dimensions: they calculate to 301.593 ci / 4,942.2 cc, conventionally named the 302. Converting the rounded label “302 ci” instead gives about 4,949 cc, so the two values should not be expected to convert exactly. The Wikipedia page independently gives 4,942 cc / 301.6 cu in and identifies 5.0 as marketing.

Metric conversions in **02 / Specifications** (`index.html` lines 536–555) match 25.4 mm/in rounded to one decimal. The **04 / Blueprint** diagram’s 18.75 in / 476 mm and 20.75 in / 527 mm (`index.html` lines 654–655) also round correctly. Repeated dimensions agree: the 351W deck is 9.480 in for 1969–70 and 9.503 in thereafter; the 1.297 in / 32.9 mm difference from the 302 is correct. Journal-size differences of 0.751 in (main) and 0.188 in (rod), plus the displayed rod lengths, are arithmetically correct (**02 / Specifications**, lines 546–549; **04 / Blueprint**, lines 668–695).

### Ratings and graphics — no arithmetic error demonstrated; source gaps remain

The **03 / Brake horsepower** rating-bar widths at `index.html` lines 583–601 were checked against the stated 320-hp and 420-lb-ft scales; the percentages match the displayed ratings to their shown precision. Power values are not consistently sourced to specific Ford model-year publications in the page’s source list.

The requested `hp = torque × rpm / 5252` check cannot validly use the page’s listed *peak* horsepower rpm and *peak* torque as if they occurred together. The **script engine data** at `index.html` lines 1190–1194 provide horsepower rpm but no torque-peak rpm or torque curve; the **03 / Brake horsepower** ratings at lines 583–601 provide no rpm. For example, 225 hp at 4,600 rpm implies about 257 lb-ft at that same rpm, which does not conflict with a separately quoted 300-lb-ft peak. **VERIFY** the original rating figures and rating conditions against model-year Ford brochures/service publications; no HP/torque arithmetic error is established from the available data.

### Compression and chronology — VERIFY scope / year mapping

Compression ratios in the **02 / Specifications** row (`index.html` line 550) are ranges across unspecified variants and years; a ratio cannot be calculated from bore and stroke alone. The linked Wikipedia summary groups several compression ratios without mapping each to each displacement/year, while its 221 section reports 8.7:1 and its 289 HiPo section reports 10.5:1—consistent with the page’s 221 and 289 upper-end claims but not adequate to establish the other range endpoints. The 302-specific discussion also says compression fell to 9.0:1 in 1972, a value inside the page’s 8.0–9.5 range. These are not direct contradictions, but year/induction/engine-code mapping is missing. **VERIFY** all endpoints against year-specific factory manuals or brochures before presenting them as family-wide ranges.

The page’s 1962–2001 family span and 302 model-year span are consistent with the README and Wikipedia’s 302-era account (`README.md` line 3; **hero / 01 / Family / 02 / Specifications**, `index.html` lines 437, 512–519, 536–537). Wikipedia also describes calendar production as July 1961–December 2000, so make clear that the page’s end years are model years, not literal calendar production dates. The 351W 1969–96 and deck-height break are consistent with the linked secondary summary.

### Torque, clearances, repeated figures, and source disagreements

All **05 / Torque** table ft-lb to Nm ranges at `index.html` lines 735–753 were recalculated with 1 ft-lb = 1.3558 Nm and match the displayed rounded conversions. The torque values repeated in **06 / Assembly**, blueprint callouts, **07 / Reference** quick lookup, and print card agree with the table where the same application is represented (`index.html` lines 826–831, 889–892, 907–930, 946–949, 982–987, 1083–1092, 1142–1168). The 1/4-in and 5/16-in oil-pan subranges (7–9 and 9–11 ft-lb) correctly span the table’s 7–11 range.

The MAHLE chart is useful evidence of **real application/source variation**, not one universal stock spec:

* **302 rod bolts:** the page’s broad 221–302 column says 22–25 ft-lb and notes that manuals also list 19–24 (`index.html` lines 736–737); its assembly step still gives 22–25 as the generic 302 instruction (`index.html` line 889). MAHLE PDF p. 41 lists 19–24 for multiple 302 year entries (including 1974–82, 1984–87, and 1991–2000), while the Ford Performance stroker-kit PDF lists 50 ft-lb for its kit’s ARP bolts. These represent distinct years/hardware. Keep the hardware/year qualification prominent; the sources do not support applying one range indiscriminately.
* **351W main caps:** the page gives 95–105 ft-lb and 35–40 for 4-bolt outer bolts (**05 / Torque**, `index.html` line 736). MAHLE PDF p. 42 lists 95–105 for 351 entries and 40 ft-lb for outer bolts in its 1970–74 “355” entry, which is compatible with the page’s range. A separate 351M row lists 35–45; because 351M is not 351W, that row is not evidence of a Windsor disagreement. The MAHLE chart mixes engine/model identifiers, so do not generalize its non-Windsor value to the 351W.
* **351W head bolts:** the page shows 90–100 and itself notes 105–112 in some factory sheets (**05 / Torque**, `index.html` lines 738 and 757). MAHLE PDF p. 42 has several 351 entries listing staged 85, 95, 105–112-ft-lb values. This is an explicit, unresolved source disagreement, and the page’s 90–100 range is not supported by the linked MAHLE chart as a single universal value. Require year/block-specific verification.
* **1988–95 5.0 head bolts:** the page’s standard-hex two-step values and TTY three-step values (**05 / Torque** and **06 / Assembly**, `index.html` lines 757, 946–947) agree with the readable Engine Builder article: hex 55–65 then 65–72 ft-lb; TTY 25–35 then 45–55 ft-lb then 85–95 degrees, single use. However, the article says both bolt styles may be used on any 5.0L and must not be mixed on a head. That conflicts with treating “1988–95” or a 1992 changeover as a reliable year-based identification rule. The page appropriately says to identify the physical bolt style; retain that instruction and do not infer bolt style from year alone.
* **302 bearing/rod clearances:** the Ford Performance PDF linked from **08 / Sources** at line 1111 is for its M-6013-B347 347-ci stroker kit, not a stock 302 specification. Its “Recommended Clearances” gives main and connecting-rod bearing clearances of .0020–.0030 in and rod side clearance .010–.015 in (PDF p. 2), while **06 / Assembly** labels .0004–.0015 in as a factory main-bearing target and .010–.020 in as typical rod side clearance (`index.html` lines 826, 831, 890–892). This is not a like-for-like contradiction because the Ford kit is a different build, but the cited PDF does not substantiate the page’s stock factory targets. **VERIFY** those targets and the .0021-in allowable limit from the exact stock 302 service manual; also make clear that the Ford kit is not the source for them.

Other numeric values in **06 / Assembly** and **07 / Reference**—piston-to-wall, rod clearance, end play, pickup clearance, capacities, pressure, plug gap, timing, lash/preload, and break-in rpm/time (`index.html` lines 812, 826–831, 889–892, 926–930, 964–987, 1002–1006, 1083–1092)—are internally repeated consistently where repeated, but the six listed sources do not substantiate most of them. They are **VERIFY**, not arithmetic errors; the page’s own “check against the manual” caveats are important.

The **07 / Reference** firing-order strings are internally consistent and each is a permutation of cylinders 1–8 (`index.html` lines 1045–1075). One internal explanation is wrong: line 1075 says the 351W uses the later order “because of its different crank and cam layout,” then correctly says order follows the camshaft. Firing order is determined by the cam lobe sequence, not by a distinct crank layout. **ERROR:** remove or correct that causal claim.

## Source-quality / traceability summary

The Ford Performance source is primary but tightly scoped to a 347 stroker kit; it even directs readers to factory Ford shop manuals available through Helm. The MAHLE chart is a broad secondary torque compilation, and the Summit source could not be read in this review. Wikipedia is secondary, with some content explicitly flagged as needing citations. The Maine Mustang link is dead. None of the provided links gives a traceable, year-specific primary source for the full power/compression tables, family dimensions, or most 302 assembly values. For those figures, map claims to the applicable Ford shop manual, year/model sales literature, or Ford technical publication; retain **VERIFY** until that evidence is attached.

README numeric claims align with the page for the five engines and ten assembly stages (`README.md` lines 3 and 13; `index.html` lines 445–449 and 767–1009). The README’s 390/768/1440-px Chromium test widths (`README.md` line 28) are test-history claims, not engine figures, and cannot be verified from these static files.
