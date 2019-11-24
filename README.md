# Upsilon-Deep-Learning

## List of required dataset downloads

* README.txt
* BOLD5000_Stimuli.zip
* BOLD5000_ROIs.zip

## Data Structure of BOLD 5000

**Stimuli Presentation List**

Using the first stimuli session for example, `CSI1/CSI1_sess01/CSI_sess01_run01.mat` represent the Matlab list of image names and their corresponding dataset (Coco or Imagenet). 

The  `CSI1/CSI1_sess01/CSI_sess01_run01.txt` includes the txt list of image names. This file would be used to find and download corresponding COCO images.

*Remark: In this project only COCO images are used since imagenet images could not be downloaded.*

**ROIs**

- CSIX_ROIs_TRY.h5 or .mat contains processed ROIs voxels. ROIs provided are 'LHEarlyVis', 'RHEarlyVis', 'LHLOC', 'RHLOC', 'LHPPA', 'RHPPA', 'LHRSC', 'RHRSC', 'LHOPA', 'RHOPA’. Each ROI voxels come in matrix form. The matrix shape is # of images x # of dimensions for that ROI. 

Note that for CSI1, 2, 3 the # of images viewed is 5254. For CSI4 the # of images viewed is 3108
example:

For CSI1 ‘LHPPA’
Matrix is of shape `5254 x 157`

The ordering of images are provided in stim_list folder. CSIX_stim_lists.txt provided the 5254 ordering of image names.

## Using the COCO API

The COCO dataset provides a `pycocotools` library which loads images and apply annotations from the image id. 

Annotation structure:

```python
img_ids: All image ids included in coco_final_annotations.pkl
File Structure of data: 
{
    id: {
        'annotations': [
            {
                'segmentation': [[
                    coordinates, ...
                ]],
                'area': area of segment,
                'iscrowd': bool (0 or 1) is a number of objects highlighted,
                'image_id': id of the image,
                'bbox': [x, y, width, height],
                'category_id': id of image category,
                'id': id of image
            }
        ], ...
    }
}
```
