# MixMatch meets Transfer Learning

This script combines the Semi-Supervised-Learning method MixMatch with transfer learning to fine-tune a pre-trained [Efficient-Net](https://github.com/lukemelas/EfficientNet-PyTorch) model on a chest x-ray images dataset.

The MixMatch implementation is adapted from [here](https://github.com/YU1ut/MixMatch-pytorch).

The MixMatch method was proposed by the Google Research team, details here: [MixMatch: A Holistic Approach to Semi-Supervised Learning](https://arxiv.org/abs/1905.02249). 
The official Tensorflow implementation is [here](https://github.com/google-research/mixmatch).

Currently, the script only contains the [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) as well as a [chest x-ray images dataset](https://www.kaggle.com/nih-chest-xrays/sample).


## Requirements
- Python 3.6+
- PyTorch 1.0
- **torchvision 0.2.2 (older versions are not compatible with this code)** 
- tensorboardX
- progress
- matplotlib
- numpy
- efficientnet_pytorch

## Usage

### Train
Train the EfficientNet model by 250 labeled data of the x-ray dataset:

```
python train.py --lr 0.0001 --batch-size 16 --unfreeze 5 --dataset x_ray --n-labeled 250 --out cifar10@250 --model efficient
```



Train the ResNet model by 4000 labeled data of CIFAR-10 dataset:

```
python train.py --lr 0.002 --batch-size 64 --dataset cifar --n-labeled 4000 --out cifar10@4000 --model resnet
```


## References
```
@article{berthelot2019mixmatch,
  title={MixMatch: A Holistic Approach to Semi-Supervised Learning},
  author={Berthelot, David and Carlini, Nicholas and Goodfellow, Ian and Papernot, Nicolas and Oliver, Avital and Raffel, Colin},
  journal={arXiv preprint arXiv:1905.02249},
  year={2019}
}
```
