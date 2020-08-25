# Calculating parameters which define patient admissions distributions

**Aims**

In this folder we calculate the parameters which define the multinomial distribution by which patients are admitted to the hospital each day. This is a key element of stochasticity in our Agent Based model and core characteristic of each patient (agent.)

We originally intended to group patients by age and diagnosis (see old notebook below) but found this data to be too sparse, without adding signficant benefit in Length of Stay prediciton. Our final approach involved clustering patients by Length of Stay, which is an approach supported by the literature, and defining admissions distributions that way.

A multinomial, daily approach to modelling admissions was chosen to avoid issues relating to data sparsity, accurately reflect presence of rare days with high numbers of admissions and mimic the hospital practices of discharging patients. Alternative modelling approaches were investigated and rejected.

**Structure of this folder**

[Admissions distributions by cluster and ICU](https://github.com/c-maine/ICU_capacity_modelling_ABM/blob/master/Admissions_dists_estimation/admissions-distributions_by-clustericu.ipynb) which is the final notebook used as input to the ABM

[Admissions distributions by age and diagnosis- old notebook](https://github.com/c-maine/ICU_capacity_modelling_ABM/blob/master/Admissions_dists_estimation/admissions-distributions_by-agediagnosis.ipynb) shows older investgations based on modelling patient admissions by age and diagnosis
