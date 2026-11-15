# AirAware demo

A browser demo for predicting next-day PM2.5 near Rutgers University, New Jersey. Visitors can choose a 2026 input date, compare models, and view recorded air quality when available.

## Publish this demo

1. Create a public GitHub repository, such as `airaware`.
2. Upload the **contents of this folder** to the repository's top level. `index.html` and `airaware_export.json` must sit beside each other, rather than inside a `GitHub Demo` subfolder.
3. Open **Settings > Pages**. Set **Source** to **Deploy from a branch**.
4. Select **main** and **/(root)**, then click **Save**.
5. When GitHub finishes publishing, open the website URL shown in Pages settings and share it with visitors.

The demo URL follows `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY/`. The normal repository URL shows source files; the Pages URL opens the working interface.

Official guide: [Configure a GitHub Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The complete UI and browser inference code. |
| `airaware_export.json` | Fitted models, daily data, and validation results. |
| `.nojekyll` | Serves the folder as static files. |
| `README.md` | These instructions and demo notes. |

The published demo runs entirely in the browser. Visitors need no downloads, Python installation, Colab session, or Google Drive access.

## What the demo predicts

- Models: Linear Regression, Random Forest, and an ensemble with pollution history.
- Selecting input day D forecasts D+1. The history ensemble uses PM2.5 from D and its two preceding calendar days, plus D's weather.
- Actual PM2.5 and EPA AQI are shown when present in the exported observations.
- The data snapshot ends November 13, 2026. Missing inputs prevent a prediction; missing observations are displayed as unavailable.
- Prediction units are micrograms per cubic meter, not AQI. This historical prototype is not a live feed or official air-quality advisory.

## Update the demo

After retraining in Colab, replace this repository's `airaware_export.json` with the new export. Update `index.html` if the interface changes. Keep both files together; GitHub Pages publishes committed changes from the selected branch.
