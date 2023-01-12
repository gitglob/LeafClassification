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
### Data Augmentation
For this part, I created a custom DataLoader using the necessary PyTorch modules


