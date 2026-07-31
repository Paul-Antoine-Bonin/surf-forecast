# surf-forecast: a wave quality model for a handful of spots

## Goal
Predict session quality on Portuguese spots from swell, wind and tide data, and compare
the model against public forecasts.

## Data
- Open-Meteo Marine API: swell (height, period, direction), wind. Free, no key.
- Spots to define: Carcavelos, Ericeira, Costa da Caparica, or your actual spots.
- Labels: your own session ratings. That is what makes the project impossible to copy,
  and it is also the slowest part. Start rating from day one.

## Steps
- [ ] Set up repo, Open-Meteo Marine client, daily Parquet storage
- [ ] Define the coordinates and the orientation of each spot
- [ ] Daily collector: forecasts and realised data, archived by date
- [ ] Build the physical features: usable swell projected onto the spot orientation,
      offshore against onshore wind, period, tide coefficient
- [ ] Explicit physical scoring model, no learning, as the baseline
- [ ] Simple session rating interface (score out of 5 plus a comment)
- [ ] Once enough ratings have accumulated: regression of the score on the features
- [ ] Compare the physical model, the learned model, and the public forecast
- [ ] README: the features that actually matter, spot by spot

## Done when
The collector has been running for several months, and the README shows which variables
really explain a good session at each spot.

## Traps
- Without labels there is no learned model. The explicit physical score is the version
  that works from day one, so build that one first.
- Do not scrape ratings from a commercial service. Build your own labels.
