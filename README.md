# Brain Tumor Segmentation Project

## Dataset
- Source: [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset/data)
- Classes: 
  - `glioma`: 0
  - `meningioma`: 1
  - `notumor`: 2
  - `pituitary`: 3

## Models and Approaches

### 1. Normal CNN Model
- **Architecture**: Custom Convolutional Neural Network
  - Convolutional layers with ReLU activation
  - Max pooling layers
  - Dropout for regularization
  - Fully connected layers
- **Key Features**:
  - 3 convolutional blocks
  - 2 fully connected layers
  - Softmax output layer

### 2. VGG16 Model
- Pre-trained VGG16 architecture
- Modified final classification layer
- 4-class classification

### 3. Faster R-CNN
- Pretrained Faster R-CNN with ResNet50 backbone
- Object detection and localization
- Used for precise tumor region identification

## Data Augmentation Techniques
- Random horizontal flips
- Random rotations (±10 degrees)
- Random resized crop
- Color jittering

## Training Details

### Loss Function
- Cross-Entropy Loss for all models
- Optimized using Adam optimizer

### Performance Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix Analysis

## Results

### Normal CNN
- Accuracy: ~70%
- Precision/Recall: Varies by class
- Best performance on 'notumor' class

### VGG16 (4 Classes)
- Accuracy: ~60%
- Precision range: 0.45 - 0.72
- Strong performance on 'notumor' class

### VGG16 (2 Classes)
- Accuracy: ~94%
- High precision and recall
- Binary classification (tumor vs. no tumor)

### Faster R-CNN Segmentation Technique
- Localization and classification of tumor regions
- In the 4-class classification, implemented Chan-Vese segmentation algorithm
- Enhances tumor region localization and segmentation
- Intersection over Union (IoU) based accuracy
- Provides precise region of interest extraction after initial tumor localization


