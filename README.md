CNN-Convolutional Neural Network Image Clasification System

This machine learning project is an image classification system that is built using Keras and Tensorflow to distinguish recyclable and organic waste images. It classifies images into two categories: Organic(O) or Recyclable(R). It focuses on developing an AI-powered image classification model to assist EcoClean, GreenCity’s waste management organization, in automating the sorting of recyclable and organic waste. Due to the inefficiencies and inaccuracies of manual waste sorting, the project aims to enhance the process using transfer learning with a pre-trained VGG16 model. By the end of the project, we will have prepared and preprocessed image data, applied and fine-tuned the VGG16 model, evaluated its performance using relevant metrics, and visualized its predictions, resulting in a trained model capable of accurately classifying waste images into recyclable or organic categories for real-world application. 

Summary: Waste Product Classifier Using Transfer Learning 

Goal: Build a model that looks at an image of waste and classifies it as either Organic (O) or Recyclable (R). 

1. Setup 
Install and import libraries — TensorFlow, NumPy, Matplotlib, scikit-learn. Download a dataset of 1,200 waste images split into train and test folders. 

2. Data Preparation 
Use Keras ImageDataGenerator to load images in batches, rescale pixel values (0–255 → 0–1), and apply data augmentation (flipping, shifting) to the training set to prevent overfitting. 

3. Model 1 — Extract Features Model 
Load the pre-trained VGG16 network (trained on ImageNet), freeze all its layers, and stack new Dense + Dropout layers on top. Train only those new layers using the Adam optimizer. VGG16 acts purely as a feature extractor. 

4. Model 2 — Fine-Tuned Model
Reload VGG16 but unfreeze the last conv layer (block5_conv3), allowing it to adapt slightly to the waste data. Retrain with RMSprop optimizer. This gives the model more flexibility and typically better accuracy. 

5. Evaluation 
Both models are loaded from disk, run predictions on 100 test images, and a classification report (precision, recall, F1-score) is printed for each. Individual test images are then plotted with their actual vs. predicted labels for visual inspection. 

The key takeaway: Fine-tuning generally outperforms pure feature extraction because it allows the pre-trained model to slightly adjust its learned features to better fit the new task. 




Procedural Setup 

Install Required Libraries(numpy, sklearn, matplotlib, tensorflow),
Import Required Libraries 

Task 1: Print the version of tensorflow 
Import Dataset "Waste Classification data" from kaggle.com,
Create the o-vs-r-split directories in your environment,
Define model configuration options, 
Loading Images using ImageGeneratorClass, 
ImageDataGenerators 

Task 2: Create a test_generator using the test_datagen object 

Task 3: Print the length of the train_generator 
Pre-trained Models, 
VGG-16 

Task 4: Print the summary of the model 

Task 5: Compile the model 
Fit and train the model, 
Plot loss curves for training and validation sets (extract_feat_model) 

Task 6: Plot accuracy curves for training and validation sets (extract_feat_model) 
Fine-Tuning model 

Task 7: Plot loss curves for training and validation sets (fine tune model) 

Task 8: Plot accuracy curves for training and validation sets (fine tune model) 
Evaluate both models on test data 

Task 9: Plot a test image using Extract Features Model (index_to_plot = 1) 

Task 10: Plot a test image using Fine-Tuned Model (index_to_plot = 1) 



 

 
