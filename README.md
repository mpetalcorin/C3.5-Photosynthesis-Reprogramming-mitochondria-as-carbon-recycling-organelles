# C3.5-Photosynthesis-Reprogramming-mitochondria-as-carbon-recycling-organelles
This repository contains code, simulated datasets, and analyses exploring the feasibility of C3.5 photosynthesis: a synthetic biology strategy that repurposes mitochondria as carbon-recycling organelles.   

# Abstract

Global food demand is projected to increase by more than 50 percent by 2050, yet I recognize that most staple crops still rely on inefficient C3 photosynthesis. A major limitation comes from Rubisco, the central carbon-fixing enzyme, which often catalyzes oxygenation reactions that waste up to 40 percent of fixed carbon through photorespiration. While C4 photosynthesis offers greater efficiency, I have seen how its anatomical and regulatory complexity has hindered successful transfer into C3 crops. To address this, I propose and evaluate a novel intermediate strategy that I call C3.5 photosynthesis, which reimagines mitochondria as carbon-recycling organelles to enhance Rubisco efficiency. Using Arabidopsis as my model, I integrate computational modeling, simulated phenotyping datasets, and machine learning approaches to benchmark the feasibility of coupling mitochondrial bioenergetics with chloroplast carbon assimilation. I construct predictive frameworks that show how mitochondrial CO₂ release can be recaptured and redirected to chloroplasts through engineered organelle tethers and synthetic transporters. I then simulate the redox and energetic trade-offs of rewiring FoF₁ ATP synthase to power bicarbonate transport, providing mechanistic insights into balancing ATP costs against carbon gains. The results demonstrate that C3.5 photosynthesis could increase net carbon assimilation by 20–50 percent under fluctuating light and heat stress, without requiring the structural reprogramming needed for C4 pathways. This work lays the conceptual and computational foundation for repurposing mitochondria as carbon-recycling hubs, bridging fundamental organelle biology with translational strategies in crop engineering. By combining expertise in bioenergetics, organelle engineering, and AI-driven modeling, I believe C3.5 photosynthesis represents a high-risk, high-reward pathway to deliver climate-resilient agriculture and secure future food systems.

# Introduction

The global challenge of food security has intensified as climate change and population growth converge to place unprecedented demands on agriculture. By 2050, world food demand is expected to rise by more than 50 percent, yet crop productivity gains are stagnating (Gerber et al., 2024). Most of the world’s staple crops, including rice, wheat, and soybean, rely on C3 photosynthesis, a pathway limited by the inefficiency of the enzyme ribulose-1,5-bisphosphate carboxylase/oxygenase (Rubisco). Rubisco catalyzes both the carboxylation of ribulose-1,5-bisphosphate and the competing oxygenation reaction that initiates photorespiration, a wasteful process that can reduce net carbon assimilation by up to 40 percent under stress conditions such as heat and drought (Namachivayam et al., 2025; Iqbal et al., 2021).

C4 photosynthesis, as found in maize and sorghum, provides a natural design solution by concentrating CO₂ around Rubisco through specialized leaf anatomy and biochemical pathways. However, despite decades of effort, transferring C4 traits into C3 crops has proven extremely difficult because of the requirement for coordinated changes in cell-specific gene expression, leaf structure, and metabolite transport (Schuler et al., 2020). Synthetic biology approaches have attempted to bypass these challenges, for example by introducing cyanobacterial carboxysomes into chloroplasts (Lin et al., 2014) or by engineering photorespiratory bypasses (South et al., 2019). While promising, these strategies remain partial solutions and highlight the need for novel paradigms in photosynthetic engineering.

One such paradigm is the concept of C3.5 photosynthesis, which reimagines mitochondria not as secondary energy factories but as carbon-recycling organelles. During respiration, mitochondria release CO₂ as a byproduct of the tricarboxylic acid (TCA) cycle and generate water through the activity of the electron transport chain. This CO₂ is normally lost to diffusion but represents a potentially valuable source of substrate for Rubisco. Redirecting mitochondrial CO₂ into chloroplasts could increase Rubisco carboxylation efficiency and mitigate oxygenation, especially under fluctuating environments where photorespiration is most detrimental (Busch, 2020).

Recent advances make this concept increasingly feasible. Organelle tethering proteins have been shown to mediate direct metabolite exchange between plastids and mitochondria (Michaud et al., 2017). Synthetic biology has expanded the toolkit for engineering protein compartments that can concentrate metabolites, including efforts to reconstitute carboxysome-like structures in eukaryotic systems (Nguyen et al., 2024). Furthermore, FoF₁ ATP synthase, the rotary machine of oxidative phosphorylation, can theoretically be rewired to power transporters that pump bicarbonate or CO₂ equivalents, creating a direct bioenergetic coupling between mitochondrial proton motive force and chloroplast carbon assimilation (Hou & Wang, 2021).

Here, we present a conceptual and computational framework for C3.5 photosynthesis, using Arabidopsis as a model. By combining high-resolution phenotyping, physics-informed neural networks, and Bayesian energy-balance models, we evaluate how mitochondria could be repurposed as carbon-recycling organelles that enhance Rubisco efficiency and plant resilience. This approach bridges organelle biology with machine learning-driven design principles, offering a high-risk, high-reward pathway to climate-resilient agriculture.

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
