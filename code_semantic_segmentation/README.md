# pytorch-LFE

This is a pytorch implementation of a in-reivew paper: LFME: A Simple Framework for Learning from Multiple Experts in Domain
Generalization. We use the data-spllit, pre-process, hyper-parameter settings, and evaluation protocals all from the 
previous art [arxiv](https://arxiv.org/abs/2204.03609)(https://github.com/Genie-Kim/PintheMemory). Our work is mainly at the **train.py** and **deepv3plus.py** files, please refer to them for details.

## Pytorch Implementation

### Installation Requirements
Please refer to [environment.yml](environment.yml)

### How to Run
We evaludated our method on [Cityscapes](https://www.cityscapes-dataset.com/), [Mapillary Vistas](https://www.mapillary.com/dataset/vistas?pKey=2ix3yvnjy9fwqdzwum3t9g&lat=20&lng=0&z=1.5), [BDD-100K](https://bair.berkeley.edu/blog/2018/05/30/bdd/) which is trained on [Synthia](https://synthia-dataset.net/downloads/) ([SYNTHIA-RAND-CITYSCAPES](http://synthia-dataset.net/download/808/)), [GTAV](https://download.visinf.tu-darmstadt.de/data/from_games/)

1. For Cityscapes dataset, download "leftImg8bit_trainvaltest.zip" and "gtFine_trainvaltest.zip" from https://www.cityscapes-dataset.com/downloads/<br>
```
cityscapes
 └ leftImg8bit_trainvaltest
   └ leftImg8bit
     └ train
     └ val
     └ test
 └ gtFine_trainvaltest
   └ gtFine
     └ train
     └ val
     └ test
```
```
bdd-100k
 └ images
   └ train
   └ val
   └ test
 └ labels
   └ train
   └ val
```
```
mapillary
 └ training
   └ images
   └ labels
 └ validation
   └ images
   └ labels
 └ test
   └ images
   └ labels
```

#### We used [GTAV_Split](https://download.visinf.tu-darmstadt.de/data/from_games/code/read_mapping.zip) to split GTAV dataset into training/validation/test set. Please refer the txt files.

```
GTAV
 └ images
   └ train
     └ folder
   └ valid
     └ folder
   └ test   
     └ folder
 └ labels
   └ train
     └ folder
   └ valid
     └ folder
   └ test   
     └ folder
```

#### We [Synthia dataset](http://synthia-dataset.net/download/808/) into train/val set. Please refer the txt files.

```
synthia
 └ RGB
   └ train
   └ val
 └ GT
   └ COLOR
     └ train
     └ val
   └ LABELS
     └ train
     └ val
```

2. You should modify the dataset path to "~/dg_seg_dataset/".
```
datasetroot = os.path.expanduser('~/dg_seg_dataset/')
```

### Train and Evaluation scripts
Please refer to the train and evaluation scripts in the code_semantic_segmentation/train(eval)_scripts folders.
#### Usage Examples
```
For training:  ./train_scripts/train_GS_lfe_DR50V3P.sh
For evluation: ./eval_scripts/eval_lfe_DR50V3P.sh
```
Then the qualitative result images saved in the same folder with pth snapshot file.

