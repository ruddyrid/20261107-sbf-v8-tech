# Windsor specs / torque audit

Scope read first: `README.md` and the full `index.html` in this repo. The repo rule is explicit: the factory manual for the engine wins, and the page is a study aid rather than a service manual (`README.md:7-18`; `index.html:1101-1119`).

## 1) Repo rules and precedence

- `README.md:13-18` says the page assumes clean, lightly oiled stock fasteners; ARP, studs, and torque-to-yield hardware are separate.
- `README.md:15-18` says where sources disagree, the page says so rather than silently choosing a value; and the factory manual for your engine wins.
- `index.html:1106-1119` repeats the same rule and names the source list used in-page.
- This audit does not substitute 351C/FE/Chevrolet data, and no Windsor family values were mixed across families.
- Printed unit pairs remain as printed without converting them to a different set of units.

## 2) Evidence reviewed

Source URLs referenced by the page (
`index.html:1111-1118`):
- https://performanceparts.ford.com/download/instructionsheets/fordinstshtm-6013-b347.pdf
- https://help.summitracing.com/knowledgebase/article/HE-04923/en-us
- https://www.enginebuildermag.com/2013/04/revised-cylinder-head-bolt-and-torque-procedures-for-88-95-ford-5-0l-engines/
- https://www.mahle-aftermarket.com/media/local-media-north-america/pdfs-&-thumbnails/torque3.pdf
- https://en.wikipedia.org/wiki/Ford_Windsor_engine
- https://mainemustang.com/mustang-info/ford-engine-bolt-torque-chart

Accessible evidence used for cross-check:
- The Ford Performance crank-kit PDF is a Ford-sourced technical instruction sheet and is relevant to measuring procedure; it is not equivalent to an engine-specific manual scan for every fastener.
- The Engine Builder article explicitly states: the two cylinder-head bolt styles are physically different, they must not be mixed on one head, and TTY bolts are single-use (`https://www.enginebuildermag.com/2013/04/revised-cylinder-head-bolt-and-torque-procedures-for-88-95-ford-5-0l-engines/`).
- The Summit URL was attempted but the site blocked the request, so it remains unverified in this environment and is not treated as a winning source over factory data.

## 3) Specs table audit: 221 / 260 / 289 / 302 / 351W

Relevant section: `index.html:529-557`.

Findings:
- The table keeps the family split correct: 221, 260, 289, and 302 share the short-deck Windsor architecture; 351W is the taller-deck variant.
- `Deck height` is correctly shown as `8.206 in` for 221/260/289/302 and `9.480 / 9.503 in` for 351W, with the note that the 351W deck was 9.480 in for 1969-70 and 9.503 in from 1971 (`index.html:541-557`). This matches the repo’s own caveat and is the correct way to represent the family split.
- `Rod length` values are kept by family: 221/260/289 are `5.155 in`; 302 is `5.090 in`; 351W is `5.956 in` (`index.html:539-545`). This is consistent with the short-deck Windsor vs tall-deck Windsor distinction.
- `Main journal` / `Rod journal` values are correctly split by family, with 351W using the larger `3.000 in` main and `2.311 in` rod journals (`index.html:543-546`).
- `Bore spacing` remains a constant `4.380 in` across the family, which is consistent with Windsor-family architecture (`index.html:546-547`).
- Power output is intentionally not treated as a direct comparison across SAE gross/net eras; the page explicitly says that gross and net are not comparable (`index.html:565-592`). That is a good, correct caution.

Status: acceptable at the repo level for family architecture and nominal dimensions. Exact factory manual scans for each year/casting are not in this environment, so any year-specific production tolerance or exact casting variation stays `VERIFY` rather than silently resolved.

## 4) Torque-table audit against factory/manual-style evidence

Relevant section: `index.html:701-757`.

Findings:
- The page correctly states the stock-fastener assumption: clean, lightly oiled stock bolts; aftermarket/ARP/studs/TTY are separate (`README.md:13-18`; `index.html:703-712`).
- The table is framed as a stock-fastener reference and includes explicit warnings against mixing hardware (`index.html:711-712`). That is consistent with the repo’s rule and with the 1988-95 5.0L head-bolt issue.
- `Main cap bolts` are shown as `60-70 ft-lb` for 221-302 and `95-105 ft-lb` for 351W (`index.html:731-735`). The table contains the correct conceptual split: 351W mains are larger and torque higher.
- `Connecting rod bolts` are shown as `22-25 ft-lb` for 221-302 and `40-45 ft-lb` for 351W, with a note that some factory manuals list alternate values (`index.html:734-737`). This is the correct kind of caution: not a silent resolution; it names the disagreement.
- `Cylinder head bolts` are shown as `65-72 ft-lb` for normal 221-302 and `90-100 ft-lb` for 351W (`index.html:737-741`). The warning below the table correctly says there are two 1988-95 5.0L head-bolt styles and they must not be mixed (`index.html:757`). That aligns with the Engine Builder source exactly.
- The table’s note for 1988-95 `5.0L` head bolts matches the accessible evidence: standard non-flanged hex head bolts in two steps to 55-65 then 65-72 ft-lb; flanged TTY bolts in three steps to 25-35, 45-55, then 85-95 degrees; and TTY bolts are single-use (`index.html:757`; Engine Builder article text).
- The stock torque table includes a warning that numbers assume clean lightly oiled stock hardware (`index.html:703-712`), which is a standard prerequisite for a manual-based torque table.

