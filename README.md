# Psychological distress in IBS

INITIATED: [Arvid Lundervold](https://www.uib.no/en/persons/Arvid.Lundervold), 2024-07-20

Code and [data](./data/BGA_IBS_SSS_B_H_F_R_77x14.csv) accompanying the paper: <br>
A.J. Lundervold, ..., A. Lundervold. **Decoding IBS: A Machine Learning Approach to Psychological Distress and Gut-Brain Interaction.**<br> To appear in _BMC Gastroenterology_ 

Last updated: 2024-08-06

<!--

_BMC Gastroenterology_ 2024;xx:yy <br>


**Website**: <TBA><br>
**PDF Version**: <TBA>><br>
Overleaf Version: https://www.overleaf.com/project/65609f60093ec62d6d1b13cb (restricted access)<br>

-->

**Website**: TBA<br>
**PDF Version**: TBA<br>
Overleaf Version: https://www.overleaf.com/project/65609f60093ec62d6d1b13cb (restricted access)<br>


### The notebooks:

- [1-exploration.ipynb](./notebooks/1-exploration.ipynb) - **Exploratory Data Analysis** of the multisource psychological distress ([data](./data/))
- [2-supervised-classification.ipynb](./notebooks/2-supervised-classification.ipynb) - **Predictive modeling** (IBS vs. HC) from multisource psychological distress [data](./data/BGA_for_classification_77x13.csv) using [PyCaret 3.0](https://pycaret.gitbook.io/docs)
- [3-unsupervised-classification.ipynb](./notebooks/3-unsupervised-classification.ipynb) - **Unsupervised classification** of the multisource psychological distress [data](./data/BGA_for_classification_77x13.csv)  using [PyCaret 3.0](https://pycaret.gitbook.io/docs)

----


### Abstract

**Purpose**: Irritable bowel syndrome (IBS) is a diagnosis defined by gastrointestinal (GI) symptoms like abdominal pain and changes associated with defecation.  
The condition is classified as a disorder of the gut-brain interaction (DGBI), and patients with IBS commonly experience psychological distress. The present study focuses on this distress, defined from reports of fatigue, anxiety, depression, sleep disturbances, and performance on cognitive tests. The aim was to investigate the joint contribution of these features of psychological distress in predicting IBS versus healthy controls (HCs) and to disentangle clinically meaningful subgroups of IBS patients. 
**Methods**: IBS patients ($n = 49$) and HCs ($n = 28$) completed the Chalder Fatigue Scale (CFQ), the Hamilton Anxiety and Depression Scale (HADS), and the Bergen Insomnia Scale (BIS), and performed tests of memory function and attention from the Repeatable Battery Assessing Neuropsychological Symptoms (RBANS). An initial exploratory data analysis was followed by supervised (\texttt{Random Forest}) and unsupervised (_K-means_) classification procedures. 
**Results**: The explorative data analysis showed that the group of IBS patients obtained significantly more severe scores on all included measures, with the strongest pairwise correlation between fatigue and a quality measure of sleep disturbances. The supervised classification model correctly predicted belongings to the IBS group in 80% of the cases in a test set of unseen data. Two methods for calculating feature importance in the test set gave mental and physical fatigue and anxiety the strongest weights.
An unsupervised procedure with $K = 3$ showed that one cluster contained 24% of the patients and all but two HCs. In the two other clusters, their IBS members were overall more impaired, with the following differences. One of the two clusters showed more severe cognitive problems and anxiety symptoms than the other, which experienced more severe problems related to the quality of sleep and fatigue. The three clusters were not different on a severity measure of IBS and age.
**Conclusion**: The results showed that psychological distress is an integral component of IBS symptomatology. The study should inspire future longitudinal studies to further dissect clinical patterns of IBS  to improve the assessment and personalized treatment for this and other patient groups defined as disorders of the gut-brain interaction. <br>
The project is registered at https://classic.clinicaltrials.gov/ct2/show/NCT04296552 (20/05/2019)}

   
**Keywords**: Irritable Bowel Syndrome (IBS);  Fatigue; Sleep Disturbances; Depression-Anxiety; Cognition; Machine Learning; Feature Importance

-----

### Installation

**CONDA ENVIRONMENT:**

_Alternatively_: make a `ibs` conda environment using an `environment.yml` file (see [here](environment.yml))

Assuming Anaconda is installed (https://www.anaconda.com) and **the following conda environment (`ibs`) installed as follows:**

```
### create the conda environment ibs:
conda create --name ibs python=3.11

## activate conda environment:
conda activate ibs

## install packages using pip

pip install ydata-profiling       # or, pip install -U ydata-profiling[notebook]
pip install pycaret[all]          # MacOS: pycaret'[all]' or, pip install -U pycaret
pip install scikit-learn-intelex  # Optional (not for M1, M2, M3 on Mac)
pip install jupyter               #
pip install openpyxl              #
pip install pyreadstat            # cfr. pd.read_spss()
pip install pingouin              # 
pip install shap                  # 
pip install xgboost               # 
pip install scikit-plot           #

# To initiate the ibs environment 
conda env update -f environment.yml

# To update the ibs environment (if new package versions become available):
conda update -n ibs --all        # To update all packages in the named environment

# To remove and reinstall the ibs environment (if installation problems):
conda deactivate
conda env remove -n ibs
#   <fix installation>
## Then, recreate the conda environment ibs as above
```

**Note**: The `scikit-learn-intelex` package is a drop-in replacement for `scikit-learn` that accelerates scikit-learn estimators using Intel(R) oneAPI Data Analytics Library (oneDAL) and Intel(R) oneAPI Threading Building Blocks (oneTBB). It is available for Linux and Windows. For more information, see https://intel.github.io/scikit-learn-intelex/

**Note**: The `ydata-profiling` package is an alternative to `pandas_profiling` and is a visual data profiling tool. It is available for Linux and Windows. For more information, see https://github.com/ydataai/ydata-profiling

**Note**: The `pycaret` package is a low-code machine learning library that automates machine learning workflows. It is available for Linux and Windows. For more information, see https://pycaret.org/  and https://pycaret.gitbook.io/docs/get-started/installation   

**Note**: The `pingouin` package is a statistical package based mostly on pandas and seaborn. It contains tools that require pandas, numpy, scipy, and statsmodels. It is available for Linux and Windows. For more information, see https://pingouin-stats.org

**Note**: The `shap` package is a unified approach to explain the output of any machine learning model. It connects the gap between the model and the data. It is available for Linux and Windows. For more information, see https://shap.readthedocs.io and https://github.com/shap/shap

**Note**: The `xgboost` package is an optimized distributed gradient boosting library designed to be highly efficient, flexible, and portable. It is available for Linux and Windows. For more information, see https://xgboost.readthedocs.io and
https://github.com/dmlc/xgboost

**Note**: The `scikit-plot` package is a visualization library for quick and easy generation of common plots in data analysis and machine learning. It is available for Linux and Windows. For more information, see https://scikit-plot.readthedocs.io and https://github.com/reiinakano/scikit-plot
