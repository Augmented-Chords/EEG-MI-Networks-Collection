# EEG-MI-Networks-Collection
This repository is for collect deep learning networks and train them on BCI Competition Data sets or EEG Motor Movement/Imagery Dataset.

Using Keras with TensorFlow, MNE-Python, Scikit-learn, etc.

https://www.bbci.de/competition/

https://physionet.org/content/eegmmidb/1.0.0/

Please forgive many of the networks here are coded based on the descriptions and figures in the original paper, there might be different and incorrect parts here.

Also, due to differences in preprocessing methods and various parameter settings, there may be significant different results compared to the original papers.

## Preprocess of BCI Competition IV Data sets 2a

* Data sets 2a Preprocess 0.0-4.0s 250Hz

Extracts 4 seconds (1000 time points) after the cue appears.

* Data sets 2a Preprocess 0.5-2.5s 128Hz

Downsample to 128Hz, extracts 2 seconds (256 time points) after the cue appears for 0.5 seconds.

## Preprocess of EEG Motor Movement/Imagery Dataset

The sampling rate of this dataset is 160Hz, extracts 4 seconds (640 time points) in each event.

Channel selection refer to

https://iopscience.iop.org/article/10.1088/1741-2552/ac4430

FC5-FC6, FC3-FC4, FC1-FC2; C5-C6, C3-C4, C1-C2; CP5-CP6, CP3-CP4, CP1-CP2 were used.

Each pairs of symmetrical signal data feed to the network as a different unit.

## EEGNet

Attempted to train on BCI Competition IV Data sets 2a (0.5-2.5s 128Hz 256 time points), reached a validation accuracy rate of 63.90%.

This network does not seem to be designed for direct classification in the original paper.

- https://iopscience.iop.org/article/10.1088/1741-2552/aace8c

## EEG-Inception

- https://iopscience.iop.org/article/10.1088/1741-2552/abed81

Attempted to train on BCI Competition IV Data sets 2a (0.0-4.0s 250Hz 1000 time points), reached a validation accuracy rate of 67.57% with just 10 epochs, but serious overfitting occurred.

In original paper, they extracts 3 seconds (750 time points) from each task.

Also, they used data augmentation to avoid overfitting, but here is directly used the original data for training.

## Simplified CNN Classification Method

- https://www.frontiersin.org/articles/10.3389/fnhum.2020.00338/full

Attempted to train on EEG Motor Movement/Imagery Dataset, reached a validation accuracy rate of 69.64%.

The original paper trained 9 groups of pair separetely.

Also, The original network only has four outputs (No resting state), changed to five here, this may also have a negative impact.

## HopefullNet

- https://iopscience.iop.org/article/10.1088/1741-2552/ac4430

Attempted to train on EEG Motor Movement/Imagery Dataset, reached a validation accuracy rate of 91.40%.

In the original paper they used SMOTE to balance the dataset and a lower learning rate to get better accuracy.
