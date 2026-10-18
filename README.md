# cats-vs-dogs-classification-cnn
A deep learning project that classifies cat and dog images using a Convolutional Neural Network (CNN) built with TensorFlow and Keras. Includes data preprocessing, augmentation, model evaluation, and predictions on custom images.
# 🐱🐶 Cats vs Dogs Image Classification Using CNN

A deep learning project that classifies images of cats and dogs using a Convolutional Neural Network (CNN) built with TensorFlow and Keras.

This project demonstrates the complete image classification workflow, including dataset preparation, image preprocessing, data augmentation, CNN model training, performance evaluation, and prediction on custom images.

## 📌 Project Overview

Image classification is an important application of computer vision. This project uses deep learning to distinguish between two animal categories: cats and dogs.

The model learns visual features from labeled images and predicts whether an uploaded image contains a cat or a dog.

The project uses a balanced dataset of 1,600 images and trains a CNN model for binary image classification.

## ✨ Features

- 🐱🐶 Binary classification of cats and dogs.
- 🖼️ Image resizing and preprocessing.
- ⚖️ Balanced dataset with 800 cat images and 800 dog images.
- 🔄 Data augmentation using flipping, rotation, zoom, and contrast adjustments.
- 🧠 CNN model built with TensorFlow and Keras.
- 📈 Training and validation accuracy visualization.
- 📉 Training and validation loss visualization.
- 🧪 Model evaluation on a separate test dataset.
- 📊 Classification report and confusion matrix.
- 🔍 Prediction visualization with actual and predicted labels.
- 📤 Custom image upload and prediction.
- 💾 Trained model saved in Keras format.

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Pillow (PIL)
- Google Colab
- Jupyter Notebook

## 📂 Dataset

**Dataset:** Cats and Dogs Filtered Dataset

The project downloads the dataset from Google's TensorFlow public course storage.

Dataset source:

https://storage.googleapis.com/tensorflow-1-public/course2/cats_and_dogs_filtered.zip

The notebook selects a balanced subset of images from the original training folders.

| Dataset Details | Count |
|---|---:|
| Cat images | 800 |
| Dog images | 800 |
| Total images | 1,600 |
| Training images | 1,120 |
| Validation images | 240 |
| Testing images | 240 |

Each category contributes 560 training images, 120 validation images, and 120 testing images.

## 🧠 CNN Model Architecture

The model uses a sequential CNN architecture to learn features from cat and dog images.

The main layers include:

1. **Input Layer:** Accepts RGB images of size 150 × 150.
2. **Data Augmentation:** Applies random flipping, rotation, zooming, and contrast changes during training.
3. **Rescaling Layer:** Normalizes pixel values to the range of 0 to 1.
4. **Convolutional Layers:** Uses 32, 64, and 128 filters to extract visual features.
5. **Max Pooling Layers:** Reduce spatial dimensions.
6. **Dropout Layers:** Help reduce overfitting.
7. **Flatten Layer:** Converts feature maps into a one-dimensional representation.
8. **Dense Layer:** Learns higher-level classification patterns using 128 units.
9. **Output Layer:** Uses one neuron with sigmoid activation to predict the probability of a dog image.

### Model Configuration

| Parameter | Value |
|---|---|
| Model type | Convolutional Neural Network |
| Input image size | 150 × 150 × 3 |
| Optimizer | Adam |
| Loss function | Binary Crossentropy |
| Evaluation metric | Accuracy |
| Batch size | 32 |
| Training epochs | 15 |
| Output activation | Sigmoid |

## ⚙️ Project Workflow

### 1. Import Libraries
Import the required Python libraries for data processing, visualization, model building, and evaluation.

### 2. Check GPU Availability
Check whether a GPU is available to accelerate model training.

### 3. Download and Extract Dataset
Download the Cats and Dogs Filtered dataset and extract its contents.

### 4. Create a Balanced Dataset
Select 800 cat images and 800 dog images to create a balanced dataset.

### 5. Split the Dataset
Divide the selected images into training, validation, and testing sets.

### 6. Load Image Datasets
Load images from their respective folders using TensorFlow's image dataset utilities.

### 7. Optimize the Data Pipeline
Use TensorFlow's prefetch functionality to improve data-loading efficiency.

### 8. Apply Data Augmentation
Introduce image variations through random horizontal flipping, rotation, zooming, and contrast adjustment.

### 9. Build and Compile the CNN
Create the CNN architecture and configure it with the Adam optimizer and binary crossentropy loss.

