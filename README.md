# 6DGS
## [Project page](https://mbortolon97.github.io/6dgs/) |  [Paper]([https://arxiv.org/](https://arxiv.org/abs/2407.15484v1))
This repository contains a PyTorch implementation for the paper: [6DGS: 6D Pose Estimation from a Single Image and a 3D Gaussian Splatting Model](https://arxiv.org/).

## Installation

#### Tested on Ubuntu 22.04 + Pytorch 1.10.1 

Install environment:
```
conda env create --file environment.yml
conda activate gaussian_splatting
```


## Quick start
### Training the base 3DGS model
The training script is in `train.py`, to train a 3DGS:

```
python train.py -s [dataset location]
```

We provide two scripts that it is necessary only to edit with the correct paths to the dataset:
```
sh tools/launch_all_mip_training.sh
sh tools/launch_all_tanks_and_temple_training.sh
```

### Run the pose estimation
The training and testing script for the pose estimation is located in `pretrain_eval_attention.py`, for training and testing on all the objects from Mip-NeRF 360:

```
python3 pretrain_eval_attention.py --exp_path ../pose-splatting/output/ --out_path results.json --data_type mip360
```

For the Tanks Temple objects
```
python3 pretrain_eval_attention.py --exp_path ../pose-splatting/output/ --out_path results.json --data_type tankstemple
```



## Citation
If you find our code or paper helps, please consider citing:
```
@INPROCEEDINGS{Bortolon20246dgs,
  author = {Bortolon, Matteo and Tsesmelis, Theodore and James, Stuart and Poiesi, Fabio and Del Bue, Alessio},
  title = {6DGS: 6D Pose Estimation from a Single Image and a 3D Gaussian Splatting Model},
  booktitle = {ECCV},
  year = {2024}
}
```
