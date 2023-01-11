# Satellite Imagery segmentation for Built Structure Analysis

## Data


- The Data use in the project is used provided by the Ordinance Survey Ireland (OSI) which can be found [here](https://drive.google.com/drive/folders/14sBkjeYY7R1S9NzWI5fGLX8XTuc8puHy).


- The directory structure to be followed for the code is:\
`Data`\
|\
|____ `Train`\
|&emsp;&emsp;&emsp;&emsp;|\
|&emsp;&emsp;&emsp;&emsp;|______Image\
|&emsp;&emsp;&emsp;&emsp;|\
|&emsp;&emsp;&emsp;&emsp;|______Mask\
|\
| _____`Test`\
&emsp;&emsp;&emsp;&emsp;|\
&emsp;&emsp;&emsp;&emsp;|______Image\
&emsp;&emsp;&emsp;&emsp;|\
&emsp;&emsp;&emsp;&emsp;|______Mask


## Data Preprocessing
- The Data from the OSI are the DSMs, corresponding to satellite Imagery, with values between 0 and 255.
- The grey scale values are thresholded into 10 classes corresponding to the pixel values: `10, 30, 50, 70, 90, 115, 135, 165, 195, 210`.
- The distribution of the pixel values is done on an uneven scale considering the fact that major data in th DSMs contain the pixel values between 0 and 120, hence the class distribution based on class values is also uneven.
- Then the resulting threholded images are placed in the `Mask` folder of both training and tests folders. 

## Model

- The architecture used in the project is the DeepLabV3 explained in [Rethinking Atrous convolution for semantic image segmentation](https://arxiv.org/abs/1706.05587).


## Results

- The evaluation metrics are as follows\
<space> `Training Dice loss: 0.09218`\
`Training IoU Score: 0.8353`\
`Test Dice loss: 0.1482`\
`Test IoU Score: 0.7517`



    <img src="results/1.png" alt="Result 1" style="height: 150px;width:450px;"/>\
    <img src="results/2.png" alt="Result 2" style="height: 150px;width:450px;"/>\
    <img src="results/3.png" alt="Result 3" style="height: 150px;width:450px;"/>
