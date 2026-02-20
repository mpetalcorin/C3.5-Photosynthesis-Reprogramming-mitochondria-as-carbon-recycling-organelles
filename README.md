# C3.5-Photosynthesis-Reprogramming-mitochondria-as-carbon-recycling-organelles
This repository contains code, simulated datasets, and analyses exploring the feasibility of C3.5 photosynthesis: a synthetic biology strategy that repurposes mitochondria as carbon-recycling organelles.   

# Abstract

Global food demand is projected to increase by more than 50 percent by 2050, yet I recognize that most staple crops still rely on inefficient C3 photosynthesis. A major limitation comes from Rubisco, the central carbon-fixing enzyme, which often catalyzes oxygenation reactions that waste up to 40 percent of fixed carbon through photorespiration. While C4 photosynthesis offers greater efficiency, I have seen how its anatomical and regulatory complexity has hindered successful transfer into C3 crops. To address this, I propose and evaluate a novel intermediate strategy that I call C3.5 photosynthesis, which reimagines mitochondria as carbon-recycling organelles to enhance Rubisco efficiency. Using *Arabidopsis* as my model, I integrate computational modeling, simulated phenotyping datasets, and machine learning approaches to benchmark the feasibility of coupling mitochondrial bioenergetics with chloroplast carbon assimilation. I construct predictive frameworks that show how mitochondrial CO₂ release can be recaptured and redirected to chloroplasts through engineered organelle tethers and synthetic transporters. I then simulate the redox and energetic trade-offs of rewiring FoF₁ ATP synthase to power bicarbonate transport, providing mechanistic insights into balancing ATP costs against carbon gains. The results demonstrate that C3.5 photosynthesis could increase net carbon assimilation by 20–50 percent under fluctuating light and heat stress, without requiring the structural reprogramming needed for C4 pathways. This work lays the conceptual and computational foundation for repurposing mitochondria as carbon-recycling hubs, bridging fundamental organelle biology with translational strategies in crop engineering. By combining expertise in bioenergetics, organelle engineering, and AI-driven modeling, I believe C3.5 photosynthesis represents a high-risk, high-reward pathway to deliver climate-resilient agriculture and secure future food systems.

# Introduction

The global challenge of food security has intensified as climate change and population growth converge to place unprecedented demands on agriculture. By 2050, world food demand is expected to rise by more than 50 percent, yet crop productivity gains are stagnating (Gerber et al., 2024). Most of the world’s staple crops, including rice, wheat, and soybean, rely on C3 photosynthesis, a pathway limited by the inefficiency of the enzyme ribulose-1,5-bisphosphate carboxylase/oxygenase (Rubisco). Rubisco catalyzes both the carboxylation of ribulose-1,5-bisphosphate and the competing oxygenation reaction that initiates photorespiration, a wasteful process that can reduce net carbon assimilation by up to 40 percent under stress conditions such as heat and drought (Namachivayam et al., 2025; Iqbal et al., 2021).

C4 photosynthesis, as found in maize and sorghum, provides a natural design solution by concentrating CO₂ around Rubisco through specialized leaf anatomy and biochemical pathways. However, despite decades of effort, transferring C4 traits into C3 crops has proven extremely difficult because of the requirement for coordinated changes in cell-specific gene expression, leaf structure, and metabolite transport (Schuler et al., 2020). Synthetic biology approaches have attempted to bypass these challenges, for example by introducing cyanobacterial carboxysomes into chloroplasts (Lin et al., 2014) or by engineering photorespiratory bypasses (South et al., 2019). While promising, these strategies remain partial solutions and highlight the need for novel paradigms in photosynthetic engineering.

One such paradigm is the concept of C3.5 photosynthesis, which reimagines mitochondria not as secondary energy factories but as carbon-recycling organelles. During respiration, mitochondria release CO₂ as a byproduct of the tricarboxylic acid (TCA) cycle and generate water through the activity of the electron transport chain. This CO₂ is normally lost to diffusion but represents a potentially valuable source of substrate for Rubisco. Redirecting mitochondrial CO₂ into chloroplasts could increase Rubisco carboxylation efficiency and mitigate oxygenation, especially under fluctuating environments where photorespiration is most detrimental (Busch, 2020).

