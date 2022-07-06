# ML_drug_discovery
## Goal
This project classifies effectiveness (active or inactive) of the drug based on Lipinski molecular descriptors for ABL-kinase (target protein) using multiple machine learning models. 

## Description
ABL-kinases are associated with multiple diseases including Parkinson's disease and other neurodegenerative diseases. This project is binary classification problem
where features (X) are Lipinski molecular descriptors and target (y) is either `active` or `inactive`.

## Data
Data is obtained from the [ChEMBL Database](https://www.ebi.ac.uk/chembl/). The [ChEMBL Database](https://www.ebi.ac.uk/chembl/) is a database that contains curated bioactivity data of more than 2 million compounds.

## Data Preprocessing

### Feature extraction
The features (i.e. Lipinski molecular descriptors) were generated from the smiles obtained the ChEMBL Database. 
Lipinski's rule states that, in general, an orally active drug has no more than one violation of the following criteria$^1$:

- No more than 5 hydrogen bond donors (the total number of nitrogen–hydrogen and oxygen–hydrogen bonds)
- No more than 10 hydrogen bond acceptors (all nitrogen or oxygen atoms)
- A molecular mass less than 500 daltons
- An octanol-water partition coefficient (log P) that does not exceed 5                             

### Labelling Data
The bioactivity data is in the IC50 unit. Compounds having values of less than 1000 nM will be considered to be active while those greater than 10,000 nM 
will be considered to be inactive. As for those values in between 1,000 and 10,000 nM will be referred to as intermediate.

### EDA
#### Pairplots

<img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/Pairplot.png" width="1000" height="800">

#### Correlation Plot

<img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/Correlation.png" width="700">

#### Class Distribution
<img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/Class-distribution.png">

#### Boxplots
![boxplot](https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/boxplot_lipinksi_descriptors.png)

## Machine Learning models

- k-Nearest Neighbour (KNN)
-  Logistic regression
-  Decision tree
- Random forest
-  Gradient boosting
- Support vector machine
-  Neural network
-  XGBoost
- CatBoost

## Results
### Model Comparison

<p float="left">
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/model-comparision.png" width="300" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/drug-effectiveness.png" width="250" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/drug-noneffectiveness.png" width="250" /> 
</p>


### Confusion Matrix
<p float="left">
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-kNN.png" width="250" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-Logistic Regression.png" width="250" /> 
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-Decision Tree.png" width="250" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-Random Forest.png" width="250" /> 
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-Gradient Boosting.png" width="250" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-SVM.png" width="250" /> 
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-Neural Networks.png" width="250" />
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-XGBoost.png" width="250" /> 
  <img src="https://github.com/Mayank-5245/ML_drug_discovery/blob/master/images/confusion-matrix-CatBoost.png" width="250" />
</p>

## Conclusion
- Performance of all machine learning models used is decent based on 10-fold cross validation of the dataset. `XGBoost` seems to providing the best performance.
- `Neural Network` achieves a highest score in predicting both classes.
- Feature selection suggests the `NumHDonors` and `NumHAcceptors` are the most crucial factor for the successful prediction of bioactivity of the drug.

## References
1. [Wikipedia.org (Lipinski's rule of five)](https://en.wikipedia.org/wiki/Lipinski%27s_rule_of_five#:~:text=Lipinski's%20rule%20states%20that%2C%20in,all%20nitrogen%20or%20oxygen%20atoms))
2. [ChEMBL Database](https://www.ebi.ac.uk/chembl/)
