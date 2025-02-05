# Running on your own dataset
1) We used `pytorch/pytorch:0.4.1-cuda9-cudnn7-devel` docker. Directory with input images is mounted as `/dataset`, results will be saved in `/output`, directory with code is mounted as `/SOF-VSR`.
2) Enter directory `/SOF-VSR`. See `SOF-VSR.sh` script for installation commands and running example.

# SOF-VSR (Super-resolving Optical Flow for Video Super-Resolution)
Pytorch implementation of our ACCV 2018 paper ***"Learning for Video Super-Resolution through HR Optical Flow Estimation"*** and TIP 2020 paper ***"Deep Video Super-Resolution using HR Optical Flow Estimation"***.


[[ACCV]](http://arxiv.org/abs/1809.08573) [[TIP]](http://arxiv.org/abs/2001.02129)


## Overview
![overview](./Figs/overview.png)

Figure 1. Overview of our SOF-VSR network.

<img width="500" src="https://github.com/LongguangWang/SOF-VSR/blob/master/Figs/temporal_profiles.png"/></div>

Figure 2. Comparison with the state-of-the-arts.

## Requirements
- Python 3
- pytorch (0.4), torchvision (0.2)
- numpy, PIL
- Matlab (For PSNR/SSIM evaluation)

## Datasets
We collect 145 1080P video clips from [the CDVL Database](http://www.cdvl.org) for training.

We use the Vid4 dataset and a subset of the DAVIS dataset (namely, DAVIS-10) for benchmark test.
- Vid4([BaiduPan](https://pan.baidu.com/s/1q947P3mvPaOjTZ5f1kXoTg), [GoogleDrive](https://drive.google.com/file/d/1ayb41qjur19Qq04kQewMHE5U2t-Sbwdw/view?usp=sharing))
- [DAVIS-10](https://davischallenge.org/)  
We use 10 scenes in the DAVIS-2017 test set including boxing, demolition, dive-in, dog-control, dolphins, kart-turn, ocean-birds, pole-vault, speed-skating and wings-trun.

## Train & Test
[[ACCV]](./ACCV/README.md)

[[TIP]](./TIP/README.md)

## Results
![Vid4](./Figs/results_Vid4.png)

Figure 3. Comparative results achieved on the Vid4 dataset. Zoom-in regions from left to right: **IDNnet**, **VSRnet**, **TDVSR**, our **SOF-VSR**, **DRVSR** and our **SOF-VSR-BD**. 

![DAVIS-10](./Figs/results_DAVIS.png)

Figure 4. Comparative results achieved on the DAVIS-10 dataset. Zoom-in regions from left to right: **IDNnet**, **VSRnet**, our **SOF-VSR**, **DRVSR** and our **SOF-VSR-BD**. 

![temporal_profiles](./Figs/temporal_profiles.gif)

Figure 5. Visual comparison of 4x SR results. From left to right: **VSRnet**, **TDVSR**, our **SOF-VSR** and the **groundtruth**.

## Citation
```
@InProceedings{Wang2018accv,
  author    = {Longguang Wang and Yulan Guo and Zaiping Lin and Xinpu Deng and Wei An},
  title     = {Learning for Video Super-Resolution through {HR} Optical Flow Estimation},
  booktitle = {ACCV},
  year      = {2018},
}
@Article{Wang2020tip,
  author    = {Longguang Wang and Yulan Guo and Li Liu and Zaiping Lin and Xinpu Deng and Wei An},
  title     = {Deep Video Super-Resolution using {HR} Optical Flow Estimation},
  journal   = {{IEEE} Transactions on Image Processing},
  year      = {2020},
}
```
## Contact
For questions, please send an email to wanglongguang15@nudt.edu.cn
