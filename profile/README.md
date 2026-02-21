# OpenLEDEval

Open-source tools for objective, reproducible display evaluation.

OpenLEDEval provides a standardized methodology and software toolkit for measuring and reporting display color fidelity. While the project originated in LED panel evaluation, the toolset supports any display technology — LED walls, OLED monitors, projectors, and beyond. Rather than relying on manufacturer-reported best-case specs, OpenLEDEval captures hundreds of stimulus-response pairs using a spectroradiometer and generates distribution-based metrics (mean + 95th percentile) that reflect real-world performance. The entire analysis pipeline — metrics, tolerances, and visualizations — is open and independently verifiable.

## Repositories

| Repository | Description |
|---|---|
| [**OpenLEDEval**](https://github.com/OpenLEDEval/OpenLEDEval) | Evaluation methodology, test specifications, and reference materials |
| [**OLE-Toolset**](https://github.com/OpenLEDEval/OLE-Toolset) | Self-contained measurement suite — drives a test pattern generator and spectroradiometer to capture display measurements, then analyzes colorimetric data and produces standardized PDF fidelity reports |
| [**bmd-signal-gen**](https://github.com/OpenLEDEval/bmd-signal-gen) | Test pattern generator for Blackmagic Design DeckLink devices with full HDR metadata support, 12-bit RGB output, and both CLI and Python API interfaces |

## How It Works

1. **Generate** — Send precisely defined PQ-encoded test colors to a display via a Blackmagic DeckLink device using bmd-signal-gen (integrated directly as a library)
2. **Measure** — Capture the display's light output with a spectroradiometer (e.g. Colorimetry Research CR-300)
3. **Analyze** — Compare stimulus vs. response using perceptual color metrics (dE 2000, dE ITP, EOTF tracking, white point stability)
4. **Report** — Generate a standardized PDF with color-coded tolerance bands based on just-noticeable-difference (JND) thresholds
