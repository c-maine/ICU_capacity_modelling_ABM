# ICU_capacity_modelling_ABM
An Agent-Based Model for Intensive Care Unit capacity modelling at the Beth Israel Deaconess Medical Center

**Introduction**

More than five million patients are admitted to U.S. Intensive Care Units (ICUs) each year for treatments and interventions for acute and life-critical conditions. 

ICU stays represent 13.2\% of all hospital costs (critical_care_statistics) and hospital stays that involve ICU services are 2.5 more costly than other hospital stays (utilisation_of_intensive_care_services), whilst also carrying the highest mortality of any hospital unit (icu_outcomes). For these reasons, the study of ICU medicine is of great interest to enable both improvement in clinical outcomes and more efficient health resource utilisation.

**Motivations**

The availability of Intensive Care Unit (hereafter ICU) beds is important in determining a critically ill patient’s clinical outcome. The delay of admission from the emergency room and other, non-ICU wards to the ICU increase a patient’s mortality risk (cardoso_grion_matsuo_anami_kauss_seko_bonametti_2011) (chalfin_trzeciak_likourezos_baumann_dellinger_2007) (young_gooder_mcbride_james_fisher_2003). The primary purpose of this repo is to demonstrate bed numbers that would be required to meet demand at different confidence levels and thereby prevent such delays. It is hoped that this approach will support hospital resource management and planning at the hospital-level.

Central to the issue of capacity is the tradeoff associated with specialisation- that is, whether a hospital should adapt its ICU beds to provide more specialised care at the risk that these beds become less well-suited to treat other patients. Specialised ICU beds were shown to provide no length of stay or mortality benefit compared to generalised ICU beds in a study of 84,182 patients in 124 ICUs (lott_iwashyna_christie_asch_kramer_kahn_2009). Additionally, critically ill patients assigned to an open bed in a different subspecialty ICU- the practise of ‘boarding’, even when they are treated by the same care team, saw increased mortality (stretch_penna_celi_landon_2018). This evidence suggests that improved patient outcomes should not be a rationale for specialisation, although there may be other valid reasons such as resource management.  Despite this, as hospital size increases, hospitals the prevalence of specialised ICU units increases (groeger_guntupalli_strosberg_halpern_raphaely_cerra_kaye_1993).  The secondary purpose of this repo is to provide a quantification of numbers of beds that would be required to prevent ‘boarding’ in specialised ICUs in one hospital through simulation. We hope these simulations will support decision-making with regards to the tradeoffs of specialisation of ICUs and general ICU management.

Finally, we aim to show how sensitive our results are to changes in patient admission patterns. Seasonal patterns in ICU admission and mortality are well documented (garfield_ridley_kong_burns_blunt_gunning_2008) (pendergraft_stanford_beasley_stempel_mclaughlin_2005),  notably in countries with harsh winter climates and/or influenza seasons. Situations in which over-capacity arises may result in higher overall inpatient cost (huang_thind_dreyer_zaric_2010) and increased boarding (associated with worse patient outcomes.) Here, we are especially interested in unpredictable admissions pattern changes. We expect that changes in patient admission patterns to have a significant impact on specialised ICU bed requirements to meet the same confidence level for not reaching ICU capacity.

**Agent-Based Modelling**

To support these aims, we built an Agent-Based Model (ABM) using hospital Length Of Stay (hereafter LOS) estimates and patient admission distributions drawn from the MIMIC-III critical care database. MIMIC-III is a large, freely-available database comprising de-identified health-related data associated with over 40,000 patients who stayed in critical care units of the Beth Israel Deaconess Medical Center (BIDMC) between 2001 and 2012. This database is well-suited to the task due to its detailed patient characteristics and treatment information allowing prediction of length of stay and admission time records which allow the estimation of patient admission distributions.

To achieve the best length of stay estimations, we experimented with multiple machine learning techniques and present the results here. As part of that investigation, we include findings on feature importances and correlations, notably sepsis. Additionally, we use parametric methods to estimate patient admission distributions and then update these methods using Bayesian techniques in order to be able to capture changing priors relating to admissions. These components come together in the final Agent-Based Model, which we designed to best simulate the hospital admissions, flow and discharge processes.

**Main results**

 To ensure that no ICU runs over capacity at the 95\% confidence level, 16, 12, 31, 45, 16 and 16 beds would be required in the Coronary Care Unit (CCU), Cardiac Surgery Recovery Unit (CSRU), Neonatal ICU (NICU), Medical ICU (MICU), Trauma/Surgical ICU (TSICU) and Surgical ICU (SICU) respectively. This totals 105 adult beds and 31 infant beds in the whole hospital that would be required to prevent boarding, which is 36\% and 55\% more than the hospital runs currently (105/77, 31/20.) 

A simulated prolonged heat wave increased the number of beds required to prevent boarding at the 95\% confidence level by 4.7\% for adult ICUs and 9.7\% for infant beds. 17, 13, 34, 47, 17 and 18 beds would be required under a scenario of heat for the CCU, CSRU, NICU, MICU, TSICU and SICU respectively. These results show that relatively small changes in admission patterns can have an effect on ICU and hospital capacity requirements.

The sensitivity of our results to changes in admissions distributions highlight the circumstances to which our bed estimates can and cannot be extended. This demonstrates that our results are hospital, context-specific, such that recommendations for bed numbers at BIDMC cannot be directly translated to recommendations at other hospitals. In order to purpose recommendations for other hospitals, further research into how admissions distributions generalise across populations would be required. For example, how admission patterns are different in areas with different demographic, ethnic compositions, migrations, hospital openings or closures.

Despite these limitations, we believe that this approach could be used by the BIDMC to support decisions about ICU bed resource allocation and additionally to any other hospital which has patient admission records available for distribution estimation. Specifically, the number of beds required per ICU to ensure capacity is not reached and also as part of a broader hospital resource allocation study to determine the tradeoffs associated with specialisation of ICU beds and under/over-utilisation of ICU resources.

**Using this Repo**

The data used in this project comes from: MIMIC-III, a freely accessible critical care database. Johnson AEW, Pollard TJ, Shen L, Lehman L, Feng M, Ghassemi M, Moody B, Szolovits P, Celi LA, and Mark RG. Scientific Data (2016). DOI: 10.1038/sdata.2016.35. Available from [here](http://www.nature.com/articles/sdata201635)

The sections include:

[ABM_results](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/ABM_results) contains the Agent Based Model, simulations from which the results are graphed and the final graphs themselves.

Admissions_dists_estimation

[Data_processing](https://github.com/c-maine/ICU_capacity_modelling_ABM/tree/master/Data_processing)

LOS_prediction

Sepsis_prediction
