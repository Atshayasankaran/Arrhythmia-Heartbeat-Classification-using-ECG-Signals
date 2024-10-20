# Arrhythmia-Heartbeat-Classification-using-ECG-Signals
An arrhythmia is a disorder where the heart beats out of its usual rhythm. It means the heart beats irregularly.
The rate of a person’s heartbeat is determined by electrical signals flowing through the heart. These signals
are produced by the Sino Atrial (SA) node in the heart which acts as a natural pacemaker. If these electrical
signals are irregular, it leads to heart problem. In recent years, the individuals who are diagnosed with this
condition has increased. In this work hybrid model is created for feature extraction and classification of various arrhythmias which includes Nonectopic beats (normal beat), Ventricular ectopic beats, Supraventricular ectopic beats, Fusion Beats and Unknown Beats by comparing various algorithms for feature extraction, feature reduction and classification. 

# Dataset
In this study, Massachusetts Institute of Technology-Beth Israel
Hospital (MIT-BIH) Arrhythmia Dataset is used. Dataset contains
the ECG signals taken from 47 persons recorded for 24 h. This data
set contains ECG signals of subjects aged between 23 and 89 and
also contain 53% male and 47% female cardio signals.

dataset - https://www.kaggle.com/datasets/taejoongyoon/mitbit-arrhythmia-database/data

# Model Architecture
<p align="center">
<img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/Architecture.JPG">
</p>

# Preprocessing
1)	Denoising is performed to minimize the noise or unwanted data
from the ECG signal. For denoising Discrete Wavelet Transform (DWT)
is used.
<h5 align="center">ECG Signal in the dataset</h5>
<p align="center">
<img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/ECG.JPG">
</p>

2)	The dataset contains the ECG signal with continuous beats. Segmentation is
used to separate a single beat from the continuous beats.

<h5 align="center">Denoised and Segmented signals</h5>
<p align="center">
<img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/Denoised signal.JPG">
</p>

3)	Resampling is the process of balancing an unbalanced dataset. The
dataset has a varied amount of data for each class.

<p align="center">
 <img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/ Class distribution.JPG">
</p>

When compared to the class with the most instances, the number of instances of the class with the fewest instances is less than one percent. To balance the dataset, resampling is performed. After sampling, each class contains 5000 samples.

# Feature Extraction
Feature extraction is employed to capture important signal characteristics. This work utilizes techniques such as Long Short-Term Memory (LSTM), Gated Recurrent Units (GRU), and Bidirectional LSTM to achieve this.

# Feature Reduction
For feature reduction, the goal is to minimize the number of features after extraction to speed up training and testing processes. Features are derived from the flatten layer of the deep learning model, and then reduced using two methods: Linear Discriminant Analysis (LDA) and Principal Component Analysis (PCA).

<p align="center">
 <img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/ Feature reduction.JPG">
</p>


# Classification
Classification is performed by feeding the reduced features into various machine learning algorithms. The techniques used for classification include Decision Tree, Random Forest, Naive Bayes, K-Nearest Neighbors (KNN), and Support Vector Machines (SVM) with different kernels: Polynomial, RBF, and Sigmoid.

# Results and Conclusion
Among all the tested algorithms, the BiLSTM combined with Random Forest achieved the highest accuracy of 98.84%. However, the proposed hybrid model, BiLSTM + Random Forest + PCA, produced a slightly lower accuracy of 98.46% but with reduced prediction time. In comparison, the hybrid model LSTM + Random Forest + PCA delivered a lower accuracy of 98.2%. 

<h3 align="center">10-fold cross validation</h3> 

<p align="center">
 <img src="https://github.com/Atshayasankaran/Arrhythmia-Heartbeat-Classification-using-ECG-Signals/blob/main/img/ Cross validation.JPG">
</p> 

The models are tested using 10-fold validation method, which again
ensures the consistency of the proposed models. This proposed hybrid
model is used to assist the physicians to diagnosis the heart problem
patients quickly and start the treatment at the earliest possible and
saves the life of patients.

# Publication
 I have published a paper in Elsevier journal based on this project. For a more detailed description about the project, please refer to the paper:

- **P. Varalakshmi, Atshaya P. Sankaran** (2023), "An improved hybrid AI model for prediction of arrhythmia using ECG signals", Biomedical Signal Processing and Control (https://doi.org/10.1016/j.bspc.2022.104248)






