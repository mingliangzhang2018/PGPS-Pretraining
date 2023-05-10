# PGPS-Pretraining
The Structural and Semantic Pre-training Language Model of [PGPSNet](https://github.com/mingliangzhang2018/PGPS)

<div align=center>
	<img width="800" src="images\Pre-training.png">
</div>
<div align=center>
	Figure 1. Pipeline of structural and semantic pre-training.
</div>

## Environmental Settings

They are the same as [PGPSNet](https://github.com/mingliangzhang2018/PGPS)

## PGPS9K Dataset

You could download the dataset from [Dataset Homepage](http://www.nlpr.ia.ac.cn/databases/CASIA-PGPS9K).

In default, unzip the dataset file to the fold `./datasets`.

## Training

The default parameter configurations are set in the config files `./config/config_default.py` and the 
default training modes are displayed in `./sh_files/train.sh`, for example,

```
CUDA_VISIBLE_DEVICES=0 python -m torch.distributed.launch \
--nproc_per_node=1 \
--master_port=$((RANDOM + 10000)) \
start.py
```
The training records of pre-training are saved in the folder `./log`. In default, we choose the model of last epoch as the pre-trained language model.   