# Ninjacart_ComputerVision_Classification — Vegetable Image Classifier
Domain: Computer Vision • Tech Stack: TensorFlow | Keras | Transfer Learning | CNN | Image Augmentation

## Overview
- The objective is to build a multiclass image classification model that can automatically identify images of Onion, Potato, Tomato, and Noise (Indian Market Scenes).

- The problem is inspired by **Ninjacart**, India’s largest fresh produce supply chain company, which aims to automate vegetable classification using AI and image recognition.

- Through this project, I explored the **end-to-end pipeline of image classification** — from data preprocessing and visualization to model building, overfitting control, and transfer learning.

### Dataset

- Dataset Link: https://drive.google.com/file/d/1clZX-lV_MLxKHSyeyTheX5OCQtNCUcqT/view
- This dataset contains web-scraped images of vegetables and market scenes organized into folders.

- Dataset Structure
  | Class | Train Images | Test Images |
  |:------|:-------------:|:------------:|
  | Tomato 🍅 | 789 | 106 |
  | Potato 🥔 | 898 | 83 |
  | Onion 🧅 | 849 | 81 |
  | Indian Market (Noise) 🏪 | 599 | 81 |
  | **Total** | **3135** | **351** |

## Problem Statement

Build a multiclass image classification model that can correctly predict whether an image contains:

- Tomato

- Potato

- Onion

- Indian Market (Noise)

## Concepts Practiced

- Dataset Preparation & Visualization

- Building and training CNN models

- Handling image data (resizing, normalization, augmentation)

- Implementing callbacks (EarlyStopping, ModelCheckpoint, TensorBoard)

- Dealing with overfitting using Batch Normalization, Dropout, and Data Augmentation

- Transfer Learning (VGG16, ResNet50, MobileNet)

- Model evaluation using confusion matrices and performance graphs

## Project Workflow
- #### 1. Setup and Data Loading
  - Downloaded the dataset using gdown and extracted it.
  
  - Verified directory structure and image counts.
  
  - Imported necessary libraries: TensorFlow, Keras, Matplotlib, Seaborn, OpenCV, NumPy, etc.

- #### 2. Exploratory Data Analysis (EDA)
  - Visualized a sample grid of training images.
  
  - Checked image dimensions and verified class distribution.
  
  - Plotted histogram to confirm data balance across categories.

- #### 3. Data Preprocessing
  - Resized images to a square format (e.g. 224×224).
  
  - Normalized pixel values between 0 and 1.
  
  - Split data into train, validation (80:20), and test sets.
  
  - Applied data augmentation: random rotations, flips, zooms, shifts.

- #### 4. Model Building
  - **Baseline CNN**

    - Built a simple CNN architecture from scratch using Conv2D, MaxPooling2D, and Dense layers.
    
    - Trained with Adam optimizer and categorical crossentropy loss.

  - **Improved CNN**

    - Added BatchNormalization and Dropout layers to reduce overfitting.

    - Implemented callbacks:

      - EarlyStopping (monitor validation loss)
      
      - ModelCheckpoint (save best weights)
      
      - TensorBoard (for live metrics visualization)

  - **Transfer Learning**

    - Experimented with:
    
      - VGG16
      
      - ResNet50
      
      - MobileNetV2
    
    - Used pretrained ImageNet weights and added custom dense layers for fine-tuning.

- #### 5. Model Evaluation
  - **Metrics**
  
    - Accuracy, Loss curves
    
    - Confusion Matrix for each model
    
    - Classification Report (Precision, Recall, F1-Score)
  
  - **Visualization**
  
    - Plotted:
    
      - Training vs Validation Accuracy
      
      - Training vs Validation Loss
      
      - Confusion matrix using Seaborn heatmaps

## Testing & Inference
  
  - Evaluated the best-performing model on the test dataset (351 images).
  
  - Tested on random unseen samples to verify predictions.
  
  - Visualized predicted vs actual class labels.

## Results & Insights
  | Model | Train Accuracy | Test Accuracy | Remarks |
  |:------|:---------------:|:--------------:|:--------|
  | Custom CNN | 80% | 70% | Baseline model; underfitting slightly |
  | CNN Revamp | 87% | 83% | Improved generalization using Dropout & BatchNorm |
  | VGG19 | 95% | 90% | Excellent performance; pretrained model (Transfer Learning) |
  | ResNet101 | 98% | 29% | Severe overfitting; needs regularization or fine-tuning |
  | MobileNet | 96% | 84% | Lightweight and efficient; good balance between speed & accuracy |

✅ Best Model: VGG19 (Transfer Learning) — achieved the highest and most stable performance with strong generalization on unseen data.
✅ Key Takeaway: Transfer learning models like VGG19 and MobileNet clearly outperform CNNs built from scratch, offering high accuracy with limited data and less training time.

## Visualizations

  - Class distribution histogram
  
  - Image sample grids
  
  - Training/Validation accuracy & loss plots
  
  - Confusion matrices for all models
  
  - TensorBoard logs for model performance tracking

## Tools & Libraries Used
  | Category | Tools / Libraries |
  |:---------|:-----------------|
  | Deep Learning | TensorFlow, Keras |
  | Data Manipulation | NumPy, Pandas |
  | Visualization | Matplotlib, Seaborn |
  | Image Processing | OpenCV |
  | Logging | TensorBoard |
