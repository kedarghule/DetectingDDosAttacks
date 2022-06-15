# Detection of DDoS Attacks using Machine Learning

## Problem Statement

Distributed Denial of Service or DDoS attack is one in which traffic from different sources flood a victim thereby interrupting service. The problem statement is that given a labelled dataset of the details of DDoS attacks, we need to implement a classification algorithm to find out if the attack is a DDoS attack or not.

## Dataset

The dataset is a subsampled version of the CSE-CIC-IDS2018, CICIDS2017, and CIC DoS datasets (2017). It consists of 80% benign and 20% DDoS traffic, in order to represent a more realistic ratio of normal-to-DDoS traffic.

## Data Preprocessing

- Source IP and Destination IP were extracted from Flow ID.
- Data was sorted by Timestamp.
- Any unneccessary columns were dropped.
- Check for missing values was performed.
- Check for class imbalance.

  ![image](https://user-images.githubusercontent.com/41315903/173917041-920d3a10-3043-42cb-9a42-ab0ea91075c1.png)
  
  We can see that there is class imbalance present and this needs to be handled.

## Feature Engineering

- ML Models cannot handle IP addresses. IP addresses were handled as follows:
  Eg: 192.168.4.4 was divided into four columns separated at "."
- Label Encoding the target variable. 1 stands for DDoS attack and 0 for benign.

## Handling Class Imbalance And Splitting the Data

Since we have over 100K samples in the minority class, we can use random undersampling as our approach to handle class imbalance. `RandomUnderSampler` from the `imblearn.under_sampling` library. After this, we split the data: 70% training set and 30% test data.

## Machine Learning

4 ML Models were used and their ROC AUC Scores were noted.
- Logistic Regression: 0.9904716509939988
- Random Forest: 0.9999999856560075
- KNN: 0.9998091214573287
- AdaBoost: 0.9999991923228831

Furthermore, their accuracies were noted too:
- 'Logistic Regression': 0.9592333333333334
- 'Random Forest': 0.9999666666666667
- 'KNN': 0.9987833333333334
- 'AdaBoost': 0.9997

The better option among these classifiers is Random Forest eventhough all of them perform well.

Below is the Confusion Matrix for the Random Forest Classifier:

![image](https://user-images.githubusercontent.com/41315903/173928475-b9c66f36-fdcc-441d-bd26-e70a09e6bb37.png)

Below is the Precision-Recall Curve:
 
![image](https://user-images.githubusercontent.com/41315903/173929356-fad31417-8486-4827-a5dc-7f06f8b5a3b8.png)


