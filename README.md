# MCANet_CVPR2020
Implementation of Multi Co-Attention Network(MCANet) to solve Object Co-segmentation.

### Table of Contents
- <a href='#Installation'>Installation</a>
- <a href='#Datasets'>Datasets</a>
- <a href='#Model'>Model</a>
- <a href='#Demos'>Demos</a>
- <a href='#Evaluation'>Evaluation</a>
- <a href='#Performance'>Performance</a>
&nbsp;
&nbsp;
## Installation
- Clone this repository.
- Python 2.7
- [PyTorch](http://pytorch.org/) 0.4.1 
- Packages: `numpy`,`opencv-python`,`matplotlib`,`glob`
- Datasets: follow the [instructions](#Datasets) below
## Datasets
Four OCS benchmark datasets are used for evaluating the performance of our proposed MACNet.

### VOC10
Collected by Faktor and Irani([paper](https://www.cv-foundation.org/openaccess/content_iccv_2013/papers/Faktor_Co-segmentation_by_Composition_2013_ICCV_paper.pdf)), this dataset contains 1,037 images of 20 object classes, and it is the most challenging dataset in the experiment due to extreme intra-class variability, subtle foreground/background discrimination, and class imbalance. [Download Link](https://drive.google.com/open?id=1V7YRZafySYOPtZ4WiwqM6pUnjc_8TAH7).
### Internet
Introduced by [paper](http://people.csail.mit.edu/mrub/ObjectDiscovery/), this dataset encloses images with three common object classes. This dataset raises the particular challenge of noisy outliers, such that images with no common object exist in the dataset. [Download Link](http://people.csail.mit.edu/mrub/ObjectDiscovery/ObjectDiscovery-data.zip).
### MSRC
This dataset encompasses 14 image groups with 410 images, each group contains common objects drawn from the same class. [Download Link](http://people.csail.mit.edu/mrub/ObjectDiscovery/ObjectDiscovery-data.zip).
### iCoseg
There are 38 categories in [iCoseg dataset](https://www.cc.gatech.edu/~dbatra/papers/bkpcl_cvpr10.pdf) with totally 643 images. Each category composes images containing foreground with limited intra-class variability. [Download Link](http://people.csail.mit.edu/mrub/ObjectDiscovery/ObjectDiscovery-data.zip).

## Model
   
- [Implementation](https://github.com/blankblankblank123/MCANet_CVPR2020_submit/tree/master/libs/models)
- the codes of resnet101 and ASPP layer are copied from [this work](https://github.com/kazuto1011/deeplab-pytorch)
- download pretrained MCANet weights at [here](https://drive.google.com/open?id=1tyM2tJ_LhfCmI3rsliciLidfHk5ploKc)

<img align="left" src= "https://github.com/blankblankblank123/MCANet_CVPR2020_submit/blob/master/doc/model.PNG">

## Demos
```
Usage: python demo.py
```
Input with multi-classes [demo images](https://github.com/blankblankblank123/MCANet_CVPR2020_submit/tree/master/demo_images), output with grouped images. The result visualization can be seen [here](https://github.com/blankblankblank123/MCANet_CVPR2020_submit/tree/master/result/demo).

group 1:
<img align="left" src= "https://github.com/blankblankblank123/MCANet_CVPR2020_submit/blob/master/result/demo/0.png">

group 2:
<img align="left" src= "https://github.com/blankblankblank123/MCANet_CVPR2020_submit/blob/master/result/demo/1.png">

group 3:
<img align="left" src= "https://github.com/blankblankblank123/MCANet_CVPR2020_submit/blob/master/result/demo/2.png">

## Evaluation
Metric:
- Jaccard
- Precision

```
Usage: python eval_vis_voc_group.py | eval_vis_internet_group.py | eval_vis_msrc_group.py
```

## Performance
- average
<table>
    <tr>
        <th>Dataset</th>
        <td colspan="2">VOC10</td>
        <td colspan="2">Internet</td>
        <td colspan="2">MSRC</td>
    </tr>
    <tr>
        <th> Metric</th>
        <th>P</th>
        <th>J</th>
        <th>P</th>
        <th>J</th>
        <th>P</th>
        <th>J</th>
    </tr>
    <tr>
        <th> MCANet</th>
        <th>93.5</th>
        <th>63.7</th>
        <th>94.2</th>
        <th>74.8</th>
        <th>90.1</th>
        <th>73.5</th>
    </tr>
   
</table>

-voc10
<table>
    <tr>
        <th> Class</th>
        <th>A.P.</th>
        <th>Bike.</th>
        <th>Bird</th>
        <th>Boat</th>
        <th>Bottle</th>
        <th>Bus.</th>
        <th>Car</th>
        <th>Cat</th>
        <th>Chair</th>
        <th>Cow</th>
        <th>D.T.</th>
        <th>Dog</th>
        <th>Horse</th>
        <th>M.B.</th>
        <th>P.S.</th>
        <th>P.P.</th>
        <th>Sheep</th>
        <th>Sofa</th>
        <th>Train</th>
        <th>TV</th>
    </tr>
    <tr>
        <th> Metric</th>
        <th>P</th>
        <th>J</th>
        <th>P</th>
        <th>J</th>
        <th>P</th>
        <th>J</th>
    </tr>
    <tr>
        <th> MCANet</th>
        <th>93.5</th>
        <th>63.7</th>
        <th>94.2</th>
        <th>74.8</th>
        <th>90.1</th>
        <th>73.5</th>
    </tr>
   
</table>
