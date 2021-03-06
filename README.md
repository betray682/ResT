# ResT
By Qing-Long Zhang and Yu-Bin Yang

[State Key Laboratory for Novel Software Technology at Nanjing University]

This repo is the official implementation of ["ResT: An Efficient Transformer for Visual Recognition"](https://arxiv.org/pdf/2105.13677v3.pdf). It currently includes code and models for the following tasks:
> **Image Classification**: Included in this repo. See [get_started.md](get_started.md) for a quick start.

> **Object Detection and Instance Segmentation**: Based on [detectron2](https://github.com/facebookresearch/detectron2).

**ResT** is initially described in [arxiv](https://arxiv.org/pdf/2105.13677v3.pdf), which capably serves as a
general-purpose backbone for computer vision. It can tackle input images with arbitrary size. Besides, 
ResT compressed the memory of standard MSA and model the interaction between multi-heads while keeping 
the diversity ability. 


## Main Results on ImageNet with Pretrained Models

**ImageNet-1K Pretrained Models**

| name | resolution |acc@1 | acc@5 | #params | FLOPs | FPS| 1K model |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |:---: |
| ResT-Lite  | 224x224 | 77.2 | 93.7 | 10.5M | 1.4G | 1246 | [baidu](https://pan.baidu.com/s/1PSqwEvwfdqSGB4tlL9kFRg)
| ResT-Small | 224x224 | 79.6 | 94.9 | 13.7M | 1.9G | 1043 | [baidu](https://pan.baidu.com/s/1lx33vDMdPyw4U9sgaKvv4g)
| ResT-Base  | 224x224 | 81.6 | 95.7 | 30.3M | 4.3G | 673  | [baidu](https://pan.baidu.com/s/1sSi7r83ujb146WhU8F-wGw)
| ResT-Large | 224x224 | 83.6 | 96.3 | 51.6M | 7.9G | 429 | [baidu](https://pan.baidu.com/s/1lVStrppan4nbAqCEuNvRDg)

Note: access code for `baidu` is `rest`. pretrained models for [google drive](https://drive.google.com/drive/folders/1H6QUZsKYbU6LECtxzGHKqEeGbx1E8uQ9).

## Main Results on Downstream Tasks

**COCO Object Detection (2017 val)**

Attention: The results of downstream tasks are very sensitive to the training settings, a fluctuation of 1.0 is OK!

| Backbone | Method | pretrain | Lr Schd | box mAP | mask mAP | #params | model |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ResT-Small | RetinaNet | ImageNet-1K | 1x | 40.3 | - | 23.4M | [baidu](https://pan.baidu.com/s/1Yi1pBN953YWSyzLmYssEWQ) |
| ResT-Base | RetinaNet | ImageNet-1K | 1x | 42.0| - | 40.5M | [baidu](https://pan.baidu.com/s/10yGl7qwKWdvrNr4YLxdsHw) |
| ResT-Small | Mask R-CNN | ImageNet-1K | 1x | 39.6 | 37.2 | 33.3M | [baidu](https://pan.baidu.com/s/10IdRvoG1pOPBtzKjsUHOSw) |
| ResT-Base | Mask R-CNN | ImageNet-1K |  1x | 41.6 | 38.7 | 49.8M | [baidu](https://pan.baidu.com/s/1dohuRUhfAaG72KvXd8NwYw) |

Note: This is the results with LN (Comparison is shown in the Appendix part). 
For training with rest backbones, you need to convert the original pre-trained weights to d2 format by [convert_to_d2.py](d2/convert_to_d2.py). Access code for `baidu` is `rest`.

## Citing ResT

```
@article{zhql2021ResT,
  title={ResT: An Efficient Transformer for Visual Recognition},
  author={Zhang, Qinglong and Yang, Yubin},
  journal={arXiv preprint arXiv:2105.13677v3},
  year={2021}
}
```