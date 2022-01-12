# 2021-VRDL_HW3
Visual Recognition using Deep Learning HW3

##  Hardware

The following specs were used to create the original solution.

* Ubuntu 18.04.4 LTS
* NVIDIA® GeForce RTX™ 3090

## Reproducing Submission

*   [Download Models](#Download-Models)
*   [Make Submission](#Make-Submission)

## Requirements

```Requirements
# python version: Python 3.8
skimage
imageio
Pytorch (Pytorch version >=0.4.1 is recommended)
tqdm
pandas
cv2 (pip install opencv-python)
Matlab
```

## Dataset Preparation
You can download the data on the google drive：https://drive.google.com/file/d/1GL_Rh1N-WjrvF_-YOKOyvq0zrV6TF4hb/view

Data
```data
  +- dataset
    +- training_hr_images
       +- 2092.png
       +- 8049.png
       ...
    +- testing_lr_images
       +- 01.png
       +- 02.png
       ...
```

## Data Preprocessing
You can run to get HR/LR pairs by following, and change your path.
Or you can download my dataset to train:https://drive.google.com/file/d/13bXhfAQVsX6w35otfY0Qs95teEBY9TbU/view?usp=sharing

```Data Preprocessing
$ Run ./scripts/Prepare_TrainData_HR_LR.m in Matlab to generate HR/LR training pairs with corresponding degradation model and scale factor.
$ Run ./results/Prepare_TestData_HR_LR.m in Matlab to generate HR/LR test images with corresponding degradation model and scale factor, and choose one of SR benchmark for evaluation during training.
```

## Training
You can train the data by following:

```train
$ python train.py -opt options/train/train_SRFBN_example.json
```

## Download Models

You can download my models here:

- https://drive.google.com/file/d/1f4krEH5t60qOrmnRHQLRE77qpT0KeYRR/view?usp=sharing

## Make Submission

You need to download models, and put them at ./experiments/SRFBN_in3f128_x3/epochs/ folder or change your path.
You can get the predict result by following:

```test
$ python test.py -opt options/test/test_SRFBN_example.json
```

## Reference

- https://github.com/Paper99/SRFBN_CVPR19https://github.com/Paper99/SRFBN_CVPR19
