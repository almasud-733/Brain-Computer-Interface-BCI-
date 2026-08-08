Brain-Computer Interfaces (BCIs) based on motor imagery (MI) electroencephalography 
(EEG) offer a non-invasive pathway for communication and control, but their real-world 
reliability is hindered by high inter-subject variability and low signal-to-noise ratio. This 
study presents a comparative evaluation of three modeling paradigms, a classical machine
learning ensemble, EEGNet, and DeepConvNet for binary left-hand versus right-hand MI 
classification using the PhysioNet EEG Motor Movement/Imagery dataset. To improve 
reliability, a per-subject quality screening stage pools only "good" subjects into a common 
training/test split, rather than training on the full unfiltered cohort. Handcrafted features 
were extracted using a Filter-Bank Common Spatial Patterns (FBCSP) front end, which 
decomposes the mu/beta range into nine overlapping sub-bands and applies mutual
information feature selection, feeding five hyperparameter-tuned base classifiers (LDA, 
SVM, Random Forest, Logistic Regression, XGBoost) whose out-of-fold probabilities are 
combined via a Logistic Regression meta-learner. This ensemble is benchmarked against 
two end-to-end deep learning architectures operating directly on raw motor-cortex channel 
data: EEGNet, a compact CNN using depthwise and separable convolutions to learn spatial 
and temporal filters jointly, and DeepConvNet, a deeper convolutional network with 
progressively pooled temporal-spatial blocks. On a held-out test set, the meta-ensemble 
reached 81.89% accuracy, DeepConvNet reached 80.00% accuracy, while EEGNet 
achieved the best overall performance at 83.02% accuracy, suggesting that a compact 
CNN's ability to learn subject-general spatiotemporal filters directly from raw signal can 
outperform both a heavily hand-engineered feature-ensemble pipeline and a deeper 
convolutional architecture on this task. These findings indicate that combining subject
quality screening with lightweight, learned spatial filtering offers a favorable accuracy
complexity trade-off for practical, cross-subject MI-based BCI systems.<img width="1536" height="1024" alt="left vs right hand imagery" src="https://github.com/user-attachments/assets/e509f7d7-7e3d-47d5-9ac0-b35082b1ac8f" />
<img width="1300" height="1210" alt="64 electrode" src="https://github.com/user-attachments/assets/a4bf96d1-1479-4f4e-99f2-92cd43821fc1" />
