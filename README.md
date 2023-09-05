# EEG-MI-Networks-Collection
This repository is for collect deep learning networks and train them on BCI Competition Data sets or EEG Motor Movement/Imagery Dataset.

https://www.bbci.de/competition/iv/

https://physionet.org/content/eegmmidb/1.0.0/

The training results can be found in the outputs of Jupyter notebook.

Due to differences in preprocessing methods and various parameter settings, there may be significant differences in results compared to the original paper.

## Preprocess of BCI Competition IV Data sets 2a

The sampling rate of this dataset is 250Hz, downsample to 128Hz, extracts 2 seconds (256 time points) after the cue appears for 0.5 seconds.

## Preprocess of EEG Motor Movement/Imagery Dataset

The sampling rate of this dataset is 160Hz, extracts 4 seconds (640 time points) in each event.

Channel selection refer to

https://iopscience.iop.org/article/10.1088/1741-2552/ac4430

FC5-FC6, FC3-FC4, FC1-FC2; C5-C6, C3-C4, C1-C2; CP5-CP6, CP3-CP4, CP1-CP2 were used.

Each pairs of symmetrical signal data feed to the network as a different unit.

## EEGNet

- https://iopscience.iop.org/article/10.1088/1741-2552/aace8c

## Simplified CNN Classification Method

- https://www.frontiersin.org/articles/10.3389/fnhum.2020.00338/full

The original paper trained 9 groups of pair separetely.
Also, The original network only has four outputs, changed to five here.

## HopefullNet

- https://iopscience.iop.org/article/10.1088/1741-2552/ac4430

In the original paper they used SMOTE to balance the dataset and a lower learning rate to get better accuracy.
