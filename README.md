# 20261107 — Small Block Ford V8 Technical Reference

A single-page, self-contained technical reference for the Ford Windsor small block V8 family: **221, 260, 289, 302, and 351W**, with a 302 build deep-dive.

**Live site:** https://ruddyrid.github.io/20261107-sbf-v8-tech/

## What it covers

- Factory specifications side by side: bore, stroke, deck height, rod length, journals, compression, valvetrain, induction, and output
- Brake horsepower explained — SAE gross vs. net, with representative rating bars
- Blueprint dimensions and an interactive front-elevation diagram
- Stock fastener torque table with category filters, search, click-to-copy, and SAE/metric conversion
- A 10-stage 302 assembly sequence with clearances, torque values, main-cap and head-bolt sequence diagrams, and saved progress
- Firing orders, cylinder numbering, fluid capacities, and a printable one-page pit card

## Notes

- Torque figures assume clean, lightly oiled **stock** fasteners. ARP, studs, and torque-to-yield hardware use their own procedures.
- Where sources disagree, the page says so rather than silently choosing a value.
- This is a study aid, not a service manual. Verify clearances with measuring tools and torque with a calibrated wrench; the factory manual for your engine wins.

## Local use

Open `index.html` directly in a browser. No build step, no server, no dependencies beyond Google Fonts (with system fallbacks).

## Build notes

Technical data was audited with Claude; design and accessibility QA was reviewed with GitHub Copilot. All interactive behavior was verified in headless Chromium at 390, 768, and 1440 px, plus print output.
