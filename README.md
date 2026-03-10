# 🐾 Animal Image Classification (10 Classes)

[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.19.0-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?logo=kaggle&logoColor=white)](https://www.kaggle.com/)

Proyek Deep Learning untuk klasifikasi gambar hewan menggunakan arsitektur **Convolutional Neural Network (CNN)** yang dikombinasikan dengan **Transfer Learning MobileNetV2**. Model ini dioptimalkan untuk mengenali 10 kelas hewan berbeda dengan akurasi tinggi.

---

## 📊 Project Overview

| Feature | Details |
| :--- | :--- |
| **Dataset Source** | Kaggle (64 Animal Classes) |
| **Selected Classes** | 10 Distinct Classes |
| **Total Images** | 10,000 (After Augmentation) |
| **Framework** | TensorFlow / Keras |
| **Model Architecture** | MobileNetV2 + Custom Dense Layers |
| **Final Test Accuracy** | **99.50%** |

---

## 📂 Dataset & Preprocessing

Dataset asli memiliki 64 kelas, namun untuk meningkatkan performa dan mengurangi ambiguitas fitur visual, dipilih **10 kelas** dengan morfologi yang signifikan:

* **Classes:** *Snake, Elephant, Dolphin, Grasshopper, Owl, Frog, Penguin, Giraffe, Butterfly, Crab.*
* **Augmentation:** Dilakukan untuk menyeimbangkan dataset menjadi **1,000 gambar per kelas**.
    * Techniques: *Rotation, Horizontal Flip, Zoom, Brightness Adjustment.*
* **Data Split:**
    * Training: 80%
    * Validation: 10%
    * Testing: 10%

---

## 🧠 Model Architecture



[Image of CNN architecture diagram]


Model menggunakan pendekatan **Transfer Learning** untuk efisiensi komputasi dan akurasi maksimal:
1.  **Base Model:** MobileNetV2 (Pre-trained on ImageNet).
2.  **Global Average Pooling:** Untuk mengurangi dimensi spasial.
3.  **Fully Connected Layer:** Dense layer dengan Dropout untuk mencegah overfitting.
4.  **Output Layer:** Softmax activation untuk 10 kelas.

---

## 📈 Performance

Hasil evaluasi pada *test set* menunjukkan performa yang sangat solid:

| Metric | Value |
| :--- | :--- |
| **Loss** | 0.0426 |
| **Accuracy** | 99.50% |

> **Note:** Visualisasi *Confusion Matrix* dan *Training History* (Accuracy/Loss) dapat ditemukan di folder `plots/`.

---

## 💾 Model Export & Deployment

Model telah dikonversi ke berbagai format untuk fleksibilitas deployment:

```text
project/
├── tfjs_model/         # Untuk Web Deployment (React/Vue)
│   ├── group1-shard1of1.bin
│   └── model.json
├── tflite/             # Untuk Mobile App (Android/iOS)
│   ├── model.tflite
│   └── label.txt
└── saved_model/        # Untuk Production Server (TF Serving)
    ├── saved_model.pb
    └── variables/
