# Deep Learning - 6.1 mini project

# Improving the model
## Default
Train: 0, 1
Val: 1.79, 0.64

## Added maxpool2d
Pooling will shrink the image and get higher level features, e.g. edges.
Train: 0.02, 1
Val: 1.68, 0.67

## Increased the validation dataset (0.1 -> 0.3)
Train: 0, 1
Val: 1.56, 0.61

## Reduce overfitting
### Added BatchNorm2d
Train: 0, 1
Val: 1.93, 0.59
### Added Dropout (0.2) after conv2d
Train: 0.01, 1
Val: 6.35, 0.49
### Added Dropout (0.5) after fc - This actually seems to kindof reduce overfitting
Train: 0.03, 0.97
Val: 4.98, 0.55

### Added dataloader, moved BatchNorm2d after Relu and added BatchNorm1d 
Source: https://stackoverflow.com/questions/47143521/where-to-apply-batch-normalization-on-standard-cnns#:~:text=Andrew%20Ng%20says%20that%20batch,linearity%20of%20the%20current%20layer
Train: 0.01, 1
Val: 0.14, 0.83

Too good to be true. This is likely a random good result because of the random split between the train and validation set.
Re-running it gave results that did not exceed 0.6 accuracy.
The results also fluctuated wildly between epochs.

### Removed batchnorm before the final FC layer
Source: https://stats.stackexchange.com/questions/361700/lack-of-batch-normalization-before-last-fully-connected-layer

### Added extra fc layer in for the margin, texture features, as more complicated relationships between these variables might help with predictions
train: 0.159681, 0.977273
val: 0.206735, 0.767677

### Data Augmentation
Added random Rotation(90), vertical_flip(0.25) and horizontal_flip(0.25)
train: 0.112090, 0.973485
val: 0.079271, 0.883838

This is considered the first very good result.

### Replaced the cnn layer with a pretrained resnet50 and stopped the training early
train: 0.036295, 0.991162
val: 0.030818, 0.954545