Status: acceptable as a stock-fastener reference, and the page correctly identifies disagreement instead of hiding it. However, exact year-by-year Ford service-manual page scans were not available in this repo and must remain `VERIFY` for the final manual page for any casting/year/hardware combination.

## 5) Assembly-stage audit: all 10 stages

Relevant section: `index.html:759-1011`.

Findings:
- All 10 stages are included: teardown, machine work, crank/main-bearing fit, rods and pistons, cam/timing, oil system, cylinder heads, valvetrain, intake/ignition/accessories, and first start/break-in.
- The key fastener sequence diagrams are present and consistent with Windsor practice: main-cap sequence `3-2-4-1-5` and head-bolt sequence `9-5-1-3-7` / `10-6-2-4-8` (`index.html:834-870`).
- Main-bearing clearance and end-play values are expressed as range targets (`0.0004-0.0015 in` target; `0.0021 in` allowable) with the correct caution that these are measured values to be checked with tools (`index.html:826-847`). This is a correct assembly practice statement.
- Rod bearing clearance is listed as `0.0008-0.0015 in` and side clearance as `0.010-0.020 in` (`index.html:884-894`), which is an assembly check, not a final torque value.
- Cylinder-head stage includes the correct TTY warning: do not mix styles; TTY bolts are single-use; flanged TTY uses an additional angle step (`index.html:943-947`). This matches the accessible Engine Builder article.
- Stage 6 includes an oil system value of `5 qt with filter, stock 302` (`index.html:924-938`). That is a practical assembly summary, but exact year-specific fluid capacity figures should always be checked to the actual engine and pan setup; this is a `VERIFY` item if the build is not a stock production 302.

Status: largely coherent and consistent with the repo’s own rules. The warning about aftermarket/TTY hardware and the need to verify exact year-specific values is the right caution. If the project wants absolute factory-manual matching, it still needs exact scanned pages for the specific casting and year.

## 6) Firing orders and cylinder numbering

Relevant section: `index.html:1014-1099`.

Findings:
- Standard Windsor order is shown as `1-5-4-2-6-3-7-8` for 221/260/289/302 (`index.html:1023-1048`).
- The 5.0 HO / 351W order is shown as `1-3-7-2-6-5-4-8` (`index.html:1049-1082`).
- Cylinder numbering is described as passenger side `1-2-3-4` front to rear and driver side `5-6-7-8` front to rear (`index.html:1017-1019`).
- This is the correct Windsor-family distinction: the standard Windsor order and the later HO/351W order are not the same, and the block is not a generic “all Ford V8” numbering scheme.

Status: correct for the family as represented. The page warns to confirm the firing order when the engine is assembled with a distributor or aftermarket cam — appropriate and safe.

## 7) Fluid capacities and pit card

Relevant section: `index.html:924-938` and source/print-card references at `index.html:1101-1128`.

Findings:
- The assembly stage says `5 qt with filter, stock 302` for the oil system (`index.html:924-938`).
- The page references a printable one-page pit card and notes the values are a quick lookup, not a substitute for the factory manual (`index.html:1106-1119`).
- Fluid capacities are not a place to silently mix entire families or aftermarket pan configurations. The repo is correct to treat those values as a quick-reference aid and to require verification against the actual engine and pan.

Status: `VERIFY` for exact stock/aftermarket pan and transmission fluid or coolant values, because the repo does not include a readable exact Ford manual page for each configuration here.

## 8) Conclusion / lead note

- The repo’s page is materially consistent with the Windsor-family architecture and the source rule it states: factory manuals outrank secondary sources; do not substitute 351C/FE/Chevrolet data.
- The `specs` and `torque` sections correctly preserve the family split and explicitly flag disagreement where values vary or where hardware style changes.
- The strongest accessible extra evidence is the Ford Performance crank-kit PDF and the Engine Builder 1988-95 5.0L head-bolt article, both of which support the page’s warnings and the TTY/stock-fastener distinction.
- The only unresolved item is the exact official Ford manual page for each casting/year/hardware variant. Those remain `VERIFY` in this repo because the underlying factory PDF pages were not readable here.
- The page should therefore be treated as a careful study aid with explicit caveats, not as a stand-in for a Ford factory service manual on a specific engine.

Lead-facing verdict: acceptable as a working Windsor-family reference, but not a final factory-manual substitute. Any actual build, especially with 351W deck height, 1988-95 5.0L head-bolt style, or dissimilar aftermarket hardware, should be checked to the exact engine year/casting and the factory manual for that engine.
