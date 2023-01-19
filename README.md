# LeafClassification

This is a personal project, which I decided to do after following the material of the course "Deep Learning" at DTU.
Its purpose is to train in PyTorch and DL practices.

My best results were:
          Loss     Accuracy
train: 0.036295,   0.991162
val:   0.030818,   0.954545

After submitting my model on Kaggle, I got a score of: 4.60016

In short, I used a pretrained Resnet50 to extract the "Image" features, an RNN network to extract the "Shape" features and a FC network to extract the features from the variables "Texture" and "Margin".

It is also worth noticing that using a 1-layer custom CNN for the image features also gave pretty good results (train: 0.112090, 0.973485, val: 0.079271, 0.883838).

To avoid overfitting, I used Data Augmentation, BatchNorm and dropout layers as much as possible.

In the output_layer, I combined the features and passed them from a fully connected layer with 99 output output_features (as many as my classes) and passed them from a Softmax activation function to get the probabilities.
