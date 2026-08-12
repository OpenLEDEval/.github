# OpenDisplayEval

Open-source tools for objective, reproducible display evaluation.

OpenDisplayEval provides a standardized methodology and software toolkit for measuring and reporting display colour fidelity. The project originated in LED panel evaluation, and the toolset now supports any display technology — LED walls, OLED monitors, projectors, and beyond. Rather than relying on manufacturer-reported best-case specs, it captures hundreds of stimulus-response pairs using a spectroradiometer and generates distribution-based metrics (mean + 95th percentile) that reflect real-world performance. The entire analysis pipeline — metrics, tolerances, and visualizations — is open and independently verifiable.

## Repositories

| Repository | Description |
|---|---|
| [**display-report**](https://github.com/OpenDisplayEval/display-report) | Measurement and reporting suite — drives a test pattern generator and spectroradiometer to capture display measurements, then analyzes the colorimetric data and produces a standardized PDF fidelity report |
| [**display-patterns**](https://github.com/OpenDisplayEval/display-patterns) | Test pattern and chart generation library — checkerboards, colour cubes, and temporal-alignment counter panels, rendered to numpy arrays or TIFF |
| [**bmd-signal-gen**](https://github.com/OpenDisplayEval/bmd-signal-gen) | Signal generator for Blackmagic Design DeckLink devices with full HDR metadata support, 12-bit RGB output, and both CLI and Python API interfaces |
| [**methodology**](https://github.com/OpenDisplayEval/methodology) | Evaluation methodology, test specifications, and organizational records |

## How It Works

1. **Generate** — Send precisely defined PQ-encoded test colours to a display via a Blackmagic DeckLink device using bmd-signal-gen
2. **Measure** — Capture the display's light output with a spectroradiometer (e.g. Colorimetry Research CR-300)
3. **Analyze** — Compare stimulus vs. response using perceptual colour metrics (dE 2000, dE ITP, EOTF tracking, white point stability)
4. **Report** — Generate a standardized PDF with colour-coded tolerance bands based on just-noticeable-difference (JND) thresholds

## A note on the name

This organization was previously **OpenLEDEval**. The rename reflects that the
toolset applies to any display technology, not only LED. GitHub redirects old
`OpenLEDEval/*` URLs, so existing clones and links continue to work.
