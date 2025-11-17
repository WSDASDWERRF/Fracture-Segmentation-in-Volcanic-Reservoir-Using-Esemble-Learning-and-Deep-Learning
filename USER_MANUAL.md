## Overview

## Software
The software Imagej and Dragonfly can be downloaded from folder software installation package.

## Data augmentation
The data for training contains 9 952*881 images, which can be used for training the random forest model. Cause of the difference in feature labeling, you can get different results in training.
And my random forest model would be downloaded from folder trained model.
Then, the segmented 9 images would be put into training the U-Net++ model. For the same reason, you can use your own model for getting the final micro-feature segmentation, or use my U-Net++ model.
And my U-Net++ model would be downloaded from folder trained model.

## Model
The models of random forest, 2.5D U-Net++ would be founded from folder trained model. On the same time, you can see other models, like Link-Net, I-Net in the same folder.
One thing needs to be emphasizing, * means that the model was trained after using random forest model. Random forest model would be used in software Imagej, and other model should be used in Dragonfly.

## Training
All models are trained after “label-as-you-train” strategy. 
Hence, in random forest model, you can choose three of the samples to train your own model. And my model was trained for three times, by the first three images. 
In other deep-learning models, all models was trained for 5 epochs.

## Application
You can find codes from floder code to automatedly apply the random forest model for every image.
And other models would be applied in software Dragonfly.

## How to use

**Random forest model
Download software Imagej and the data 9 952*881 images.
Import one of the image into Imagej, use module "B&C" or "Enhance Contrast" and change "saturated" into 0.35.
Then, use module"Freehand", select ROI area for further labeling. 
Use module"Advanced Weka Segmentation", label the feature area and then train random forest model.
See the trained model and then, label more fractures and other areas for better training.
Stop training and import your own model.
Choose one another image, repeat the process above, while in this time, you can firstly apply the former model into segmentation and then, label and train the new model.
Finally, you can use my code to automatedly apply the random forest model for every image.

**2.5D U-Net++ model
Download software Dragonfly and prepare the data 9 segmented images from the random forest model.
Import all images into Dragonfly and use module "Segmentation Wizard" from menu "Artificial Intelligence".
Choose one image, select ROI (make sure that the ROI area in every image you would label would be same) and label the feature area ( pores:first class, fractures:second class, air:third class).
Choose one another image, repeat the process above.
After labeling all 9 images, you can add the 2.5D U-Net++ model in module "Models", and set 2.5D input configuration, a five-level encoder–decoder depth, a batch size of 8, and the Adadelta optimizer for training in 5 epochs.
When training the model, you can see the loss and accuracy curves and get the estimated time for every epoch.
Stop training, you can apply the model and see the segmentation result, if you don't satisfy with the result, you can label and train the model again.
Finally, import your 2.5D U-Net++ model and apply it for the 3D grayscale volume by module "Deep Learning Tools" from menu "Artificial Intelligence".

**Other models for comparsion
Differen from 2.5D models, you should just label one image for training. Other steps are same with the 2.5D U-Net++ model training. You can choose your loved model for training.
In this study, I trained the other four models: I-Net, Trans-Unet, Unet and Link-Net. You can apply those models for the segmentation comparsion.

**Random forest model for comparsion
You can put raw images into Dragonfly to repeat processes above and compare the segmentation results.
The differences would be pronounced founded in labeling and training.
