# Description
MATLAB code for Bland-Altman analysis of proportional bias between IKD- and 
ID-measured ankle torques, including mixed-effects modelling to account for 
within-trial clustering. Developed during my research work at the HUS Motion 
Laboratory, New Children's Hospital, Helsinki.

---

## Repository Contents

- `Bland_Altman_Analysis.mlx` — MATLAB Live Script for agreement analysis:
  - Bland-Altman plots (mean vs. difference) across all trials and by condition
  - Proportional bias testing via linear regression (Diff ~ Mean)
  - Mixed-effects modelling to account for within-trial clustering
  - Peak-based accuracy metrics: MAPE, RMSE, and CV
- `Bland_Altman_Analysis.html` — Rendered output (code, results, plots)

## Analysis Overview

For each trial (or group of trials, by experimental condition), the script:
1. Loads the corresponding IKD and ID torque signals and time-aligns them
2. Identifies peak torques in both signals using condition-specific peak 
   detection parameters
3. Computes Bland-Altman mean and difference values, plotting bias and 
   limits of agreement (±1.96 SD)
4. Tests for proportional bias via linear regression of the differences 
   against the mean torque values
5. Fits a mixed-effects model (random intercept by trial) to account for 
   within-trial clustering when combining multiple trials
6. Reports peak-based accuracy metrics (MAPE, RMSE, CV) alongside the 
   Bland-Altman statistics

## How to Run

1. Download or clone this repository.
2. Open `Bland_Altman_Analysis.mlx` in MATLAB.
3. Load the required workspace files:
   - `IKD_Torque_Data.mat` — dynamometer (IKD) torque values
   - `Force_LeverArm_Trials1-4.mat` — force and lever-arm data for trials 1–4
   - `Force_LeverArm_Trials5-8.mat` — force and lever-arm data for trials 5–8
4. Run the script section by section (organized by trial/condition, followed 
   by a combined subplot summary across all four conditions).

Alternatively, open `Bland_Altman_Analysis.html` to view the rendered output 
without running MATLAB.
