# Ford Windsor Small Block V8 Accuracy Review

Date: 2026-11-10

**Merged counts:** ERROR 2 · VERIFY 7 · NIT 2

**Fix-run instructions:** Apply §1 and §3 to `index.html`; no `README.md` edit is required. Leave every §2 item unchanged for the owner. Commit this report and the three papers under `review/working/` first, then commit the §1/§3 page fixes separately and push both commits to `main`.

**Authorization record:** The owner answered Yes to all nine authorization questions. This run remained limited to the SBF V8 repository and its `main` branch; it did not touch the unrelated repositories/sites named in the job, access or use secrets, or install software.

## §0 — Resolved disagreements

- **302 / Windsor production end:** The claims paper called the “302 in 2001” wording an error, while the sources paper found the 1968–2001 span consistent when read as model years. QA agreed that the evidence does not establish an error. Keep the existing range; year-by-year applications remain VERIFY because no factory application chart was readable.
- **SAE gross/net wording:** The claims paper called the unqualified transition an error. The source and QA reviews found the broad U.S. passenger-car transition plausible but recommended scoping the explanation. Reclassify as a NIT and make that scope explicit; do not change the horsepower values.
- **351W firing-order explanation:** The sources paper flagged the causal phrase about a different crank and cam layout. The order strings and their assignment to standard Windsor versus HO/351W were not disputed. Remove the unsupported causal clause as a NIT while retaining the page’s instruction to verify the cam card; do not change either firing-order sequence.
- **Torque and clearance values:** The specs paper found the family layout and assembly guidance coherent, but neither it nor the sources paper had readable, exact Ford service-manual pages for each year, casting, and stock fastener. The sources identify real disagreements (especially 351W head bolts and 302 rod bolts). Therefore those figures remain VERIFY; do not choose a value from a secondary chart or revise torque rows.
- **Dead source links:** The source audit found the Engine Builder page returned 403 and the Maine Mustang page returned 404. Working Internet Archive copies were independently checked and returned HTTP 200; §1 replaces only those two destinations and labels them as archived.
- **Authorization scope:** The Yes response to questions 8 and 9 does not expand this job beyond the explicit SBF V8 repo scope. No unrelated property was touched and no secret was accessed or used.

## §1 — ERROR fixes

1. **Engine Builder source link — `index.html:1113`.** The current direct URL returns HTTP 403. Replace it with the verified HTTP 200 archived copy:
   `https://web.archive.org/web/20250818174311/https://www.enginebuildermag.com/2013/04/revised-cylinder-head-bolt-and-torque-procedures-for-88-95-ford-5-0l-engines/`
   Label the link as an archived copy. The archived article is the cited secondary source for the two 1988–95 5.0L head-bolt procedures; it is not a substitute for the applicable factory manual.
2. **Maine Mustang source link — `index.html:1116`.** The current URL returns HTTP 404. Replace it with the verified HTTP 200 archived copy:
   `https://web.archive.org/web/20220318073915/http://mainemustang.com/mustang-info/ford-engine-bolt-torque-chart`
   Label the link as an archived copy. No torque value is changed by restoring this cross-check reference.

## §2 — VERIFY; leave unchanged

1. **Production years and applications** — `index.html:447–451, 507–514, 536–537, 1190–1194`. Verify the 221, 260, 289, 302, and 351W model-year/application ranges against the correct Ford year/model application charts. In particular, retain “1968–2001” as the current model-year range, not a calendar-year claim, until factory application evidence is attached.
2. **Factory specifications and compression ranges** — `index.html:536–555, 557`. Bore/stroke arithmetic and metric conversions pass, but exact factory-year specifications, compression endpoints, and the 351W 9.480/9.503-in deck-height year split lack readable, year-specific factory evidence in this audit. Verify against the applicable Ford manual or engineering drawing.
3. **Horsepower and gross/net rating conditions** — `index.html:565–600, 1190–1194`. The chart widths and scales are arithmetically consistent. Verify representative horsepower/torque figures, model-year mapping, and rating conditions against period Ford publications. Peak horsepower rpm and peak torque are not necessarily simultaneous, so the page’s available values do not establish an `hp = torque × rpm / 5252` error.
4. **Summit Racing citation content** — `index.html:1112`. The link returns HTTP 200 but served an Incapsula challenge instead of the cited torque article. Its contents were not readable here; keep it as VERIFY and do not treat the status code alone as source validation.
5. **Stock torque values by engine/year/hardware** — `index.html:731–753, 757, 889–892, 946–949`. Exact stock values require the applicable Ford service manual. In particular, 351W head-bolt sources disagree (the page lists 90–100 ft-lb while other cited material lists 105–112 ft-lb), and 302 rod-bolt values vary by application. Keep the existing warnings and table unchanged pending the exact manual; do not substitute 351C, FE, or other-family figures.
6. **Bearing and assembly clearances** — `index.html:812, 826–831, 884–894, 1088–1092`. Verify main/rod clearance ranges, the 0.0021-in allowable main limit, end play, piston-to-wall, and rod side-clearance values against the exact stock 302 manual and applicable parts. The linked Ford Performance PDF is for a 347-ci stroker kit and does not substantiate stock 302 limits.
7. **Operating values and capacities** — `index.html:926–930, 964–1006, 1083–1092, 1159–1168`. Verify oil/coolant capacity, pickup clearance, oil pressure, base timing, plug gap, preload/lash, and break-in figures for the specific model year and configuration. The page’s existing measurement and manual-check cautions remain important.