Recent advances make this concept increasingly feasible. Organelle tethering proteins have been shown to mediate direct metabolite exchange between plastids and mitochondria (Michaud et al., 2017). Synthetic biology has expanded the toolkit for engineering protein compartments that can concentrate metabolites, including efforts to reconstitute carboxysome-like structures in eukaryotic systems (Nguyen et al., 2024). Furthermore, FoF₁ ATP synthase, the rotary machine of oxidative phosphorylation, can theoretically be rewired to power transporters that pump bicarbonate or CO₂ equivalents, creating a direct bioenergetic coupling between mitochondrial proton motive force and chloroplast carbon assimilation (Hou & Wang, 2021).

Here, I present a conceptual and computational framework for C3.5 photosynthesis, using *Arabidopsis* as a model. By combining high-resolution phenotyping, physics-informed neural networks, and Bayesian energy-balance models, I evaluate how mitochondria could be repurposed as carbon-recycling organelles that enhance Rubisco efficiency and plant resilience. This approach bridges organelle biology with machine learning-driven design principles, offering a high-risk, high-reward pathway to climate-resilient agriculture.

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
**Petalcorin, M. I. R.** (2025). Engineering C3.5 Photosynthesis: Coupling Mitochondrial Bioenergetics to Rubisco Efficiency in Arabidopsis. bioRxiv. https://www.biorxiv.org/cgi/content/short/2025.10.04.680431v1

## Conclusion and Future Directions

This study introduces C3.5 photosynthesis as a transformative framework for crop engineering, built on the idea of repurposing mitochondria as carbon-recycling organelles. By coupling mitochondrial CO₂ release and bioenergetics with chloroplast carbon assimilation, we provide computational and simulated evidence that assimilation rates, Rubisco efficiency, and water-use efficiency can be improved by 20-50 percent in Arabidopsis. These improvements parallel or exceed those achieved by recent photorespiratory bypass strategies (South et al., 2019), while offering a fundamentally different path, one that leverages existing mitochondrial processes rather than requiring anatomical restructuring akin to C4 photosynthesis.

Looking forward, the next five years present a unique opportunity to test and translate this framework. Stage 1 focuses on synthetic biology of mitochondrial compartments, building carboxysome-like structures within mitochondria to trap CO₂. Stage 2 establishes organelle tethers and metabolite channels to direct CO₂ flux to chloroplasts. Stage 3 pursues bioenergetic coupling, rewiring FoF₁ ATP synthase to power bicarbonate transporters while balancing ATP costs. Stage 4 validates performance in Arabidopsis through phenotyping and molecular assays. Stage 5 scales this design into staple crops such as rice and wheat under controlled and semi-field environments.

The implications extend beyond agriculture. By reconceptualizing mitochondria as synthetic carbon pumps, this approach opens a new frontier in organelle engineering. It also provides a broader paradigm for synthetic biology: cross-organelle reprogramming that integrates chloroplasts, mitochondria, and even peroxisomes into unified networks. Such designs may not only enhance crop resilience but also contribute to planetary sustainability by reducing fertilizer inputs, improving water-use efficiency, and enabling decarbonised plant-based production systems.

If successful, C3.5 photosynthesis could represent a paradigm shift of novel significance. It would establish an entirely new photosynthetic pathway, expand the synthetic biology toolkit into mitochondria, and deliver real-world solutions to one of humanity’s greatest challenges, feeding a growing population under climate change. By anchoring this vision in testable, stage-gated experiments, the path from concept to field deployment becomes both scientifically feasible and societally urgent.

References

