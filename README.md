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

## Feature Engineering

- ML Models cannot handle IP addresses. IP addresses were handled as follows:
  Eg: 192.168.4.4 was divided into four columns separated at "."
- Label Encoding the target variable.

## Machine Learning

4 ML Models were used and their accuracies were noted.
- Logistic Regression: 0.68225
- Random Forest: 0.73365
- KNN: 0.67754
- AdaBoost: 0.99999

![image](https://user-images.githubusercontent.com/41315903/172191979-68503b45-53db-402d-a32a-4b8553fcdb2a.png)

Clearly, the AdaBoost Classifer stood out with 99.9% accuracy. Below is it's confusion matrix:

![image](https://user-images.githubusercontent.com/41315903/172192168-6442e3a7-3b40-4e96-ae6d-09de6544ef3b.png)

And here is the classification report:

![image](https://user-images.githubusercontent.com/41315903/172200284-66351563-11de-46e0-be1d-464b9205b828.png)