## §3 — NIT fixes

1. **Scope the gross/net explanation** — `index.html:565`. Change the lead sentence to identify U.S.-market passenger-car SAE ratings, for example: “For U.S.-market passenger-car ratings, Ford advertised SAE gross horsepower through 1971; from 1972, ratings were SAE net — measured as installed. The two are not comparable.” This is a scope clarification, not a horsepower correction.
2. **Remove the unsupported firing-order cause** — `index.html:1075`. Replace the first sentence’s “because of its different crank and cam layout” explanation with a neutral statement, for example: “The 351W uses the later order. A 302 with an HO cam also uses 1-3-7-2-6-5-4-8 — the order follows the camshaft, not simply the block.” Keep both firing-order strings and the cam-card warning unchanged.

## §4 — DO NOT TOUCH

- Displacement calculations from the displayed bore and stroke, including the 255-ci timeline variant, pass; the 302’s 4,942-cc figure is consistent with the nominal 4.000 × 3.000-in dimensions.
- Displayed inch-to-millimeter conversions, blueprint dimensions, journal-size differences, and repeated dimension values are internally consistent.
- Keep both firing-order sequences as shown: standard Windsor `1-5-4-2-6-3-7-8`; 5.0 HO / 351W `1-3-7-2-6-5-4-8`. Keep the cylinder numbering as shown.
- Keep the main-cap `3-2-4-1-5` and head-bolt `9-5-1-3-7 / 10-6-2-4-8` sequences and their diagrams.
- Keep the 1988–95 5.0L hex-versus-TTY distinction, no-mixing warning, and single-use TTY warning; the accessible archived article supports those cautions.
- Torque-table ft-lb/Nm conversions and repeated values match arithmetically. No torque-row replacement met the evidence threshold for an ERROR correction; do not silently resolve the source disagreements.
- Keep the warning that stock torque figures assume clean, lightly oiled fasteners and that aftermarket hardware requires its own instructions.

## §5 — Verification steps

1. Review the diff and confirm only the two source destinations/labels in §1 and the two wording changes in §3 changed in `index.html`; confirm §2 values and the torque table are untouched.
2. Check the external source links in `index.html` with redirected HTTP GETs. In particular, the two archive destinations in §1 returned HTTP 200 during this audit; note that the Summit link’s HTTP 200 challenge page remains a §2 content-verification item.
3. Serve the repo locally on loopback only with `python3 -m http.server 8000 --bind 127.0.0.1`; load `/` and confirm the page, diagrams, tables, and scripts render. Stop the local server after QA.
4. Independently confirm the two archived links, the changed wording, and the unchanged §2 locations; check the rendered page locally.
5. Commit the report and working papers separately from the page fixes, push both commits to `origin main`, compare local and remote logs, and check the live Pages URL for HTTP 200.

## Appendix — Torque rows retained (no corrected rows)

No torque-table row is approved for replacement: the accessible evidence does not establish a single year-independent factory value where sources disagree. The following rows are transcribed from the existing table as a guard against accidental edits; they are **not** new values to apply. Keep the existing notes and §2 verification warnings.

| Fastener | 221–302 (ft-lb) | 351W (ft-lb) | Nm (221–302 / 351W) |
|---|---:|---:|---:|
| Main cap bolts | 60–70 | 95–105 | 81–95 / 129–142 |
| Connecting rod bolts | 22–25 | 40–45 | 30–34 / 54–61 |
| Cylinder head bolts | 65–72 | 90–100 | 88–98 / 122–136 |
| Rocker arm nuts | 17–23 | 17–23 | 23–31 |
| Intake manifold | 23–25 | 23–25 | 31–34 |
| Exhaust manifolds | 18–24 | 18–24 | 24–33 |
| Valve covers | 3–5 | 3–5 | 4–7 |
| Spark plugs | 10–15 | 10–15 | 14–20 |
| Oil pump bolt | 23–28 | 23–28 | 31–38 |
| Oil pan | 7–11 | 7–11 | 9–15 |
| Harmonic damper | 70–90 | 70–90 | 95–122 |
| Flywheel / flexplate | 75–85 | 75–85 | 102–115 |
| Cam sprocket bolt | 40–45 | 40–45 | 54–61 |
| Cam thrust plate | 8–10 | 8–10 | 11–14 |
| Front cover | 12–15 | 12–15 | 16–20 |
| Water pump | 12–18 | 12–18 | 16–24 |
| Thermostat housing | 12–15 | 12–15 | 16–20 |
| Pressure plate | 35 | 35 | 47 |
| Bellhousing | 28–38 | 28–38 | 38–52 |
