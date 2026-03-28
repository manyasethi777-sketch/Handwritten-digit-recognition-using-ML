#  Handwritten Digit Recognition using Machine Learning & Deep Learning

## 📌 Overview

This project focuses on recognizing handwritten digits (0–9) using the **MNIST dataset**. Multiple models are implemented and compared to evaluate their performance in terms of accuracy and efficiency.

The models used are:

* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)
* Convolutional Neural Network (CNN)

---

## 📂 Dataset

We use the **MNIST dataset**, a benchmark dataset in computer vision.

* Total samples: 70,000 images
* Image size: 28 × 28 pixels
* Classes: 10 (digits 0–9)

Dataset is loaded using:

```python
fetch_openml('mnist_784')
```

---

## ⚙️ Preprocessing Steps

* Converted labels from string → integer
* Normalized pixel values (0–255 → 0–1)
* Split dataset:

  * Training set: 56,000 samples
  * Testing set: 14,000 samples

---

## 🤖 Models Implemented

---

### 🔹 1. K-Nearest Neighbors (KNN)

* Algorithm: Distance-based classification
* Parameter used: `k = 3`

#### 📊 Results:

* Accuracy: **97.13%**

####  Pros:

* Simple and easy to implement
* High accuracy without training phase

####  Cons:

* Slow during prediction (distance calculation for all points)
* Memory intensive

---

### 🔹 2. Support Vector Machine (SVM)

* Kernel used: Linear
* Regularization parameter: `C = 1`
* Dataset reduced to:

  * Training: 10,000 samples
  * Testing: 2,000 samples

#### 📊 Results:

* Accuracy: **90.75%**

####  Pros:

* Effective in high-dimensional spaces
* Good theoretical foundation

####  Cons:

* Computationally expensive
* Not scalable to large datasets (hence reduced data used)

---

### 🔹 3. Convolutional Neural Network (CNN)

* Deep learning model specialized for image processing

#### 🏗️ Architecture:

* Conv2D (32 filters, kernel size = 3, ReLU)
* MaxPooling (2×2)
* Flatten
* Dense (128 neurons, ReLU)
* Output layer (10 neurons, Softmax)

#### ⚙️ Training:

* Optimizer: Adam
* Loss function: Categorical Crossentropy
* Epochs: 5
* Batch size: 128

#### 📊 Results:

* Accuracy: **98.30%**

####  Pros:

* Best performance for image data
* Automatically extracts features

####  Cons:

* Requires more computation
* Needs more data and tuning

---

## 📈 Performance Comparison

| Model        | Accuracy          |
| ------------ | ----------------- |
| KNN (k=3)    | 97.13%            |
| SVM (Linear) | 90.75%            |
| CNN          | **98.30% (Best)** |

---

## 📊 Visualization

* Confusion matrices plotted using:

  * `seaborn`
  * `matplotlib`

These help visualize:

* Correct classifications
* Misclassified digits

---

##  Key Insights

* CNN outperforms traditional ML models due to its ability to capture spatial features
* KNN performs surprisingly well but is inefficient for large datasets
* SVM accuracy drops due to dataset reduction (computational limits)

---

## 🚀 How to Run the Project

### 1. Install Dependencies

```bash
pip install numpy matplotlib seaborn scikit-learn tensorflow
```

### 2. Run the script

```bash
python main.py
```

---

## 📁 Project Structure

```
├── main.py
├── README.md
└── outputs/
    ├── knn_confusion_matrix.png
    ├── svm_confusion_matrix.png
```

---

##  Future Improvements

* Use CNN with more layers for higher accuracy
* Try data augmentation
* Implement real-time digit recognition using webcam
* Deploy as a web app using Flask

---

## 🎯 Conclusion

This project demonstrates how different machine learning and deep learning models perform on the same dataset. While traditional models like KNN and SVM are effective, **CNN provides the best performance for image-based tasks**.

---


