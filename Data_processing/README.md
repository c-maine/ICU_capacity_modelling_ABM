# Data Processing

This folder takes raw data from multiple sources and applies the pre-processing needed for further exploration.


- The four raw data sources provide 7 csvs. These are found in the folder 'input data'
- The folder 'notebooks' provides code for our data transformations, including clustering exploration


The motivation for using clusters to predict hospital length of stay follows from the paper by Azari et al [27], who consistently found that using clustering as a precursor to form the training set; binning the LOS into three groups of short, medium, and long stays, gives better prediction results as compared to non-clustering based training sets.


- The output data is found in the folder 'output_data'. These outputs will be used in 'Admissions_dists_estimation' and 'los_prediction'