### 10. Train the Model
Train the model for 15 epochs while monitoring training and validation performance.

### 11. Evaluate Performance
Evaluate the trained model on the test dataset and calculate test accuracy and loss.

### 12. Generate Evaluation Reports
Generate a classification report, confusion matrix, and visual examples of model predictions.

### 13. Save the Model
Save the trained CNN model as `dogs_vs_cats_cnn.keras`.

### 14. Predict Custom Images
Upload a cat or dog image and display the predicted class along with its confidence score.

## 🚀 Getting Started

### Option 1: Run in Google Colab

Google Colab is the recommended environment because the notebook uses Google Colab-specific file upload functionality and paths.

1. Clone or download this repository.
2. Open `Copy_of_DOGS_VS_CATS_IMAGE_CLASSIFICATION.ipynb` in Google Colab.
3. Run the notebook cells in order.
4. Wait for the dataset to download and extract.
5. Train the CNN model.
6. Review the accuracy, loss, classification report, and confusion matrix.
7. Upload your own cat or dog image to test the model.

A GPU runtime is recommended for faster training, although a CPU can also be used.

### Option 2: Run Locally

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/cats-vs-dogs-classification-cnn.git
```

Navigate to the project directory:

```bash
cd cats-vs-dogs-classification-cnn
```

Install the required libraries:

```bash
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn pillow jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open the notebook and execute its cells in order.

**Note:** The notebook contains Google Colab-specific paths and uses `google.colab.files` for custom image uploads. These sections need to be adapted for local execution.

## 📁 Project Structure

```text
cats-vs-dogs-classification-cnn/
│
├── Copy_of_DOGS_VS_CATS_IMAGE_CLASSIFICATION.ipynb
├── README.md
└── dogs_vs_cats_cnn.keras
```

The `.keras` model file is generated after successful training and saving. It is optional if you want to share only the notebook and training code.

## 📊 Model Evaluation

The model is evaluated using the following metrics:

- **Test Accuracy:** Measures the proportion of correctly classified test images.
- **Test Loss:** Measures the model's prediction loss on the test dataset.
- **Precision:** Measures the correctness of positive predictions for each class.
- **Recall:** Measures how many actual examples of a class are correctly identified.
- **F1-Score:** Combines precision and recall into a single metric.
- **Confusion Matrix:** Shows correct and incorrect predictions for both classes.

The notebook generates these evaluation results after training.

**Actual test accuracy and loss:** Add the values printed by your notebook after running the evaluation cell.

## 🔍 Custom Image Prediction

The notebook supports predictions on user-uploaded images.

The prediction workflow is:

1. Upload an image of a cat or dog.
2. Convert the image to RGB format.
3. Resize it to 150 × 150 pixels.
4. Pass the image through the trained CNN.
5. Interpret the sigmoid output to determine the predicted class.
6. Display the predicted animal and confidence percentage.

This feature allows users to test the trained model on images outside the training dataset.

## ⚠️ Limitations

- The model is trained on a relatively small subset of 1,600 images.
- Performance may vary on images with unfamiliar backgrounds, lighting, or animal poses.
- Predictions depend on the quality and characteristics of the input image.
- The confidence score should not be interpreted as a guarantee of correctness.
- The model is designed for cat-versus-dog classification and is not intended to classify other animal categories.

## 🔮 Future Improvements

- Increase the size and diversity of the training dataset.
- Apply transfer learning using MobileNetV2 or EfficientNet.
- Introduce early stopping and learning-rate scheduling.
- Test performance on independent real-world images.
- Deploy the model through a Gradio or Streamlit web interface.
- Build a simple web or mobile application for image classification.
- Compare the performance of different CNN architectures.

## 🎯 Applications

- Learning deep learning and computer vision.
- Practicing binary image classification.
- Understanding CNN architecture and data augmentation.
- Experimenting with image preprocessing and evaluation metrics.
- Developing basic AI-powered image recognition applications.

## 👨‍💻 Author

**Your Name**

GitHub: https://github.com/YOUR-USERNAME

## 📄 License

This project is intended for educational and learning purposes. Add a `LICENSE` file if you want to distribute the project under a specific open-source license.

## 🙌 Acknowledgments

- TensorFlow and Keras
- Scikit-learn
- Matplotlib and Seaborn
- Google Colab
- Contributors to the Cats and Dogs Filtered dataset

---

**Built with Python, TensorFlow, and CNN for image classification.**
