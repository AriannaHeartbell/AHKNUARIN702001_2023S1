# ARIN702001_Deep Learning assignment

## Basic Info
김동규/2023000903

All code was written and executed on Google Colab. 

## Summary
Each model uses the model trained in the previous stage(eg.d1 used d0 as a pretrained model) and makes slight modifications to the hyperparameters in the current stage.
- b1: [baseline](https://github.com/heechul-knu/cifar-baseline): 95.80%
- d0: lr=0.008, epoch=40, lr scheduler=cosine annealingLR, random erasing; random horizontal flip is not used
- d1: lr=0.007, epoch=20
- d2: momentum=0.6
- d3~d6: momentum=0.9, lr= 0.006: 96.48%(d6) 

## Colab Running Environment
- GPU Device: Tesla T4
- Operating System: Linux
- OS Release: 5.15.107+
- Python Version: 3.10.11
- Torch Version: 2.0.1+cu118
- Torchvision Version: 0.15.2+cu118
- Timm Version: 0.9.2
