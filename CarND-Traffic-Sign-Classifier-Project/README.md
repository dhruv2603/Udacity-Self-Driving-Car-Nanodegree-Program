## Project: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---
In this project, a Convolutional Neural Network (CNN) based on the LeNet architecture is used to classify German traffic signs. The model is trained on the
[German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset) dataset and is also tested on real-world images sourced from the web. This project is part of the Udacity Self-Driving Car Nanodegree program.

Project Pipeline
---
The major steps followed in this project are:
* Load and explore the dataset
* Split the dataset into training, validation and test sets
* Visualize the dataset to understand the class distribution
* Preprocess the images (convert to grayscale and normalize pixel values to \[-1,1\])
* Define and implement a LeNet-style CNN from scratch using Tensorflow
* Train and evaluate the model
* Test the model on new, unseen traffic sign images from the web
* Analyze the top-5 softmax probabilities for these predictions

Results
---
 Metric                      | Accuracy |
|-----------------------------|----------|
| **Training Accuracy**       | 100%     |
| **Validation Accuracy**     | 98.85%   |
| **Test Accuracy (GTSRB)**   | 89.5%    |
| **Web Image Accuracy**      | 40%      |

The model demonstrates excellent performance on the training and validation datasets. However, performance drops significantly on traffic signs collected from the web due to differences in lighting, angles, and image quality.

> 📌 **Note:** Adding data augmentation and domain adaptation techniques could help improve generalization on real-world images.

Key Insights
---
- **Weight Initialization Matters**: Initially, using `tf.random.normal` for weight initialization resulted in poor training performance, with the model getting stuck in local minima. Switching to He initialization (`tf.keras.initializers.HeNormal`) led to significantly better results.
- **Softmax for Interpretability**: Even though the model outputs raw logits, applying softmax post-inference provided useful confidence scores for the top predictions.

### Dependencies

Ensure you have the [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit) installed. It includes:

- TensorFlow  
- NumPy  
- Matplotlib  
- Pandas  
- OpenCV  

### Dataset and Repository

1. Download the data set from [here](https://d17h27t6h515a5.cloudfront.net/topher/2016/November/581faac4_traffic-signs-data/traffic-signs-data.zip). The classroom has a link to the data set in the "Project Instructions" content. This is a pickled dataset in which we've already resized the images to 32x32. It contains a training, validation and test set.
2. Clone the project, which contains the Ipython notebook and the writeup template.
```sh
git clone https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project
cd CarND-Traffic-Sign-Classifier-Project
jupyter notebook Traffic_Sign_Classifier.ipynb
```
