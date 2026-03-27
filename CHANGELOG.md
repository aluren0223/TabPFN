# Changelog

All notable changes to TabPFN are documented here.

## [2.0.7] - 2025

### Fixed
- Various bug fixes and stability improvements.

## [2.0.0] - 2025-01-09

### ⚠️ Breaking Changes
- Complete codebase overhaul with new architecture. The previous v1 API is no longer compatible.
- Previous version remains available at [v1.0.0](../../tree/v1.0.0) and via `pip install tabpfn==0.1.11`.
- Python 3.9+ is now required (dropped support for Python 3.8).

### Added
- **TabPFNClassifier**: New sklearn-compatible classifier interface supporting binary and multi-class classification.
- **TabPFNRegressor**: New sklearn-compatible regressor interface for tabular regression tasks.
- **CUDA optimization**: Significantly improved GPU performance for large datasets.
- **Native missing value support**: TabPFN now handles missing values (NaN) without preprocessing.
- **AutoTabPFN** support via [TabPFN Extensions](https://github.com/PriorLabs/tabpfn-extensions): Post-hoc ensembling with `AutoTabPFNClassifier` and `AutoTabPFNRegressor` for best-in-class results.
- **Offline model usage**: Models can be downloaded in advance and used without internet access. See the [download script](scripts/download_all_models.py) or manual instructions in the README.
- **HuggingFace Hub integration**: Model weights are automatically downloaded from HuggingFace on first use.
- **New model architecture**: Transformer-based foundation model trained on a large corpus of tabular datasets, published in [Nature (2025)](https://doi.org/10.1038/s41586-024-08328-6).
- Support for datasets up to **10,000 rows**.
- Support for Python **3.9, 3.10, 3.11, 3.12, 3.13**.

### Changed
- Moved from single-file implementation to a full package structure under `src/tabpfn/`.
- Model weights are now versioned and hosted on HuggingFace (`Prior-Labs/TabPFN-v2-clf` and `Prior-Labs/TabPFN-v2-reg`).

### Performance
- Outperforms traditional methods (XGBoost, Random Forests, etc.) on small tabular datasets while being dramatically faster to fit.
- GPU recommended for datasets larger than ~1,000 samples; CPU is feasible for small datasets.

---

## [0.1.11] - 2023 (v1 legacy)

The original TabPFN v1 release. See the [v1.0.0 tag](../../tree/v1.0.0) for the full history.

- TabPFN: A transformer that solves small tabular classification problems in a second ([ICLR 2023](https://openreview.net/forum?id=cp5PvcI6w8_)).
