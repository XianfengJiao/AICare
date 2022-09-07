# AICare
The source code for paper *Mortality Prediction with Adaptive Feature Importance Recalibration for Peritoneal Dialysis Patients: a deep-learning-based study on a real-world longitudinal follow-up dataset*

In this work, our objective is to develop a deep learning model for a real-time, individualized, and interpretable mortality prediction model, AICare, for patients with Peritoneal Dialysis (PD). This study has collected 13,091 clinical follow-up visits and demographic data of 656 PD patients from Peking University Third Hospital, covering more than 12 years. There are about 20 visits recorded for each patient, with an average visit interval of 2.7 months and an average follow-up time of 4 years. To summarize:

1)	Experiment results show that AICare achieves 81.6% AUROC (area under the receiver operating characteristic curve) on the mortality prediction task, which outperforms the state-of-the-art comparative deep learning models while simultaneously providing qualitative interpretability.
2)	This study first provides a comprehensive elucidation of the relationship between the causes of mortality in patients with PD and clinical features based on an end-to-end deep learning model. 
3)	This study first reveals the pattern of variation in the importance of each feature in the mortality prediction and provides recommended reference value for most PD patients based on built-in interpretability, without any injection of human physicians' knowledge. 
4)	To further foster personalized clinical service, we develop a practical AI-Doctor interaction system to visualize the trajectory of patients' health status and risk indicators.

Some online resources and the research overview figure are listed below:
1)	We have made an abstract presentation video to introduce our work https://youtu.be/BZybN7U_nMs.
2)	Our developed health trajectory visualization system with anonymous case studies is publicly available at http://47.93.42.104/A8. 
3)	Visualization of the importance of the features is available at http://47.93.42.104/statistics/feature. 
4)	Users can upload the data online to get the prediction results immediately http://47.93.42.104/predict or download the code to train the model based on their dataset offline https://github.com/Accountable-Machine-Intelligence/AICare.




## Overview

#### Mortality Prediction Research Overview for peritoneal dialysis (PD) Patients.

<img src="figs/overview.png" alt="overview.png" style="zoom:67%;" />




### Implications

#### Average Feature Importance Heatmap for Diverse Mortality Causes Generated by AICare.

<img src="figs/cod.png" alt="cod" style="zoom: 50%;" />



 The **darker** the color, the greater the importance. 

- Serum albumin is the most important feature in mortality prediction, especially for peritoneal dialysis (PD) patients who died of gastrointestinal (GI) disease and peripheral vascular disease (PVD). 

- Diastolic blood pressure (DBP) is the second indicative feature, especially for PD patients who died of cachexia, cancer and cerebrovascular disease (CVE).

- Come with the paper for more details.

  #### Average Feature Importance Variation Learned by AICare along with Feature Values.

  <img src="figs/importance.png" alt="importance" style="zoom: 67%;" />

  

  The clinical visits are marked as colored dots and histograms. Red represents **high risk** predicted by AICare, while green represents **low risk**.  The average feature importance is visualized as blue fold lines. 
  The traditional clinical reference values are vertically marked as blue dotted lines. 
  There are two variation patterns of feature importance, **V-shaped parabolic curves** (e.g., albumin, diastolic blood pressure) and **L-shaped fold lines** (e.g., systolic blood pressure, hemoglobin). 

  1) We take the serum albumin's importance variation as an example of a **V-shaped** parabolic curve. For most patients, when albumin is lower (higher) than the turning point of 32 g/L, the more extreme the value is, the more attention weight is assigned by AICare, which means this feature takes essential parts in health status representation learning, and meanwhile the predicted mortality risk rises (declines). As a result, AICare recommends improving the serum albumin to above 32 g/L, the higher the better.
  2) On the contrary, we take the systolic blood pressure's (SBP) importance variation as an example of an **L-shaped** fold line. For most patients, when SBP is lower than the turning point of 130 mmHg, the lower the value is, the more attention weight is assigned. However, when SBP is higher than 130 mmHg, the attention weight drops to nearly 0,  meaning this feature will no longer affect the health status representation learning. As a result, AICare recommends improving the SBP to above or near 130 mmHg, but higher will not be beneficial.


#### More Case study

For more case studies, please visit:

​	http://47.93.42.104/A1 

​	http://47.93.42.104/A2

​	http://47.93.42.104/A3

​	http://47.93.42.104/A4

​	http://47.93.42.104/A5

​	http://47.93.42.104/A6

​	http://47.93.42.104/A7

​	http://47.93.42.104/A8

​	http://47.93.42.104/A9

​	http://47.93.42.104/A10

### Requirements

* Install python, pytorch. We use Python 3.7.3, Pytorch 1.5.1.
* If you plan to use GPU computation, install CUDA

