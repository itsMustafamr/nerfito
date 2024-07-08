# NeRF-ito
A tiny implementation of NeRF
you can find the code [here](https://github.com/nerfstudio-project/nerfstudio)

commands i learnt
ctrl + b (in vs code) - side bar

code . -> when executed will open the current directory in vscode

## Dependencies
what framework should we use for this project.

- Pytorch
- TensorFlow
- Jax

According to papers we go with pytorch

Save dependencies in a file:
pip3 freeze --local > requirements.txt


## Archetecture 
2 state of the arc implementations of nerfs
[instant-gp](https://github.com/NVlabs/instant-ngp) 
[nerfstudio](https://github.com/nerfstudio-project/nerfstudio) - open source 

the main components of nerf implementation are:
- volume of spaces that is voxelized
- camera position and orientation
- Calcualte the ray for each pixel
- calulating the color and opacity at a point on each ray

(ray is the red line in the paper of nerf and in goes through the image and it is going to traverse the volume of space)
(so we are going to sample along that ray on various points and for each of that points we are going to have a neural net that predicts the opacity and color)

- Neural network to predict color and opacity
So the inputs - render the image from the camera positon.
we are going to have a - loss function for the renderred image and gound truth image.
we are going to need a - dataset loader for training and testing the image.
We are gonna need a - dataset of images and camera positions.
we need - Training and/or testing loops
then we need - evaluation code

Neural network 
- Inputs: ray direction, ray origin
- Outputs: color, opacity