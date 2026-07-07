# yana_experiments

---

[![OSA-improved](https://img.shields.io/badge/improved%20by-OSA-yellow)](https://github.com/aimclub/OSA)

---

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Architecture](#architecture)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Citation](#citation)

---

## Overview

`yana_experiments` is a Python-based experiment ledger for route-generation and street-pattern evaluation, focused on storing and reviewing generated artifacts such as route summaries, OD matrices, and preview images. It is intended for developers and researchers working on dissertation experiments, especially when checking outputs from the upstream parent pipeline and ConnectPT workflow rather than running generation locally. If you are new to the repository, start with the artifact review guidance in the README and the Getting Started material for any runnable steps or inspection workflow.

---

## Installation

**Prerequisites:** requires Python >=3.11

Install yana_experiments using one of the following methods:

**Build from source:**

1. Clone the yana_experiments repository:
```sh
git clone https://github.com/GeorgeKontsevik/yana_experiments
```

2. Navigate to the project directory:
```sh
cd yana_experiments
```

3. Install the project dependencies:

```sh
pip install -r requirements.txt
```

---

## Getting Started

This repository is an artifact workspace for route-generation experiments, so there is no local generator to run here. You only need Python 3.11+ if you want to work with the repository metadata; `pyproject.toml` does not list runtime dependencies.

1. Clone the repository and enter it.
2. Optionally check the workspace state:

```bash
make status
```

3. Inspect the saved experiment outputs. The README points to `real_morph_training_eval/bergen_norway/live_preview/` as the entrypoint for live previews, and recommends reviewing `summary.json`, OD matrices, and preview PNGs.
4. To find the saved summaries and images, use the documented search command:

```bash
find real_morph_training_eval street_pattern_route_comparison -name 'summary.json' -o -name '*.png'
```

5. Review the generated artifacts directly before drawing conclusions; the repository notes that visual sanity checks of the preview PNGs are the first check for route geometry.

---

## Architecture

`yana_experiments` is an artifact-led experiment workspace rather than the runnable route generator. The upstream parent pipeline / ConnectPT stack produces the outputs; this repository stores the resulting experiment artifacts for review.

- **Experiment inputs and outputs are organized by scenario/workflow**: the README’s system map shows `bare_od_route_generation`, `direct_connectpt`, `real_morph_training_eval`, and `street_pattern_route_comparison` as the main experiment branches.
- **Each branch emits reviewable artifacts** such as route preview PNGs, summary JSON, OD matrices, and pattern statistics/plots.
- **Manual review is part of the workflow**: the README routes these artifacts into a review step, and the recommended checks focus on `summary.json`, OD matrices, and preview images.
- **Local code boundaries are minimal** in the provided context: `pyproject.toml` marks the project as a non-package workspace with no runtime dependencies, and the Makefile only exposes basic repository status/check helpers.
- **Operational guidance lives in docs** (`README.md`, `AGENTS.md`, `CONTRIBUTING.md`) rather than in an in-repo application runtime, which reinforces the repository’s role as an experiment ledger.

---

## Documentation

A detailed yana_experiments description is available [here](https://github.com/GeorgeKontsevik/yana_experiments/tree/main/docs).

---

## Contributing

- **[Report Issues](https://github.com/GeorgeKontsevik/yana_experiments/issues)**: Submit bugs found or log feature requests for the project.

- **[Submit Pull Requests](https://github.com/GeorgeKontsevik/yana_experiments/tree/main/CONTRIBUTING.md)**: To learn more about making a contribution to yana_experiments.

---

## Citation

If you use this software, please cite it as below.

### APA format:

    GeorgeKontsevik (2026). yana_experiments repository [Computer software]. https://github.com/GeorgeKontsevik/yana_experiments

### BibTeX format:

    @misc{yana_experiments,

        author = {GeorgeKontsevik},

        title = {yana_experiments repository},

        year = {2026},

        publisher = {github.com},

        journal = {github.com repository},

        howpublished = {\url{https://github.com/GeorgeKontsevik/yana_experiments}},

        url = {https://github.com/GeorgeKontsevik/yana_experiments}

    }

---