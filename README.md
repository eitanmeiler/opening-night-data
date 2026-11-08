# Opening Night: live box office forecasts

Live data for **Opening Night**, Eitan Meiler's pre-registered study of what predicts a US film's opening weekend.
For each wide release this season, the file records:

- **our forecast**, locked in before release, with an 80% range;
- **Hollywood's forecast**, Boxoffice Pro's last published pre-release range;
- **the actual opening**, with source and date.

It also records who came closer.

`results.json` is the only data file. It powers the Opening Night page on [eitanmeiler.com](https://eitanmeiler.com/opening-night.html)
and is updated automatically: forecasts are added before each opening, and results the weekend after.

## Why the git history matters

From November 2026 on, each forecast is committed here **before** the film opens, so anyone can check, in this
repo's commit history, that no forecast was changed after the fact. Forecasts made before this repo existed were
committed to the (private) research repository first; they are marked as such in the data.

## How to read it

| Field | Meaning |
|---|---|
| `ours.forecast_m`, `low_m`, `high_m` | Model forecast and 80% range, $ millions |
| `hollywood` | Boxoffice Pro range; `mid_m` is used for scoring |
| `actual.status` | `saturday_projection`, `sunday_estimate` or `bom_actual` (final) |
| `grade.*_miss_pct` | \|actual / forecast − 1\| × 100 |
| `kind: draft` | The Oct 23 films were scored on drafts committed Oct 20 (the planned one-week lock-in did not run) |
| `side_case` | Limited releases outside the model's population: shown, not scored |
