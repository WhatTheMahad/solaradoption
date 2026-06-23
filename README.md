# solaradoption

**Solar Adoption in Pakistan**, a civic-tech data visualization tracking Pakistan's
rooftop solar / net-metering boom by DISCO, framed around the February 2026 shift from
net metering to net billing.


## What is this?

A single static page that:

- Shows Pakistan's net-metering adoption by DISCO at a glance via a 20×20 dot grid
  (each dot = 0.25% of households), split into **net-metered solar / off-grid solar /
  grid-only / unelectrified**.
- Frames the data through the **Feb 2026 policy shift** (net metering → net billing) — the
  editorial centerpiece, with a before/after comparison.
- Is built to be shared and cited: one URL, credible numbers, NEPRA as the primary source.

Not a dashboard, calculator, or tool — a **publication** with one strong visual.

## The DISCOs

National rollup plus 11 distribution utilities:

| Utility | Region | NM capacity | Share |
|---------|--------|------------:|------:|
| LESCO | Punjab — Lahore | ~1,300 MW | 21% |
| IESCO | Islamabad / Rawalpindi | ~915 MW | 15% |
| K-Electric | Karachi (private) | ~915 MW | 15% |
| MEPCO | South Punjab — Multan | ~790 MW | 13% |
| FESCO | Faisalabad | ~670 MW | 11% |
| GEPCO | Gujranwala | ~610 MW | 10% |
| PESCO | Khyber Pakhtunkhwa | ~305 MW | 5% |
| HESCO | Sindh — Hyderabad | ~245 MW | 4% |
| QESCO | Balochistan | ~183 MW | 3% |
| SEPCO | Sindh — Sukkur | ~122 MW | 2% |
| TESCO | Tribal districts | ~61 MW | 1% |

National total ≈ **6.1 GW** across ≈ **283,000** active net-metering connections (mid-2025).

## Data — confidence tiers

This project takes sourcing seriously, so it distinguishes two tiers (see the in-app FAQ):

- **Well-sourced** — national capacity (~6.1 GW), connections (~283,000), growth (4.9→6.1 GW
  in H1 2025), and the capacity *share* of the major DISCOs. From NEPRA and Renewables First.
- **Modeled estimates** — exact per-DISCO connection *counts* and the household-level
  breakdown (net-metered / off-grid / grid-only / unelectrified). Derived from each DISCO's
  NEPRA capacity share scaled to the national total, anchored on LESCO's ~91,500. These are
  directional, not exact.

> **Next refresh priority:** replace the modeled per-DISCO figures with the line-item table
> from the latest NEPRA State of the Industry Report.

## The Feb 2026 policy shift

NEPRA's Prosumer Regulations 2026 replaced net metering with net billing:

| | Before (net metering) | After (net billing) |
|---|---|---|
| Export buyback | Rs 22–27 / kWh | ~Rs 11 / kWh |
| Billing basis | Unit-for-unit offset | Import & export priced separately |
| Contract | 7 years | 5 years |
| Payback | 3–4 years | 6–8 years |

Existing net-metering consumers are generally honored for the rest of their contracts.

## Data sources

- **NEPRA — State of the Industry Report** (annual, FY-based) — primary authority
- **NEPRA — Prosumer Regulations 2026** — the policy shift
- [Renewables First — Pakistan Electricity Review 2025](https://uploads.renewablesfirst.org/Pakistan_Electricity_Review_2025_89f0b613d6.pdf) and the PECI solar tracker (cross-validation)
- [pv-magazine — Pakistan adds 1.2 GW net-metering in H1 2025](https://www.pv-magazine.com/2025/08/06/pakistan-adds-1-2-gw-of-net-metering-capacity-in-h1/)
- [pv-magazine — Pakistan unveils new net-metering rules (Dec 2025)](https://www.pv-magazine.com/2025/12/18/pakistan-unveils-new-net-metering-rules-for-rooftop-pv/)
- Ember, IEEFA, Pakistan Bureau of Statistics (PV imports)

NEPRA is cited as the authority; PECI is used for QA, not as the source of record.

## Tech stack

Single `index.html`: React 18 UMD + Babel standalone (both from unpkg), all data inline.
No build step, no backend. Mobile-first, max-width 760px. Fonts: DM Sans (UI) + JetBrains
Mono (numbers). Accent: sun-yellow `#f5a524`.

## Run locally

```bash
python3 -m http.server 8090   # then open http://localhost:8090
# or: npx serve .
# or: open index.html directly
```

## Deploy

Static — drop on Vercel (or any static host). Add an `og.png` (a screenshot of the dot
grid) at the site root for the Twitter/LinkedIn share preview; the meta tags already
reference `/og.png`.


## License

MIT
