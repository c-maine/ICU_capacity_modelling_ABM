# ICU_capacity_modelling_ABM

An Agent-Based Model for Intensive Care Unit capacity modelling at the Beth Israel Deaconess Medical Center

**Final paper**

The final project is available in PDF form [here](https://github.com/c-maine/ICU_capacity_modelling_ABM/blob/master/Submitted_Thesis.pdf). 

**Data sources**

The data used in this project comes from:
- MIMIC-III, a freely accessible critical care database (Johnson AEW, Pollard TJ, Shen L, Lehman L, Feng M, Ghassemi M, Moody B, Szolovits P, Celi LA, and Mark RG. Scientific Data (2016). DOI: 10.1038/sdata.2016.35.) It is available from [here](http://www.nature.com/articles/sdata201635)

**Using this repo**

This repo contains the code needed to replicate the results of the paper. It is structured into the following sections:

- [ABM_results](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/ABM_results) contains the Agent Based Model, simulations from which the results are graphed and the final graphs themselves.

- [Admissions_dists_estimation](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/Admissions_dists_estimation) in which we calculate the parameters defining the patient admissions distributions for each patient cluster/ICU combination. 

- [Data_processing](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/Data_processing) takes raw data from multiple sources and applies pre-processing  to generate output data that is used in the agent-based model

- [LOS Prediction](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/LOS_prediction) contains the machine learning models used to capture sub- population dynamics in patient outflow


- Sepsis_prediction

**Results**

Jump straight to our results graphs in [this notebook](https://github.com/c-maine/ICU_capacity_modelling_ABM/blob/master/ABM_results/ABM_graphs_vF.ipynb).

An example graph is included below.

![alt text](https://github.com/c-maine/ICU_capacity_modelling_ABM/blob/master/peace_wh_dists.png)
