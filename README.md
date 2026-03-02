# R2M-estimation

Code and data repository for simulations, cutoff calibration, smeariness experiments, and real-data analyses accompanying the paper on robust M-estimation on Riemannian manifolds.

This repository is organized by the paper's main experimental/theoretical components:

- `relative_efficiency` -> Sections 4.1, 4.2, 4.3
- `cutoff_selection` -> Section 5
- `smeary_circle` -> Section 3 (theoretical part) and 4.4 (simulation part)
- `realdata_analysis` -> Section 6 (Sections 6.1-6.4)

---

## Repository Structure

```text
R2M-estimation/
├─ relative_efficiency/
├─ cutoff_selection/
├─ smeary_circle/
├─ realdata_analysis/
└─ README.md
```

---

## 1. `relative_efficiency` (Sections 4.1, 4.2, 4.3)

This directory contains code/data for the simulation design and empirical relative efficiency (RE) results of robust M-estimators on Riemannian manifolds (sphere, Euclidean, hyperbolic).

### Contents

#### Simulation notebooks
- `simul_covariance_sphere.ipynb`  
  Simulation on spherical manifolds

- `simul_covariance_euclidean_samecov.ipynb`  
  Simulation on Euclidean manifolds using matched covariance settings

- `simul_covariance_hyperbolic_samecov.ipynb`  
  Simulation on hyperbolic manifolds using matched covariance settings

#### Aggregation / plotting notebook
- `simul_validation_plotting.ipynb`  
  Generates summary CSV files and plots from simulation outputs

#### Outputs
- `result_RE_varofmeans.csv`  
  Main simulation result data (relative efficiency / variance summaries)

- `plots_for_submit/`  
  Plot files used for visualization / manuscript submission figures

### Paper mapping
- Section 4.1: simulation setup / design
- Section 4.2: Gaussian setting results
- Section 4.3: heavy-tailed setting results

---

## 2. `cutoff_selection` (Section 5)

This directory contains code for cutoff calibration and practical cutoff selection, built from the relative-efficiency results produced in `relative_efficiency`.

### Contents

#### Main notebook
- `simul_regression.ipynb`  
  Includes:
  - generation of regression-ready data from relative efficiency results
  - regression modeling for cutoff calibration
  - cutoff table generation
  - rank-wise cutoff vs. RE chart generation

#### Data / outputs
- `regression_cutoff_agg/`  
  Aggregated data for regression / cutoff calibration

- `plots/`  
  Cutoff-related plots (cutoff vs. RE charts, etc.)

### Paper mapping
- Section 5: cutoff selection procedure and results

---

## 3. `smeary_circle` (Section 3 theoretical part + Section 4.4 simulation part)

This directory contains the circle (`S^1`) smeariness experiment code and outputs, including simulation and plotting.

### Contents

#### Main notebook
- `smeary_circle.ipynb`  
  Runs smeariness-related simulations and plotting

#### Data / outputs
- `core_estimator/`  
  Simulation result data for the smeariness experiments

- `plots/`  
  Figures generated from the smeariness simulations

### Paper mapping
- Section 3 (theoretical part): theoretical motivation / smeariness-related discussion
- Section 4.4 (simulation part): simulation procedure and results for the circle smeariness study

---

## 4. `realdata_analysis` (Section 6)

This directory contains the code/data for real-data analyses corresponding to Section 6 of the paper.

### Organization
The folder is organized into subfolders corresponding to Sections 6.1-6.4, and each subfolder contains the relevant:
- dataset(s)
- analysis notebook(s)
- plotting/chart notebook(s) or output figures

### Paper mapping
- Section 6.1-6.4: real-data analysis procedures and results

---

## Reproducibility Workflow (Recommended)

To reproduce the main results in order:

1. Run relative efficiency simulations
   - `relative_efficiency/simul_covariance_sphere.ipynb`
   - `relative_efficiency/simul_covariance_euclidean_samecov.ipynb`
   - `relative_efficiency/simul_covariance_hyperbolic_samecov.ipynb`

2. Aggregate simulation outputs and generate RE plots
   - `relative_efficiency/simul_validation_plotting.ipynb`

3. Run cutoff calibration / regression and generate cutoff tables & plots
   - `cutoff_selection/simul_regression.ipynb`

4. Run the `S^1` smeariness experiment
   - `smeary_circle/smeary_circle.ipynb`

5. Run real-data analyses
   - notebooks inside `realdata_analysis/` (Sections 6.1-6.4)

---

## Notes

- The repository is structured by paper section / analysis goal, not only by estimator type.
- Plot folders such as `plots/` and `plots_for_submit/` contain manuscript-ready visual outputs.
- Intermediate CSVs and aggregated regression inputs are included for reproducibility.

---

## Citation

(Review ongoing) If you use this repository, please cite the associated paper (update with final publication details when available).
