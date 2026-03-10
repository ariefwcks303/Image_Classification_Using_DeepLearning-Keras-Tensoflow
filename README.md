🐾 Animal Image Classification (10 Classes)

Deep Learning project untuk klasifikasi gambar hewan menggunakan Convolutional Neural Network (CNN) dan Transfer Learning MobileNetV2.
Dataset berasal dari Kaggle dengan total 64 kelas hewan, kemudian dipilih 10 kelas yang paling berbeda secara visual untuk meningkatkan performa model.

📊 Project Overview

Dataset Source: Kaggle

Original Classes: 64 classes

Selected Classes: 10 classes

Total Images After Augmentation: 10,000 images

Framework: TensorFlow / Keras

Final Test Accuracy: 99.50%

📦 Libraries Used
Library Version
pandas 2.2.2
numpy 2.0.2
tensorflow 2.19.0
matplotlib 3.10.0
seaborn 0.13.2
scikit-learn 1.6.1
Pillow 11.3.0
tensorflowjs 4.22.0
📂 Dataset

Dataset diambil dari Kaggle:

https://www.kaggle.com/api/v1/datasets/download/anthonytherrien/image-classification-64-classes-animal

Dataset asli memiliki 64 kelas hewan dengan berbagai kategori.

🧹 Data Preprocessing

Dari 64 kelas yang tersedia, dipilih 10 kelas hewan yang memiliki perbedaan morfologi signifikan agar model lebih mudah membedakan fitur visual.

Selected Classes
snake (216 images)
elephant (288 images)
dolphin (216 images)
grasshopper (216 images)
owl (216 images)
frog (312 images)
penguin (216 images)
giraffe (216 images)
butterfly (216 images)
crab (216 images)
🔄 Data Augmentation

Untuk meningkatkan jumlah dataset serta mengurangi overfitting, dilakukan data augmentation hingga setiap kelas memiliki 1000 gambar.

Total dataset setelah augmentasi:

10 classes × 1000 images = 10,000 images

Teknik augmentasi yang digunakan:

Rotation

Horizontal Flip

Zoom

Width & Height Shift

Brightness Adjustment

✂️ Dataset Split

Dataset dibagi menjadi:

Dataset Percentage
Training 80%
Validation 10%
Test 10%

Rasio pembagian:

Train : Validation : Test = 8 : 1 : 1
🧠 Model Architecture

Model dibangun menggunakan TensorFlow Sequential API dengan kombinasi:

Convolutional Neural Network (CNN)

Conv2D Layers

MaxPooling Layers

Transfer Learning MobileNetV2

MobileNetV2 digunakan untuk meningkatkan kemampuan ekstraksi fitur pada gambar.

🏋️ Model Training

Contoh hasil training:

Epoch 1/10
250/250 ━━━━━━━━━━━━━━━━━━━━
accuracy: 0.9293
loss: 0.3743

Validation:
val_accuracy: 0.9980
val_loss: 0.0236
learning_rate: 0.0010
📈 Model Evaluation

Evaluasi dilakukan menggunakan test dataset.

Metric Result
Test Accuracy 99.50%
Test Loss 0.0426
📊 Visualization

Visualisasi performa model menggunakan:

Confusion Matrix

Training vs Validation Accuracy

Training vs Validation Loss

Library yang digunakan:

Matplotlib

Seaborn

💾 Model Export

Model disimpan dalam beberapa format untuk deployment di berbagai platform.

project
│
├── tfjs_model
│ ├── group1-shard1of1.bin
│ └── model.json
│
├── tflite
│ ├── model.tflite
│ └── label.txt
│
├── saved_model
│ ├── saved_model.pb
│ └── variables

Format yang tersedia:

TensorFlow SavedModel

TensorFlow Lite (TFLite)

TensorFlow.js

🔍 Model Inference

Pengujian model dilakukan menggunakan data test.

Test Scenario 1

Menggunakan 9 gambar test

Hasil prediksi: 100% benar

Test Scenario 2

Menggunakan 1 gambar test

Hasil prediksi: benar

⚙️ Environment Requirements
pandas : 2.2.2
numpy : 2.0.2
tensorflow : 2.19.0
matplotlib : 3.10.0
seaborn : 0.13.2
scikit-learn : 1.6.1
Pillow : 11.3.0
tensorflowjs : 4.22.0
