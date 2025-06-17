# Frame-Level Speech Recognition

This project focuses on frame-level phoneme state classification using deep neural networks. Given Mel spectrogram frames of speech audio, the goal is to predict the phoneme state for each frame using a feed-forward neural network.

## Goal

Build models that predict the phoneme state of each 28-dimensional Mel spectrogram frame in an utterance.

## Dataset

- Audio from Wall Street Journal (WSJ) articles, read aloud and labeled
- Data format: Mel spectrograms with shape (T, 28)
- Each frame has a corresponding phoneme state label
- ~28,539 training samples

## Phonemes

- 40 phoneme classes
- Each phoneme is divided into 3 phoneme states (subphonemes)
- Examples: "AA", "AE", "B", "CH", "D", "EH", etc.

## Model

### FF-DNN (Feed-Forward Deep Neural Network)
- Input: Frame + optional context
- Output: Phoneme state probabilities
- No batch norm or dropout
- Label smoothing, gradient clipping, learning rate scheduler used

### LA-DNN (Linear Augmented DNN)
- Deeper network with better gradient flow
- Based on [this paper](https://ieeexplore.ieee.org/document/7472646)
- Similar training setup as FF-DNN

## Experiments

### Experiment I
- FF-DNN
- Varying left/right context
- No data augmentation or hyperparameter tuning
- Used best practices: weight initialization, label smoothing, gradient clipping

### Experiment II
- LA-DNN
- No data augmentation or hyperparameter tuning
- Same best practices as above

## Evaluation

- Accuracy
- Precision and Recall
- Confusion Matrix

## References

- [FF-DNN Paper](https://ieeexplore.ieee.org/document/5734801)
- [LA-DNN Paper](https://ieeexplore.ieee.org/document/7472646)
- [Mel Spectrogram Explanation](https://haythamfayek.com/2016/04/21/speech-processing-for-machine-learning.html)

