# C3.5-Photosynthesis-Reprogramming-mitochondria-as-carbon-recycling-organelles
This repository contains code, simulated datasets, and analyses exploring the feasibility of C3.5 photosynthesis: a synthetic biology strategy that repurposes mitochondria as carbon-recycling organelles.   

# C3.5 Photosynthesis Simulation and Analysis  
**Reprogramming mitochondria as carbon-recycling organelles to enhance Rubisco efficiency in Arabidopsis**

## Overview  
This repository contains code, simulated datasets, and analyses exploring the feasibility of **C3.5 photosynthesis**: a synthetic biology strategy that repurposes mitochondria as carbon-recycling organelles.  
By coupling mitochondrial bioenergetics to Rubisco activation, we demonstrate potential gains of **20–35% in assimilation and water-use efficiency (WUE)**, benchmarked against publicly available *Arabidopsis thaliana* datasets.  

The repository includes: 
- Simulation framework for wild type vs engineered cohorts. 
- Data preprocessing and benchmarking with *Arabidopsis* public datasets  
- Machine learning analysis, including feature importance, PCA, and SHAP interpretability. 
- Figures (Figures 1–10). 
- Supporting documents (Datasheet, Model Card).  

## Repository Structure  

<img width="571" height="221" alt="Screenshot 2025-10-04 at 06 21 26" src="https://github.com/user-attachments/assets/949a0270-aa4b-43a3-870a-b867a154bd26" />

# Datasheet for the C3.5 Photosynthesis Simulation Dataset  

## Motivation  
The dataset was generated to evaluate the feasibility of **repurposing mitochondria as carbon-recycling organelles** in *Arabidopsis thaliana*.  
By simulating wild type and engineered cohorts, we tested whether bioenergetic reprogramming improves Rubisco activation, assimilation, and WUE.

## Composition  
- **Entities:** 2 plant types (wild type, engineered).  
- **Samples:** 1,000 per type (2,000 total).  
- **Variables:**  
  - Environmental: light intensity, temperature, vapor pressure deficit (VPD), soil nitrogen.  
  - Bioenergetic: ATP/ADP ratio, proton motive force (pmf).  
  - Physiological: Rubisco activation (%), assimilation (µmol CO₂ m⁻² s⁻¹), WUE (µmol CO₂ per mmol H₂O).  

## Collection Process  
- Simulation framework written in Python, calibrated to benchmark values from *Arabidopsis thaliana* public datasets (TAIR, AtGenExpress, and literature).  
- Physiological ranges validated against peer-reviewed experimental studies (Busch, 2020; Cavanagh et al., 2022).  

## Preprocessing  
- Standardized ranges (e.g., light: 50–1,500 µmol m⁻² s⁻¹).  
- Noise introduced to mimic biological variation.  
- Outliers retained if physiologically plausible.  

## Uses  
- Testbed for **machine learning models** predicting assimilation.  
- Benchmark for **explainable AI approaches** in photosynthesis research.  
- Educational resource for plant bioenergetics and synthetic biology.  

## Limitations  
- Simulated rather than measured data.  
- Models do not yet incorporate whole-plant growth, nitrogen budgets, or sink-source dynamics.  
- Environmental fluctuations simplified to steady states.  

## Maintenance  
Maintained by **Mark Ihrwell R. Petalcorin (m.petalcorin@gmail.com)**.  
Updates will include:  
- Integration of transcriptomic features.  
- Crop-level scaling (rice, wheat).

# Model Card: C3.5 Photosynthesis Assimilation Predictor  

## Model Details  
- **Developers:** Mark Ihrwell R. Petalcorin and collaborators.  
- **Framework:** Python (scikit-learn, SHAP).  
- **Type:** Ensemble regression models (Random Forest, Gradient Boosted Trees).  
- **Purpose:** Predict photosynthetic assimilation rates from environmental and bioenergetic variables.  

## Intended Use  
- **Primary:** Evaluate the impact of engineered mitochondrial CO₂ recycling on assimilation and WUE.  
- **Secondary:** Educational demonstrations of interpretable ML in plant systems.  
- **Not for:** Direct field management or crop breeding recommendations (simulation-based).  

## Inputs  
- Light intensity (µmol m⁻² s⁻¹)  
- Temperature (°C)  
- VPD (kPa)  
- Soil nitrogen (arbitrary units)  
- ATP/ADP ratio  
- pmf (dimensionless)  
- Rubisco activation (%)  

## Outputs  
- Assimilation (µmol CO₂ m⁻² s⁻¹).  
- Feature importance scores.  
- SHAP explanations and partial dependence plots.  

## Performance  
- R² (cross-validation): ~0.89  
- MAE: ~1.2 µmol CO₂ m⁻² s⁻¹  
- Dominant predictors: **Rubisco activation (≈65%)**, **ATP/ADP ratio (≈20%)**.  

## Ethical Considerations  
- Simulated dataset, not actual field measurements.  
- Model outputs are **hypothesis-generating** rather than decision-making.  
- Future integration with crop models must account for ecological, agronomic, and socioeconomic impacts.  

## Limitations  
- Current models benchmarked on *Arabidopsis* only.  
- Environmental complexity underrepresented (e.g., fluctuating light).  
- No explicit modeling of trade-offs between carbon gain and nitrogen cost.  

## Future Directions  
- Extend to multi-species simulations (rice, wheat, maize).  
- Incorporate transcriptomics and fluxomics datasets.  
- Test modular integration with **synthetic organelle engineering designs**.

## Citation

If you use this repository, please cite:\
***Petalcorin, M. I. R.*** *(2025). Engineering C3.5 Photosynthesis: Coupling Mitochondrial Bioenergetics to Rubisco Efficiency in Arabidopsis. GitHub*
