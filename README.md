# COVID19_detection_using_Deep_Learning
This repository detects covid19 from Chest X-RAY images and classifies it into a COVID patient, pneumonia or healty patient.

# DataSet
The training set is used to train the model; the test set evaluates its performance on unseen data; and the validation set aids in model selection and hyperparameter tuning. The COVID19 Radiography Dataset is used here which can be found at https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database. 
#
From this dataset, we have taken 2700 training images, 900 from each of the category(i.e 75%), 360 validation images ,i.e 120 from each of the category(10 %) and 540 testing images i.e 180 from each category (15 %).So, in total we are using 3600 images. The entire dataset can be found in dataset folder.Note all images are preprocessed with CLAHE + EraseNet + Keras-OCR,so you need not do any preprocessing further.
#
Currently, our entire dataset is very small as we had to run the entire setup on free version of Colab. We have used the very best combination of CNN models from Keras. To achieve higher accuracy on test dataset, please use image augmentation to increase the size of the dataset. Also, this is the most comprehensive covid 19 detection using Deep Learning till date achieving a very good accuracy and other metrics even on such a small dataset.
# Preprocessing of chest X Rays
For pre-processing of chest x rays, we have used the state-of the art model i.e. Scene-Text Removal EraseNet. The pre-trained model of EraseNet and other scene-text removal methods can be found at https://github.com/naver/garnet. Also, we have used inbuilt keras-ocr .Both EraseNet and Keras-OCR helped in removing text from x ray images to a certain amount. Then we used CLAHE to increase local contrast of the x-rays and enhance details of local regions.
# Ensemble of CNN 
4 very best CNN models from Keras have been used.
1. DenseNet121
2. VGG19
3. MobileNet
4. ResNet50V2

All weights are initialized from ImageNet dataset.
Finally, the CNN models are ensembled with weights chosen corresponding to the validation accuracies from the 4 models.
## Pre-Trained Models 
The pretrained models can be found in the pre-trained models folder.
## References

```bibtex
@inproceedings{lee2022surprisingly,
  title={The Surprisingly Straightforward Scene Text Removal Method with Gated Attention and Region of author={Lee, Hyeonsu and Choi, Chankyu},
  booktitle={European Conference on Computer Vision},
  pages={457--472},
  year={2022},
  organization={Springer}
}
@ARTICLE{Erase2020Liu,
  author     ={Liu, Chongyu and Liu, Yuliang and Jin, lianwen and Zhang, Shuaitao and Luo, Canjie and Wang, Yongpan},
  journal    ={IEEE Transactions on Image Processing},
  title      ={EraseNet: End-to-End Text Removal in the Wild},
  year       ={2020},
  volume     ={29},
  pages      ={8760-8775},}

@article{zhang2019EnsNet,
    title     = {EnsNet: Ensconce Text in the Wild},
    author    = {Shuaitao Zhang∗, Yuliang Liu∗, Lianwen Jin†, Yaoxiong Huang, Songxuan Lai
    joural    = {AAAI}
    year      = {2019}
  }

