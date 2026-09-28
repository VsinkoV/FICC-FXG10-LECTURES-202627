# Currency Report Card: LaTeX package

One-page Bristol Trading Society Currency Report Card in University of Bristol colours. The layout follows the page template from Lectures 1 to 5.

| File | What it is |
|---|---|
| `report-card-template.tex` | **Blank page.** Copy it for your currency and fill in every `[BRACKET]` |
| `usd-october-2026.tex` | Completed example: US dollar, October 2026 outlook |
| `bts-reportcard.sty` | The package: colours, fonts, layout and macros |
| `bts-logo.png`, `uob-logo.png` | Bristol Trading Society and University of Bristol logos |

## Compile
- **Overleaf:** upload the whole folder and set the compiler to pdfLaTeX. Overleaf has IBM Plex and Source Serif installed, so the page uses them.
- **Locally:** `pdflatex report-card-template.tex`. Without those fonts it falls back to Helvetica and Times.

## Editing cheatsheet
- **Accent colour:** `\usepackage[red]{bts-reportcard}` (options: `red`, `olive`, `ink`)
- **Header:** `\currency{}`, `\subtitle{}`, `\analyst{}`, `\asof{}`, `\issue{}`, `\tacticalview{}`, `\structuralview{}`
- **Outlook boxes:** `\begin{outlook}{title}{headline}` with `\point{Priced}{...}` lines
- **Indicators panel:** `\indicator{label}{value}`; use `\lastindicator` for the last row
- **Driver tags:** `\drivertagpos{...}` (supportive) and `\drivertagneg{...}` (against)
- **Charts:** `\begin{chartbox}{Chart 1}{claim}{source}` holding `\includegraphics`, a `pgfplots` axis with `[btschart]`, or `\chartplaceholder`
- **Trade idea:** `\traderow{Entry}{...}`; use `\lasttraderow` for the last row
- **Forecasts:** `\forecastrow{pair}{horizon}{spot}{forward}{forecast}{comment}`
- **Forward calculator:** `\fxforward[dp]{spot}{base rate %}{quote rate %}{years}` gives S × (1 + r_quote·t) / (1 + r_base·t)
