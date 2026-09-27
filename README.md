# Bounded State Updating

Reproducibility materials for the paper

**Bounded State Updating under Extreme Macroeconomic Releases and Data Revisions**

This repository contains the empirical reproduction materials for the real-time macroeconomic, controlled-experiment, M3, fitting-depth, revision-sensitivity, and external-benchmark analyses reported in the manuscript and Supplementary Information.

The package is split into four ZIP archives for convenient repository distribution. Extract **all four archives into the same parent directory**. They share the common top-level folder:

```text
Bounded_State_Updating_complete_reproducibility/
```

and together reconstruct the complete reproducibility package.

## Download files

1. `Bounded_State_Updating_repro_01_core_rtdsm_external_controlled.zip`  
   Core reproduction materials, including the July 1983--June 2025 long-sample RTDSM extension, frozen 2018--2025 RTDSM validation materials, internal-method code, controlled experiments, fitting-depth code, external benchmark materials, and table/figure source data.

2. `Bounded_State_Updating_repro_02_M3_analysis.zip`  
   Complete M3 analysis code and supporting outputs, including the 3,003-series contamination/refitting analyses, Gate F records, fitted-layer decomposition, and M3 fitting-depth summaries.

3. `Bounded_State_Updating_repro_03_M3_primary_results.zip`  
   Large series-level M3 Primary results file.

4. `Bounded_State_Updating_repro_04_M3_primary_fits.zip`  
   Large series-level M3 Primary fit record.

## Reconstructing the package

Download all four ZIP files and extract them to the same location. Because each archive uses the same top-level directory, their contents will merge into one directory:

```text
Bounded_State_Updating_complete_reproducibility/
```

Do not rename or move internal subdirectories if you want to run the supplied scripts without editing paths.

## Main reproduction components

### Long-sample RTDSM extension

The balanced July 1983--June 2025 real-time macroeconomic analysis is isolated under:

```text
long_sample_rtdsm/
```

It reconstructs the PRE/REF histories, validates the overlapping January 2018--June 2025 window against the frozen earlier results, and runs Gaussian-ST, Huber-ST, MB-ST, and CB-ST. From that directory, run:

```bash
Rscript R/run_all.R
```

The long-sample numerical results should be treated as final only after the frozen-overlap validation reports a pass.

### Controlled experiments

The controlled contamination and persistent-shift experiments are under `controlled/`.

### M3 analysis

The M3 reproduction materials are under `M3/`, with supporting frozen records under `R1_R2/04_R1_M3_PRIMARY/` and `R1_R2/07_SUMMARIES/`.

### Fitting-depth experiments

The fitting-depth code and protocol are under `fitting_depth_code/`, with frozen fit/result records under `R1_R2/`.

### External benchmark reproduction

The validated RTDSM benchmark materials are under `realtime/`, `method_code/`, `external/`, and `R1_R2/05_R2_BENCHMARKS/`.

## Data and third-party code

The original Philadelphia Fed RTDSM workbooks are publicly available from the Federal Reserve Bank of Philadelphia and are **not redistributed** in this repository. The package documents the source files, transformations, vintage construction, observation support, and release mappings used in the analysis.

The public Structural Theta and AutoTheta source code of Sbrana and Silvestrini is also **not redistributed**. The required version and acquisition instructions are documented in the package.

M3 data are obtained through the documented `Mcomp` R package/environment used by the reproduction scripts.

## Software environment

The frozen reproduction records document, among other dependencies, R 4.3.3, `forecast` 8.24.0, `robets` 1.4, and `Mcomp` 2.8. Additional package versions and environment details are recorded in the supplied scripts and documentation.

## Documentation

After extracting all four archives, see `README.md`, `README_TECHNICAL_DETAIL.md`, `PROVENANCE_COMPLETE.md`, `RECOVERED_CODE_PROVENANCE.md`, and `source_data_mapping.md` for detailed reproduction instructions and provenance.
