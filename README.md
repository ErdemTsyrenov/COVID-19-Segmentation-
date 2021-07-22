# COVID-19-Segmentation-
This is my coursework of 3 course. In this project we train artificial neural network to segment CT images into 4 classes: background, right lung, left lung, COVID-19 infection. Our main goal is COVID-19 segmentation. However in real life we have few marked data but there are a lot of data with another masks for example with lung mask. Therefore in this project we considered semisupervised learning task.
## Dataset
We used dataset from this link https://zenodo.org/record/3757476#.YPktg5Mzbeo. It has 20 CT images with .nii.gz extension. Each CT has 3 different masks: both lung and infection masks, lung only masks and infection only masks. We used 15 CT images as training data and 5 as validation data. Then we pretended that we have few marked data and used only 5 CT images with both masks, 5 images with infection only masks and other 10 images with lung only masks. Using such separation we model real situation. 
## Neural network architecture
In this project we used 2 different architectures: U-Net and DeepLabV3. Both networks show approximately the same result.
## Loss function and metrics
As a loss function we used average between weighted Cross Entropy loss and weighted Dice loss. For each class we assigned weight. If image has markup of the class, weight of this class is 1 else weight is 0. Such approach allows us not to use incorrect loss values. In the end quality of model was estimated using Dice Coefficient.
## Results
The best dice coefficient for each class was
 - background: 0.998
 - left lung:  0.921
 - right lung: 0.932
 - infection:  0.815
