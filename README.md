# SDSEN: Self-Refining Deep Symmetry Enhanced Network for Rain Removal

![equi](https://github.com/prismformore/SDSEN/raw/master/imgs/equi.jpg)

This repo is an implementation of the SDSEN ([arXiv preprint](https://arxiv.org/pdf/1811.04761.pdf)).

Rain removal aims to extract and remove rain streaks from images. Although convolutional neural network (CNN) based methods have achieved impressive results in this field, they are not equivariant to object rotation, which decreases their generalization capacity for tilted rain streaks. In order to solve this problem, we propose Deep Symmetry Enhanced Network (DSEN). DSEN extracts rotationally equivariant features of rain streaks, and then generates rain layer for image restoration. Furthermore, an efficient selfrefining mechanism is designed to remove accumulated rain streaks more thoroughly. Experimental study verifies the validity of our method, with self-refining DSEN yielding the state-of-the-art performance on both synthetic and real-world rain image datasets.
![dsen](https://github.com/prismformore/SDSEN/raw/master/imgs/dsen_.jpg)
![sdsen](https://github.com/prismformore/SDSEN/raw/master/imgs/sdsen_.jpg)

## Prerequisite
- GrouPy ([Pytorch Implementation](https://github.com/adambielski/GrouPy))
- Python>=3.6
- Pytorch>=1.0.0
- Opencv>=3.1.0
- tensorboard-pytorch


## Project Structure
- config: contains all codes
    - cal_ssim.py
    - clean.sh
    - dataset.py
    - main.py
    - model.py
    - settings.py
    - show.py
    - tensorboard.sh
- explore.sh
- logdir: holds patches generated in training process
- models: holds checkpoints
- showdir: holds images predicted by the model


## Default Settings
Rain100H: [http://www.icst.pku.edu.cn/struct/Projects/joint_rain_removal.html]


We concatenate the two images(B and O) together as default inputs. If you want to change this setting, just modify config/dataset.py.
Moreover, there should be three folders 'train', 'val', 'test' in the dataset folder.
After download the datasets, don't forget to transform the format!

Both DSEN and SDSEN are provided in ```model.py```. On the new Rain100H test set (with 200 image pairs), SDSEN and DSEN achieve 0.8492 and 0.7511 respectively.


## Train, Test and Show
```
    python config/train.py
    python config/eval.py
    python config/show.py
```

## Scripts
- explore.sh: Show the predicted images in browser
- config/tensorboard.sh: Open the tensorboard server
- config/clean.sh: Clear all the training records in the folder


# Cite
Please kindly consider citing our paper:
```
@INPROCEEDINGS{sdsen_2018,
author={Liu, Hong and Ye, Hanrong and Li, Xia and Shi, Wei and Liu, Mengyuan and Sun, Qianru},
booktitle={2019 IEEE International Conference on Image Processing (ICIP)},
title={Self-Refining Deep Symmetry Enhanced Network for Rain Removal},
year={2019},
pages={2786-2790},
doi={10.1109/ICIP.2019.8803265},
```

# Contact:
Hanrong Ye leoyhr@pku.edu.cn

# Acknowledgement
This project is based on the [RESCAN](https://github.com/XiaLiPKU/RESCAN) by Xia Li. 
