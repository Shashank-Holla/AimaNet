# AimaNet - Detecting Heart Rate from Facial Videos

AimaNet is a open source implementation for detecting blood volume pulse from facial videos. The model uses Temporal Shift Attention based convolution . The model has been trained on UBFC-Phys dataset. 

## Model Architecture

The primary objective of our architecture is to learn the mapping to translate the spatial information in a RGB image to latent encoding corresponding to the pulse signals. The architecture is also required to learn features that account for noise factors like head movement and changes in lighting. This is achieved by incorporating a temporal shift convolution attention mechanism. 

For this purpose, the architecture uses two branches to learn facial and motion features with a spatial attention module. The first branch is used to learn the temporal motion information while the second branch learns the spatial facial information. One of the ways to learn the temporal motion information is with 3D convolutions. But, 3D convolution introduces high computation cost which makes it infeasible for real time computation and inference.

To this end, the architecture leverages Time Shift Attention based Convolution (TS-CAN) to remove the need for 3D convolution operations while still allowing for spatial-temporal modeling. TS-CAN has two main components: the temporal shift module (TSM) and an attention module. TSM splits the input data into three chunks and shifts the first and second chunks along the temporal axis, while the third chunk remains unchanged. This allows information to be exchanged among neighboring frames without adding any additional parameters to the network. The architecture uses TSM in the motion branch. The appearance branch takes in the mean applied input frame and applies Attention.

## Model training

1. Clone repo

```
https://github.com/Shashank-Holla/AimaNet.git
```

2. Move into AimaNet folder. Copy input and output file. File should be named as input_numpy.npy and output_numpy.npy


3. Run below command to start training.

```
python3 main.py --epochs 2 --batch_size 3 --train_split_index 132720
```


## Reference

This PyTorch based implementation is based on [MTTS-CAN](https://faangpath.com/template/) paper. This repository is based on the open source implementation available below-

https://github.com/xliucs/MTTS-CAN


