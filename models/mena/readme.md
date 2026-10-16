# Mena

**Mena** is a 2.66M-parameter machine learning interatomic potential with a smooth 6.0 Å radial cutoff (tapering neighbor interactions between 5.0 Å and 6.0 Å), trained on MPtrj for 15.5 hours on a single NVIDIA A100-SXM4-40GB GPU (`Muon + AdamW`, 37 epochs) and evaluated locally on an Apple M3 Max (36GB).

![Mena Benchmark Summary](./mena-results.svg)

## Benchmark Summary (Matbench Discovery — Compliant Track)

| Task / Metric | Unique Prototypes (`215,488`) | Full Test Set (`256,963`) | Notes |
| --- | ---: | ---: | --- |
| **Combined Performance Score (CPS ↑)** | **0.7859** | — | Official leaderboard formula (`fillna=1.0` RMSD) |
| **F1 ↑** | **0.8232** | 0.8103 | Stability classification (`E_hull <= 0`) |
| **DAF ↑** | **5.1904** | 4.6694 | Discovery Acceleration Factor |
| **Precision ↑** | **0.7935** | 0.7782 | `TP / (TP + FP)` |
| **Recall ↑** | **0.8552** | 0.8451 | `TP / (TP + FN)` |
| **Accuracy ↑** | **0.9438** | 0.9340 | Overall classification accuracy |
| **MAE ↓ (eV/atom)** | **0.0339** | 0.0327 | Formation energy (`E_form`) MAE |
| **RMSE ↓ (eV/atom)** | **0.0761** | 0.0767 | Formation energy (`E_form`) RMSE |
| **R² ↑** | **0.8290** | 0.8193 | Coefficient of determination |
| **RMSD ↓ (unitless)** | — | **0.0744** (`0.0172` matched) | `StructureMatcher(stol=1.0)` (`0.0059` median, `91.1%` spacegroup match) |
| **Phonons `κ_SRME` ↓** | — | **0.3803** | 103 PhononDB crystals (`κ_SRE = 0.2114`, `κ_SRD = -0.1162`, `0%` imaginary/failed) |
| **Diatomics `CDS` ↑** | — | **0.5402** | Homo-nuclear diatomics (`100%` valid coverage, `73/73` elements) |

## Contact

Francesco Viola (`francesco.viola001@studenti.uniparthenope.it`)
