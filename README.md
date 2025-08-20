# Modeling the Injury Severity of Micro-Mobility Vehicle Riders

This repository contains the code, data processing scripts, and materials related to the article:

**"Modeling the Injury Severity of Micro-Mobility Vehicle Riders in Paris and Lyon"**  
by Martin Dejaeghere, 2025.

---

## 📖 Project Overview
The study investigates the determinants of crash injury severity for riders of micro-mobility vehicles (MMVs), such as **e-scooters** and **e-bikes**, in two major French cities: **Paris** and **Lyon**.  
It combines **police crash data**, **GIS information**, and **advanced econometric models** to identify factors influencing the severity of injuries.

---

## 🗂 Repository Structure
├── data/ # Raw and processed datasets (restricted, anonymized if necessary)
├── notebooks/ # Jupyter notebooks with exploratory analysis and model estimation
├── scripts/ # Python scripts for data cleaning, feature engineering, and modeling
├── figures/ # Generated figures and tables for the paper
├── tables/ # LaTeX output tables for the manuscript
└── README.md # Project documentation


---

## ⚙️ Methods
- **Data Sources**: Police-reported crashes (Paris & Lyon), geospatial data (road infrastructure, traffic environment).  
- **Models**:  
  - Random Parameters Logit (Mixed Logit)  
  - Ordered Probit  
  - Robustness checks and out-of-sample validation  
- **Software**: Python (pandas, statsmodels, scikit-learn, geopandas), LaTeX.

---

## 📊 Key Contributions
- First comparative study of injury severity for MMVs in two French metropolitan areas.  
- Incorporation of **infrastructure and spatial variables** alongside crash-level factors.  
- Evidence-based insights for **urban safety policies** and **infrastructure design**.

---

## 🚀 Getting Started
1. Clone this repository:
   ```bash
   git clone https://github.com/martin1207/Modeling_Injury_Severity.git
   cd Modeling_Injury_Severity
