# Cancer Drug Response Prediction Using Machine Learning Algorithms

Using metabolomics profiles of 927 cell lines and their corresponding drug response data to 328 drugs, machine learning algorithms are used in order to classify each cell line as a responder or non-responder to a particular drug

The main objective of this research is to improve personalized cancer therapy using machine learning algorithms.

### Dataset information

We are going to use 3 datasets, Metabolomics dataset, metadata and drug response data. These datasets are publicly available from DepMap portal (Cancer Dependency Map) and can be downloaded from the following link: https://depmap.org/portal/

1. Metabolomics dataset - contains metabolomic profiles of 927 cell lines.
2. Metadata - contains metadata of the cell lines in the metabolomics dataset and includes information like the age, sex and lineage of the cancer.
3. Drug Response Data - contains the drug response values of the cancer cell lines.

We are going to be working with 6 clinically approved drugs: CISPLATIN, GEMCITABINE, DOCETAXEL, DOXORUBICIN, GEMFITNIB, PACLITAXEL. So we are going to be creating subsets of each individual drug. These subsets will contain the cancer cell lines, their metabolite profiles and the drug response data for each of these drugs. 

### Setup

1. We are going to use Jyputer Notebooks are our workstation - can be downloaded from Anaconda (https://www.anaconda.com/products/distribution)
2. The following packages are required for the machine learning models: Numpy, Pandas, Scikit-learn, Seaborn, Matplotlib
3. These packages are already installed via Anaconda otherwise the attached codes can be run on the Anaconda Prompt in order to install the packages.

```
conda install -c anaconda pandas
conda install -c anaconda numpy
conda install -c anaconda scikit-learn
conda install -c anaconda seaborn
conda install -c conda-forge matplotlib
```

4. We are all set.

### Workflow

1. Merge the three datasets based on the Cell Line IDs.
2. Create a subset dataset for a particular drug.
3. Drop the cell line and drug response data records which belong to GDSC1 phase.
4. Normalize the dataset using Standard Normalization technique.
5. Calculate the IC50_PUBLISHED mean value
6. Any drug response greater than the mean value is labelled as "Responsive" and anything less is labelled as "Non-Responsive"
7. Dimension reduction using Correlation
8. Feature selection using Recursive Feature Elimination using Cross Validation, base estimator being Random Forest and the scoring metric is Accuracy across 5 Stratified K Folds.
9. Extract the important features
10. Train and test the model using RandomForestClassifier, Support Vector Machine and AdaBoost
11. Use classification_report in order to understand the performance of the models.


