# EEG-MI-Networks-Collection
This repository is for collect deep learning networks and train them on EEG Motor Movement/Imagery Dataset.

https://physionet.org/content/eegmmidb/1.0.0/

The sampling rate for this dataset is 160Hz, each event extracts 4 seconds, 640 time points.

No FIR or IIR filters applied.

Channel selection refer to

https://www.frontiersin.org/articles/10.3389/fnhum.2020.00338/full

FC5-FC6, FC3-FC4, FC1-FC2; C5-C6, C3-C4, C1-C2; CP5-CP6, CP3-CP4, CP1-CP2 were used. Each pairs of symmetrical epochs feed to the network as a different unit.

## HopefullNet

- https://iopscience.iop.org/article/10.1088/1741-2552/ac4430
- 
In the original paper they used SMOTE to balance the dataset and a lower learning rate to get better accuracy.
