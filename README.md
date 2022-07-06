# DrugApp: A Comprehensive Benchmark for Machine Learning-based Prediction of Drug Approval
In this study/repository, we presented a programmatic tool called “DrugApp”, that utilize available clinical trial- and patent-related data together with physicochemical and molecular features of drugs candidate compounds within a random forest classifier to predict their potential of getting approval as drugs for certain indications. The major contributions of our study are summarized below:
* We proposed comprehensive datasets, which can be useful for further computational studies as benchmarks.
* We presented important features for drug approval prediction, which can be used by both commercial and non-commercial entities to increase the efficiency of drug development procedures.
* We showed the potential of our method for revealing drugs that were withdrawn from the market sometime after their approval, indicating that it may be possible to act upon those cases in the first place to potentially prevent critical losses regarding human health. 
The modeling methodology of this study is summarized below.

![Modeling Methodology](https://user-images.githubusercontent.com/108183756/177561886-7b15e9b2-74bf-4ee6-9092-146d9cb3c836.PNG)

## Programming Environment and Files
**Descriptions of folders and files:**

*	**datasets** folder includes benchmark datasets constructed by applying extensive filtering operations. 
    * **drug_indication** folder contains FDA-approved and FDA-unapproved drug indication pairs together with all features. One-hot encoded version of categorical features are also provided. FDA-approved and FDA-unapproved drugs are represented in the column called "Label" in binary classification format (i.e., 1:approved, 0:unapproved).
    * **predicted** folder contains drug indication pairs together with all features for ongoing clinical trials. One-hot encoded version of categorical features are also provided.
    * **unique_drugs** folder contains unique FDA-approved and FDA-unapproved drugs together with randomly selected indications and all other features used for the construction of model as well as for parameter optimization (only "All" data was used), determination of evaluation metrics and feature importance. FDA-approved and FDA-unapproved drugs are represented in the column called "Label" in binary classification format (i.e., 1:approved, 0:unapproved).
*	**scripts** folder includes script files required for the construction of model as well as for parameter optimization, determination of evaluation metrics and feature importance.
*	**results** folder contains prediction results of all disease groups for ongoing clinical trials. 

**Dependencies:**

* Python 3.7.4
* Scikit-learn 1.0.2
* Pandas 1.0.3
* Numpy 1.16.5
* Matplotlib 3.2.2

**Step-by-step operation:**
1. We highly recommend you to use conda platform for installing dependencies properly. After installation of appropriate [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) version for your operating system, create and activate conda environment, and then install dependencies in the activated environment, as below:
```
conda create -n drugapp python=3.7.4
conda activate drugapp
conda install -c anaconda scikit-learn=1.0.2
conda install -c anaconda pandas=1.0.3
pip install numpy==1.16.5
pip install matplotlib==3.2.2
```
2. Clone this repository.
3. Download datasets from [here](https://drive.google.com/file/d/1zVOyFIEOo33yeF3vFE8paz5pS5H5Z99N/view?usp=sharing) and uncompress the “datasets.zip” file. Place the uncompressed folder in the cloned repository at the same level as the **results** and **scripts** folders. 
4. Set the location of **scripts** folder as the current working directory, and run the corresponding script to build models at the data scale of your interest. Instead of creating all models of the selected scale at once, you can easily edit the script file according to your purpose before running it. You need to uncomment "save model" and "save predictions" code blocks in the script file to save the constructed model and its predicted outputs, respectively.

**Example commands to run the scripts for building models of interest:**
   
For generating models for "All" disease group, run the "rf_model_for_predicting_drug_approval.py" script for RF algorithm by defining the folder name of the dataset (i.e., "All", "Alimentary", "Anti-infective", "Blood", "Dermatological", "Heart", "Hormonal", "Immunological", "Musculoskeletal", "Neoplasms", "Nervous", "Parasitic", "Rare", "Respiratory", "Sensory", and "Urinary") as parameter, e.g.:
   
```
python rf_model_for_predicting_drug_approval.py Rare
```
   
   
## License

Copyright (C) 2022 HUBioDataLab

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.

