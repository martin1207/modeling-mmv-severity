# Modeling the Injury Severity of Micro-Mobility Vehicle Riders 🛴🚲💥

This repository contains the code, data processing scripts, and materials related to the article:

**"Modeling the Injury Severity of Micro-Mobility Vehicle Riders in Paris and Lyon"**  
by Martin De Jaeghere and Silvia Varotto, 2025.


---

## How to use the code
1. Clone this repository:
   ```bash
   git clone https://github.com/martin1207/modeling-mmv-severity.git
   cd modeling-mmv-severity

2. Create and activate a virtual environment (recommended):
   ```bash
    python -m venv venv
    source venv/bin/activate   # on Linux/Mac
    venv\Scripts\activate      # on Windows


3. Install dependencies:
    ```bash
    pip install -r requirements.txt



---
## Repository Structure

📁 (Estimation_results)

- [tests](tests.ipynb) # desc stats and testing
- [requirements](requirements.txt)
- [README.md](README.md)


---
## Data explanation


The related dataset ([https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2023/#/resources](https://www.data.gouv.fr/fr/datasets/bases-de-donnees-annuelles-des-accidents-corporels-de-la-circulation-routiere-annees-de-2005-a-2023/#/resources)) contains detailed information on traffic accidents (when, where, and under what conditions crashes occur), plus details on vehicles and people involved. 

![](docs/table_mapping.png)

The field explanation (English version) can be found in this file: [metadata](docs/accidents_metadata_en.md). (Original French version can be found in this [pdf](https://www.onisr.securite-routiere.gouv.fr/sites/default/files/2024-10/Description%20des%20bases%20de%20donn%C3%A9es%20annuelles.pdf))
