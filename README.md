# ARIN702001_Deep Learning assignment

## Basic Info
김동규/2023000903

All code was written and executed on Google Colab. 

## model
models: https://huggingface.co/AriannaHeartbell/AH_DL_assignment 

mirror: https://drive.google.com/drive/folders/1ROkorA_sqWzktwf6ycrvMp2FBSOOQhqA?usp=sharing

**Final version is d6, and ensemble test requires both d5(resnet18_cifar10_0.006000_5.pth) and d6(resnet18_cifar10_0.006000_6.pth)**

## Summary

Each model uses the model trained in the previous stage(e.g. d1 used d0 as a pretrained model) and altered with slight modifications to the hyperparameters in the current stage.
- b1: [baseline](https://github.com/heechul-knu/cifar-baseline): 95.80% **(Although reported as 97.05% on the leaderboard)**
- d0: lr=0.008, epoch=40, lr scheduler=cosine annealingLR, random erasing; random horizontal flip is not used
- d1: lr=0.007, epoch=20
- d2: momentum=0.6
- d3~d6: momentum=0.9, lr= 0.006
- final accuracy: 96.48%(d5+d6 ensemble) 

## Limitation
- Due to frequent disconnection, session closure, and process kill by Colab, I used limited multiprocessing during ensemble test(indicated by the 'num_workers' variable in the ensemble test code) or high model numbers for ensemble.
- As a result of the limited GPU usage time provided by Colab and disconnection issue, I am unable to run a high number of epochs continuously
- I utilized both Colab Plus and Colab Free due to the limited GPU usage time. As a result, the runtime environment may not have been consistent throughout the entire process.

## Google Colab (Plus) Runtime info 
- GPU Device: Tesla T4
- Operating System: Linux
- OS Release: 5.15.107+
- Python Version: 3.10.11
- Torch Version: 2.0.1+cu118
- Torchvision Version: 0.15.2+cu118
- Timm Version: 0.9.2
