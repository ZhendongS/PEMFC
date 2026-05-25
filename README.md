# Data Description

This directory contains the real-world electrochemical ageing datasets used in the study.  
The data cover two broad device families:

- `Fuelcell/`: real proton exchange membrane fuel cell durability data
- `Battery/`: real battery ageing data from multiple cathode chemistries

Following the terminology used in the manuscript, the full real dataset spans:

- fuel cells
- NCA lithium-ion batteries
- NMC532 lithium-ion batteries
- NMC622/NCA-related lithium-ion batteries
- NMC811 lithium-ion batteries
- LFP lithium-ion batteries
- sodium-ion batteries

## Directory Layout

```text
realdata/
├─ Fuelcell/
│  ├─ FC_1.csv
│  ├─ FC_1_std.csv
│  ├─ FC_2.csv
│  ├─ FC_2_std.csv
│  ├─ FC_3.csv
│  ├─ FC_3_std.csv
│  ├─ FC_4.csv
│  └─ FC_4_std.csv
└─ Battery/
   ├─ TJU_NCA/
   ├─ TJU_NMC622_NCA/
   ├─ TJU_NMC811/
   ├─ USTC_LFP/
   ├─ USTC_sodium/
   └─ XJTU_NMC532/
```

## Fuelcell

The `Fuelcell/` folder contains four long-term fuel cell durability tests:

- `FC_1`
- `FC_2`
- `FC_3`
- `FC_4`

For each stack, two file types are provided:

- `FC_i.csv`: original measurement records
- `FC_i_std.csv`: harmonized data tables with unified variables and ageing labels

### Original fuel cell files

The original files contain operational measurements collected during long-duration degradation tests.  
Depending on the stack, the raw variables include:

- time
- cell voltage
- current density and current
- inlet and outlet temperatures
- hydrogen-side and air-side pressures
- auxiliary flow-related measurements

These files preserve the source-dependent measurement format and naming style.

### Harmonized fuel cell files

The `*_std.csv` files provide a consistent representation of the fuel cell data.  
Typical columns include:

- `time`: operating time
- `V`: voltage
- `I`: current density
- `T`: temperature
- `p_H2`: hydrogen partial pressure
- `p_air`: air-side pressure
- `RUL`: remaining useful life
- `SOH`: state of health
- `R_hat`, `i0_hat`, `iL_hat`: physically meaningful ageing-related parameters
- `V_phy_mean`, `V_phy_std`: physics-related voltage descriptors

These harmonized files are the cleanest form of the fuel cell ageing trajectories in this directory.

## Battery

The `Battery/` folder contains compact feature-based ageing trajectories for multiple battery chemistries.  
Each CSV file corresponds to one individual cell and records the evolution of health-related features over time or cycling.

The common filename pattern is:

- `*_features_compact.csv`

This indicates that the files are compact, feature-level representations rather than raw charge/discharge waveform archives.

### Common battery columns

Across the battery folders, the typical variables include:

- `time`: cycle index or sequence step
- `CC_std`: feature derived from the constant-current stage
- `CC_skewness`: skewness-related feature from the constant-current stage
- `CC_mean`: mean feature from the constant-current stage
- `CV_skewness`: skewness-related feature from the constant-voltage stage
- `I_ch`: charging-current-related feature
- `T`: temperature
- `RUL`: remaining useful life
- `SOH`: state of health
- `q_max`: capacity-related descriptor
- `R0`: ohmic resistance-related descriptor
- `D`: diffusion-related descriptor

Together, these variables describe the ageing trajectory of each cell in a compact multivariate form.

## Battery Subfolders

### `Battery/TJU_NCA/`

- Source: Tianjin University (TJU)
- Chemistry: NCA lithium-ion batteries
- Number of files: 38
- Representative naming style:
  - `CY25-1_1-#1_features_compact.csv`
  - `CY25-05_1-#10_features_compact.csv`
  - `CY35-05_1-#1_features_compact.csv`

This folder contains real ageing trajectories of NCA cells measured under multiple operating conditions.

### `Battery/XJTU_NMC532/`

- Source: Xi'an Jiaotong University (XJTU)
- Chemistry: NMC532 lithium-ion batteries
- Number of files: 8
- Representative naming style:
  - `XJTU_B1_2C_01_features_compact.csv`
  - `XJTU_B1_2C_08_features_compact.csv`

This folder provides real degradation data for ternary lithium-ion cells with NMC532 cathode chemistry.

### `Battery/USTC_LFP/`

- Source: University of Science and Technology of China (USTC)
- Chemistry: LFP lithium-ion batteries
- Number of files: 7
- Representative naming style:
  - `USTC_25_1C_01_features_compact.csv`
  - `USTC_25_2C_01_features_compact.csv`
  - `USTC_25_0.5C_01_features_compact.csv`

This folder contains lithium iron phosphate battery ageing trajectories under several charge/discharge rates.

### `Battery/USTC_sodium/`

- Source: University of Science and Technology of China (USTC)
- Chemistry: sodium-ion batteries
- Number of files: 3
- Files:
  - `USTC_sodium_b1_features_compact.csv`
  - `USTC_sodium_b2_features_compact.csv`
  - `USTC_sodium_b3_features_compact.csv`

This folder contains the sodium-ion battery ageing data used in the study.

### `Battery/TJU_NMC811/`

- Source: Tianjin University (TJU)
- Chemistry: NMC811 lithium-ion batteries
- Number of files: 55
- Representative naming style:
  - `CY45-05_1-#1_features_compact.csv`
  - `CY35-05_1-#1_features_compact.csv`
  - `CY25-05_1-#1_features_compact.csv`

This is the largest battery subset in the directory and covers multiple temperature conditions.

### `Battery/TJU_NMC622_NCA/`

- Source: Tianjin University (TJU)
- Chemistry label: NMC622/NCA-related subset
- Number of files: 6
- Representative naming style:
  - `CY25-05_1-#1_features_compact.csv`
  - `CY25-05_2-#3_features_compact.csv`

This folder contains a smaller mixed-chemistry subset associated with NMC622 and NCA naming.

## Naming Conventions

### Fuel cell files

- `FC_i.csv`: original fuel cell measurements
- `FC_i_std.csv`: harmonized fuel cell ageing tables

### Battery files

- `*_features_compact.csv`: compact feature-based ageing trajectories for individual cells

## Summary

In manuscript terms, this directory contains real ageing trajectories from:

- four fuel cell stacks
- 38 NCA cells
- 8 NMC532 cells
- 6 NMC622/NCA-related cells
- 55 NMC811 cells
- 7 LFP cells
- 3 sodium-ion cells

These datasets jointly form a heterogeneous real-data collection for cross-chemistry degradation analysis, covering both fuel cells and multiple battery chemistries.
