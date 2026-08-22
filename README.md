# Predictive Maintenance Baseline Study

**Leakage-safe remaining-useful-life modeling on NASA C-MAPSS FD001**

**Status:** Complete — 21/21 validation checks passed

A reproducible predictive-maintenance study that estimates turbofan remaining useful life while keeping validation engines separate and preventing rolling features from crossing engine boundaries.

[View the notebook](https://github.com/Abdulrahman-Albeladi/predictive-maintenance-baseline/blob/main/predictive_maintenance_baseline_study.ipynb) · [Open in Google Colab](https://colab.research.google.com/github/Abdulrahman-Albeladi/predictive-maintenance-baseline/blob/main/predictive_maintenance_baseline_study.ipynb)

## What this project does

- Parsed NASA C-MAPSS FD001 train, test, and RUL files.
- Constructed cycle-safe rolling sensor features within each engine.
- Split validation by engine rather than by rows.
- Compared Ridge regression and XGBoost under the same evaluation protocol.
- Used engine-level bootstrap intervals, SHAP, and five terminal failure cases.

## Results and current evidence

- 100 FD001 training engines modeled
- XGBoost RMSE: 17.351 cycles; MAE: 12.909 cycles
- XGBoost R²: 0.826
- NASA asymmetric score: 491.452
- 21/21 validation checks passed

The published notebook contains 11 stored output objects and 0/10 code cells with execution counts.

## Repository contents

```text
.
├── predictive_maintenance_baseline_study.ipynb
├── README.md
├── requirements.txt
├── data/
│   └── README.md
├── CITATION.cff
├── NOTICE.md
├── LICENSE
└── repo_manifest.json
```

## Run the notebook

1. Clone the repository or open the Colab link.
2. Create a fresh Python environment if running locally.
3. Install the dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Read the notebook's configuration cell and data note.
5. Restart the kernel and run all cells in order.
6. Use the final validation table as the completion gate. Do not reuse a metric when its check fails.

## Data

Source: [NASA C-MAPSS Jet Engine Simulated Data](https://data.nasa.gov/dataset/cmapss-jet-engine-simulated-data)

NASA source files are downloaded or supplied locally and are not committed to the repository.

See [`data/README.md`](data/README.md) before adding any local files. Large data, generated outputs, databases, credentials, and model weights are intentionally excluded from Git.

## Validation approach

The notebook contains project-specific assertions, smoke checks, and a final evidence table. Its SHA-256 digest and cell counts are recorded in `repo_manifest.json` for integrity checks.

## Limitations

- The study uses FD001 only, with one operating condition and one fault mode.
- The model is a baseline study rather than a deployed maintenance policy.
- Sensor attribution does not establish a causal mechanism of degradation.

## Reproducibility and provenance

[`repo_manifest.json`](repo_manifest.json) records the notebook digest, size, and cell counts for integrity checks.

## License

The original code and documentation in this repository are available under the MIT License. Dataset, model, and third-party package licenses remain with their respective owners; see [`NOTICE.md`](NOTICE.md).
