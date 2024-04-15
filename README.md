# COVID19_detection_using_Deep_Learning
This repository detects covid19 from Chest X-RAY images.
Please go to References  -> Block Diagram Covid Detection.pdf to see the rough block diagram
#
The training set is used to train the model; the test set evaluates its performance on unseen data; and the validation set aids in model selection and hyperparameter tuning.
#
Currently, our entire dataset is very small as we had to run the entire setup on free version of Colab. We have used the very best combination of CNN models from Keras. To achieve higher accuracy on test dataset, please use image augmentation to increase the size of the dataset. Also, this is the most comprehensive covid 19 detection using Deep Learning till date achieving a very good accuracy and other metrics even on such a small dataset.
# Preprocessing of chest X Rays
For pre-processing of chest x rays, we have used the state-of the art model i.e. Scene-Text Removal EraseNet. The pre-trained model of EraseNet and other scene-text removal methods can be found at https://github.com/naver/garnet.
# Ensemble of CNN 
4 very best CNN models from Keras have been used.
1. DenseNet121
2. VGG19
3. MobileNet
4. Xception
All weights are initialized from ImageNet dataset.
Finally, the CNN models are ensembled with weights given corresponding to the validation accuracies from the 4 models.