1.	Busch, F. A. (2020). Photorespiration in the context of Rubisco biochemistry, CO₂ diffusion, and metabolism. The Plant Journal, 101(4), 919–939. https://doi.org/10.1111/tpj.14674
2.	Carmo-Silva, E., Scales, J. C., Madgwick, P. J., & Parry, M. A. J. (2015). Optimizing Rubisco and its regulation for greater resource use efficiency. Plant, Cell & Environment, 38(9), 1817–1832. https://doi.org/10.1111/pce.12425
3.	Gerber, J.S., Ray, D.K., Makowski, D. et al. (2024) Global spatially explicit yield gap time trends reveal regions at risk of future crop yield stagnation. Nat Food 5, 125–135. https://doi.org/10.1038/s43016-023-00913-8
4.	Hennacy, J. H., & Jonikas, M. C. (2020). Prospects for engineering biophysical CO₂ concentrating mechanisms into land plants to enhance yields. Annual Review of Plant Biology, 71(1), 461–485. https://doi.org/10.1146/annurev-arplant-081519-035910
5.	Hou R, Wang Z. (2021). Thermodynamic marking of FOF1 ATP synthase. Biochim Biophys Acta Bioenerg., 1862(4):148369. https://doi.org/10.1016/j.bbabio.2021.148369
6.	Iqbal, W. A., Miller, I. G., Moore, R. L.,  Hope, I. J., Cowan-Turner, D., Kapralov, M. V. (2021) Rubisco substitutions predicted to enhance crop performance through carbon uptake modelling, Journal of Experimental Botany, 72(17)6066–6075, https://doi.org/10.1093/jxb/erab278
7.	Kromdijk, J., Głowacka, K., Leonelli, L., Gabilly, S. T., Iwai, M., Niyogi, K. K., & Long, S. P. (2016). Improving photosynthesis and crop productivity by accelerating recovery from photoprotection. Science, 354(6314), 857–861. https://doi.org/10.1126/science.aai8878
8.	Lawson, T., & Matthews, J. (2020). Guard cell metabolism and stomatal function. Annual Review of Plant Biology, 71(1), 273–302. https://doi.org/10.1146/annurev-arplant-050718-100251
9.	Lawson T, Vialet-Chabrand S. (2019). Speedy stomata, photosynthesis and plant water use efficiency. New Phytol., 221(1):93-98. https://doi.org/10.1111/nph.15330
10.	Lin, M. T., Occhialini, A., Andralojc, P. J., Parry, M. A. J., & Hanson, M. R. (2014). A faster Rubisco with potential to increase photosynthesis in crops. Nature, 513(7519), 547–550. https://doi.org/10.1038/nature13776
11.	Michaud, M., Jouhet, J., & Maréchal, E. (2017). Lipid trafficking at membrane contact sites during plant development and stress response. Frontiers in Plant Science, 8, 1920. https://doi.org/10.3389/fpls.2019.00002
12.	Namachivayam, R., Manickam, G.P., Eswaran, K. et al. (2025). Strategies to improve photosynthesis by modifying the RuBisCO system and its limitations. Mol Biol Rep., 52, 951. https://doi.org/10.1007/s11033-025-11075-0
13.	Nguyen ND, Pulsford SB, Förster B, Rottet S, Rourke L, Long BM, Price GD. (2024) A carboxysome-based CO2 concentrating mechanism for C3 crop chloroplasts: advances and the road ahead. Plant J.,118(4):940-952. https://doi.org/10.1111/tpj.16667
14.	Schuler ML, Mantegazza O, Weber AP. (2016) Engineering C4 photosynthesis into C3 chassis in the synthetic biology age. Plant J. 87(1):51-65. https://doi.org/10.1111/tpj.13155
15.	South, P. F., Cavanagh, A. P., Liu, H. W., & Ort, D. R. (2019). Synthetic glycolate metabolism pathways stimulate crop growth and productivity in the field. Science, 363(6422), eaat9077. https://doi.org/10.1126/science.aat9077
16.	Walker, B. J., VanLoocke, A., Bernacchi, C. J., & Ort, D. R. (2016). The costs of photorespiration to food production now and in the future. Annual Review of Plant Biology, 67(1), 107–129. https://doi.org/10.1146/annurev-arplant-043015-111709
17.	Xu, C., Liu, Q., & Huang, X. (2022). Machine learning-assisted synthetic biology. Nature Communications, 13(1), 3607. https://doi.org/10.1038/s41467-022-31244-4
18.	Yin, X., & Struik, P. C. (2018). The energy budget in C₃ photosynthesis: Insights from combined quantum yield and metabolic flux analysis. New Phytologist, 218(3), 986-998. https://doi.org/10.1111/nph.15051
