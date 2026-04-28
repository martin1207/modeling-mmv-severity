# Modeling the Injury Severity of Micro-Mobility Vehicle Riders

This repository contains the code related to the pre-print:

**"Modeling the injury severity of riders and pedestrians in micro-mobility vehicle crashes"**
by Martin De Jaeghere and Silvia Varotto, 2025.

The repository allows you to reproduce the results of the study, adapt the analysis to other vehicles or cities, integrate newly released crash data, and refine model configurations.

---

## Requirements

- **Python 3.13** or higher (the analysis was developed and tested with Python 3.13.2). Earlier versions are not supported because some pinned dependencies (`numpy==2.2.4`, `pandas==2.2.3`) require Python 3.10+, and several typing/syntax features used by the notebooks rely on Python 3.13.
- The full list of Python packages is in [requirements.txt](requirements.txt).

## How to use the code

1. Clone this repository:
   ```bash
   git clone https://github.com/martin1207/modeling-mmv-severity.git
   cd modeling-mmv-severity
   ```

2. Create and activate a virtual environment with Python 3.13 (recommended):
   ```bash
   python3.13 -m venv mmv_severity_env
   source mmv_severity_env/bin/activate     # on Linux/Mac
   mmv_severity_env\Scripts\activate        # on Windows
   ```

3. Install dependencies:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. Register the environment as a Jupyter kernel and launch Jupyter:
   ```bash
   python -m ipykernel install --user --name mmv_severity_env --display-name "Python (mmv_severity)"
   jupyter notebook
   ```

---

## Repository Structure

The notebooks are designed to be run in the following order. Each one produces files that the next one consumes, so do not skip steps.

1. [Data loading, wrangling and cleaning](loading_and_cleaning_data.ipynb)
   Downloads the raw French national crash database, merges the four sub-tables (characteristics, vehicles, places, users), restricts the data to the Paris and Lyon metropolitan areas, joins road-network attributes from OpenStreetMap, and writes the cleaned dataset to `final_processed_crash_dataset.csv`.

2. [Descriptive statistics and bivariate tests](desc_stats_and_bivariate_test.ipynb)
   Reads `final_processed_crash_dataset.csv`, produces summary statistics and bivariate tests (Chi-square, ANOVA, Kruskal-Wallis), and writes the result table to `descriptive_statistics_and_bivariate_tests.csv`.

3. [Model development](modeling_development.ipynb)
   Reads `final_processed_crash_dataset.csv`, estimates the discrete-choice models (logit, ordered probit/logit, mixed logit) with [Biogeme](https://biogeme.epfl.ch/), runs the likelihood-ratio tests, and performs out-of-sample validation.

Other files:
- [requirements.txt](requirements.txt) — required Python packages
- [biogeme.toml](biogeme.toml) — Biogeme configuration (number of draws, optimization algorithm, etc.)
- [docs/](docs) — supporting documentation, including the field metadata

---

## Data explanation

The dataset is the French national road-accident database (BAAC), available from data.gouv.fr:
<https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2023/>

It contains detailed information on traffic accidents (when, where, and under what conditions crashes occur), plus details on vehicles and people involved.

![](docs/table_mapping.png)

The field explanation (English version) is available in [docs/accidents_metadata_en.md](docs/accidents_metadata_en.md). The original French version is the official ONISR PDF: <https://www.onisr.securite-routiere.gouv.fr/sites/default/files/2024-10/Description%20des%20bases%20de%20donn%C3%A9es%20annuelles.pdf>
