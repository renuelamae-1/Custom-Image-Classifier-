# LW3 Custom-Image-Classifier

## Uploaded Dataset to Google Drive: https://drive.google.com/drive/folders/1hIYYSTh3beTMG-51eUyUxH425qakfQLH?usp=sharing

## Mounted G-Drive in Colab: [https://colab.research.google.com/drive/1Qoag2-vCTobnEj1105u9hWobI7JP47XO?usp=sharing]

## Guide Questions (Student Reflection & Explanation)
### 1. Dataset Preparation
####  a. How did you organize your dataset in Google Drive?
- I organized my dataset by creating a main folder named ImageDataset in Google Drive. Inside this folder, I created subfolders for each plant species (e.g., ClassA, ClassB, etc.). Each subfolder contains images belonging to that specific class. This structure allows TensorFlow to automatically assign labels based on folder names.

####  b. Why is folder structure important for TensorFlow image loading?
- The folder structure is important because the function
image_dataset_from_directory() automatically uses folder names as class labels. Without proper organization, the model would not correctly identify which images belong to which category, leading to incorrect training.

### 2. Model Training
####  a. What is the role of convolutional layers in image classification?
- Convolutional layers extract important features from images such as edges, textures, and shapes. In the code: layers.Conv2D(16, 3, activation='relu')
these layers scan the image and learn patterns that help distinguish different classes.

####  b. Why do we split data into training and validation sets?
- The dataset is split to evaluate how well the model generalizes to new data.
Training set → used to train the model
Validation set → used to test performance during training
This prevents overfitting and ensures the model works on unseen data.

### 3. Performance Analysis
####  a. What accuracy did your model achieve?
- The model achieved a validation accuracy of approximately 85%–90% after the first training and improved to around 90%–94% after applying data augmentation and dropout. This shows that the improvements helped the model generalize better.

####  b. How did the number of images affect the model’s performance?
- The number of images had a significant impact on performance. Since each class contains many images, the model was able to learn more features and patterns effectively. A larger dataset reduced overfitting and improved accuracy, while fewer images would have resulted in poor generalization.

### 4. Critical Thinking
####  a. What challenges did you encounter while using your own dataset?
- Some challenges include:
Inconsistent image sizes and quality
Class imbalance (some folders had fewer images)
Time required to collect and organize images
These issues can negatively affect model accuracy.

####  b. How can data augmentation improve your model?
Data augmentation increases dataset diversity by modifying images (flip, rotate, zoom). In the code:
layers.RandomFlip("horizontal")
layers.RandomRotation(0.1)
This helps the model generalize better and reduces overfitting.
  
### 5. Application
####  a. Suggest a real-world application for your trained model.
- A real-world application is a plant identification system that can classify plant species using images. This can help students, researchers, and farmers identify plants quickly.

####  b. How can this system be integrated into a mobile or web application?
- The model can be:
Converted to TensorFlow Lite for mobile apps
Integrated into a web app (Flask/PHP/JavaScript)
Users upload an image → system predicts the plant

## Guide Questions (Student Explanation & Reflection)
### Visualization & Overfitting
### 1. What signs indicated overfitting in your first model?
####   - In the first model, overfitting was observed when the training accuracy continued to increase while validation accuracy improved slowly or started to plateau. Additionally, the validation loss was higher than the training loss, indicating the model was memorizing training data.
### 2. How did data augmentation affect validation accuracy?
####   - Data augmentation improved validation accuracy by exposing the model to different variations of the same images. This made the model more robust and helped it perform better on unseen data, reducing overfitting.
   
### Model Improvement
### 5. What is the purpose of dropout layers?
####  - Dropout layers randomly deactivate neurons during training. This prevents the model from relying too heavily on specific features and helps reduce overfitting, leading to better generalization.
### 6. Why does data augmentation improve generalization?
####  - Data augmentation creates multiple variations of the same image (flip, rotate, zoom), which helps the model learn more diverse features. This allows it to perform better when predicting new or unseen images.
    
### Performance Comparison
### 7. Compare accuracy before and after improvements.
####  - Before improvement, the model achieved around 85%–90% accuracy. After adding data augmentation and dropout layers, the accuracy improved to approximately 90%–94%, and the gap between training and validation accuracy was reduced.
### 8. Which technique contributed most to improvement?
#### - Data augmentation contributed the most because it increased dataset diversity. Dropout also played an important role in reducing overfitting, but augmentation had a greater impact on validation accuracy.

### Deployment & Application
#### 7. Why is saving the model important?
  - Saving the model allows it to be reused without retraining. It can be deployed in applications, shared with others, and used for predictions anytime.
#### 8. How can this model be deployed in a real-world system?
  - The model can be deployed by integrating it into a web or mobile application. For example, it can be converted to TensorFlow Lite for mobile use or connected to a web system where users upload images and receive predictions.
