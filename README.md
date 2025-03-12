# Empowering IoT Security: Deploying TinyML Ensemble Techniques for Cyberattack Detection

## Authors
- Abderahmane HAMDOUCHI
- Ali IDRI

## Affiliations
- Mohammed VI Polytechnic University, Benguerir, Morocco
- Software Project Management Research Team, ENSIAS, Mohammed V University in Rabat, Morocco

## Contact
- E-mail: {Abderahmane.HAMDOUCHI ; Ali.IDRI}@Um6p.ma

## Abstract
As the Internet of Things (IoT) grows and devices connect, protecting IoT networks from vulnerabilities is crucial. Intrusion detection systems (IDS) that use machine learning (ML) techniques are vital for increasing security and preventing unauthorized access. This research constructs and assesses TinyML ensemble and singular techniques, focusing on bagging (Random Forest) and boosting (XGBoost) using decision trees as the base learner, employing three feature selection (FS) methods (ANOVA, mRMR, and chi-square), and different feature thresholds over the NF-ToN-IoT-v2 and NF-BoT-IoT-v2 datasets for cyberattack detection. Evaluations were performed on the Arduino UNO, considering prediction performance criteria, inference time, static RAM, and flash memory, and using the Borda Count voting system to rank the models. The results show that XGBoost with 5 estimators, ANOVA with mRMR as FS, and selecting 40% of the best features is the best configuration for a TinyML-based IDS.

## Keywords
- Bagging
- Boosting
- TinyML
- Internet of Things
- Intrusion Detection Systems
- Arduino UNO

## Introduction
The Internet of Things (IoT) introduces a new way of enabling a wide range of applications across various fields. However, it also raises the risk of cybersecurity attacks. This study aims to address current gaps by evaluating and comparing the effects of three FS techniques on the performance of binary classification using TinyML ensemble techniques.

## Research Questions
1. How does the number of estimators affect the performance of ensemble models on cyber detection?
2. How does the number of estimators affect the performance of TinyML ensemble models deployed on the Arduino UNO device?
3. What combination of FS, feature threshold, and number of estimators is optimal for building the most effective IDS using the TinyML ensemble on Arduino UNO?
4. What is the most effective TinyML strategy, using ensemble or single models, for detecting cyberattacks in IoT environments when deployed on Arduino UNO?

## Main Contributions
- Evaluating the effectiveness of bagging and boosting techniques in IDS.
- Conducting an experimental evaluation of TinyML ensemble models with varying estimator counts and feature thresholds.
- Proposing the optimal integration of FS methods and TinyML techniques for effective attack detection in varied IoT environments.
- Comparing bagging and boosting in the context of IoT and TinyML.
- Identifying the optimal approach (ensemble vs. singular) for anomaly detection in TinyML-based IoT IDS.

## Structure
1. **TinyML Technology**
2. **Feature Selection Techniques**
3. **Boosting and Bagging Techniques**
4. **Datasets and Performance Metrics**
5. **Experimental Design and Results**
6. **Discussion**
7. **Limitations and Future Work**
## Experimental design

![Experimental Design](experimental_design.png)
## Notebook
The accompanying Jupyter Notebook `bml-ToN-Num.ipynb` contains all the steps of the research paper, including data preprocessing, feature selection, model training, and evaluation.

## Performance Metrics
The folders `NF-BoT-IoT-v2_Results_Performances_Models` and `NF-ToN-IoT-v2_Results_Performances_Models` contain JSON files with the performance measurements of the machine learning models. These files include metrics evaluation criteria.
## Model Deployment
The zip files `NF-BoT-IoT-v2_TinyML_Models_Arduino_C.zip` and `NF-ToN-IoT-v2_TinyML_Models_Arduino_C.zip` contain the code for all generated models to deploy on Arduino. You can perform further experimentation, such as measuring energy consumption, to enhance the evaluation of the models.


### Notebook Steps
1. **Importing Libraries and Loading Data**:
    - Import necessary libraries such as pandas and warnings.
    - Load the dataset from a CSV file.

2. **Feature Deletion**:
    - Define lists of features to be deleted based on different criteria such as categorical features, unused features, target features, and features to be dropped due to high correlation or high variance inflation factor (VIF).
    - Drop the specified features from the dataset.

3. **Data Preprocessing**:
    - Convert specific columns to integer type.
    - Split the dataset into training and testing sets.
    - Reset the index of the datasets.

4. **Scaling of Numerical Values**:
    - Scale numerical features using StandardScaler from sklearn.

5. **Feature Selection**:
    - Apply SelectKBest with f_classif to select the top features based on ANOVA F-test.

6. **Model Training**:
    - Train models using XGBoost and Random Forest with different numbers of estimators.
    - Evaluate the models using metrics such as MCC and Kappa.

7. **Convert Models to TinyML**:
    - Use MicroMLGen to convert trained models to TinyML format.
    - Deploy the models on Arduino UNO and measure performance metrics such as latency, SRAM, and flash memory.

## Instructions
1. **Clone the Repository**
   ```sh
   git clone <repository-url>
   cd TinyML
   ```

2. **Install Dependencies**
   ```sh
   pip install -r requirements.txt
   ```

3. **Run the Notebook**
Open `Notebook.ipynb` in Jupyter Notebook or JupyterLab and follow the steps outlined in the notebook. This notebook uses the NF-ToN-IoT-v2 dataset, but you can replace it with the NF-BoT-IoT-v2 dataset. You should download the two datasets used from [this link](https://staff.itee.uq.edu.au/marius/NIDS_datasets/).


## Requirements
- Python 3.8 or higher
- Jupyter Notebook
- Required Python libraries (specified in `requirements.txt`)


## Citation
If you use this work, please cite the paper as follows:
```
@article{hamdouchi2025empowering,
    title={Empowering IoT security: deploying TinyML ensemble techniques for cyberattack detection},
    author={Hamdouchi, Abderahmane and Idri, Ali},
    journal={Scientific African},
    year={2025},
    publisher={Elsevier}
}
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.