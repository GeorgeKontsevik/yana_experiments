# yana_experiments

Route-generation and street-pattern evaluation experiments, including live previews for real-morphology training runs.

## System Map

```mermaid
flowchart LR
    CITY[city graph] --> TRAIN[real_morph_training_eval]
    TRAIN --> ROUTES[existing vs generated routes]
    ROUTES --> PATTERN[street-pattern comparison]
    PATTERN --> PREVIEW[live preview PNGs]
```

## Main Result

![Existing vs generated routes](real_morph_training_eval/bergen_norway/live_preview/latest_05_existing_vs_generated_vs_street_pattern_routes.png)

## Run

Entrypoint: `street_pattern_route_comparison/`

Human:

```bash
uv run python -m street_pattern_route_comparison --help
```

Agent: compare generated routes against existing routes and street-pattern labels; preserve duplicate/failed route cases as evidence instead of forcing diversity.

## Publication

No standalone publication tracked; experiment repo for dissertation route-generation work.

## Next Steps / Heuristics

Heuristic: the live preview is the first sanity check. If route geometry looks wrong, inspect graph/stops before interpreting metrics.
