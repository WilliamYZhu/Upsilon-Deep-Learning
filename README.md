# Upsilon-Deep-Learning

## Data Structure of BOLD 5000

**Stimuli Presentation List**

Using the first stimuli session for example, `CSI1/CSI1_sess01/CSI_sess01_run01.mat` represent the Matlab list of image names and their corresponding dataset (Coco or Imagenet). 

The  `CSI1/CSI1_sess01/CSI_sess01_run01.txt` includes the txt list of image names. This file would be used to find and download corresponding COCO images.

*Remark: In this project only COCO images are used since imagenet images could not be downloaded.*

**Using the COCO API**

The COCO dataset provides a `pycocotools` library which loads images and apply annotations from the image id. 