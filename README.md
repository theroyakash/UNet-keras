# UNet
Design and implementation of UNet paper in keras.
## UNet Architecture:
UNet Architecture has 3 parts:
- The Contracting/Downsampling Path
- Bottleneck
- The Expanding/Upsampling Path

### Downsampling Path:

It consists of two 3x3 convolutions (unpadded convolutions), each followed by a rectified linear unit (ReLU) and a 2x2 max pooling operation with stride 2 for downsampling.
At each downsampling step we double the number of feature channels.

### Upsampling Path:
Every step in the expansive path consists of an upsampling of the feature map followed by a 2x2 convolution (“up-convolution”), a concatenation with the correspondingly feature map from the downsampling path, and two 3x3 convolutions, each followed by a ReLU.

### Skip Connection:
The skip connection from the downsampling path are concatenated with feature map during upsampling path. These skip connection provide local information to global information while upsampling.

###Final Layer:
At the final layer a 1x1 convolution is used to map each feature vector to the desired number of classes.
![img](https://i.imgur.com/vfdENcn.png)
