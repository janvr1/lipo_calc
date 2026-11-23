# LiPo Field Charge Calculator

A single-page web calculator (in Slovenian, branded for [LiPo.si](https://www.lipo.si/)) that estimates how many times you can recharge a
LiPo pack from a larger "field battery" (big LiPo, LiFePO₄, or 12 V lead-acid/AGM).

## Modes

- **Kako velik akumulator potrebujem?** (default) – enter the required number of full charges, get the field battery capacity (Ah / Wh) you need.
- **Kolikokrat lahko napolnim?** – enter the field battery capacity, get the number of charges.

## How it works

Everything is converted to watt-hours:

```
Field Wh     = V × Ah × usable%
Delivered Wh = Field Wh × charger efficiency
Pack Wh      = cells × cell voltage × Ah × used%
Charges      = Delivered Wh ÷ Pack Wh

Required Wh  = Pack Wh × packs × charges ÷ efficiency ÷ usable%
Required Ah  = Required Wh ÷ V
```

## Run locally

Just open `index.html` in a browser — no build step, no dependencies.

## Hosting on GitHub Pages

The workflow in `.github/workflows/pages.yml` deploys the site on every push to `main`.
One-time setup: in the repo go to **Settings → Pages → Build and deployment → Source**
and choose **GitHub Actions**.

The site will then be available at `https://<user>.github.io/lipo_calc/`.
