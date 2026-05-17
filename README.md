# 🔢 Handwritten Digit Recognition using CNN (MNIST)

A Deep Learning project that classifies handwritten digits (0–9) using a Convolutional Neural Network (CNN) trained on the MNIST dataset. The project compares two optimizers — **Adam** and **SGD** — to find the best-performing model.

---

## 📌 Project Overview

| Property       | Details                          |
|----------------|----------------------------------|
| **Task**       | Image Classification             |
| **Dataset**    | MNIST (Handwritten Digits)       |
| **Model**      | Convolutional Neural Network (CNN) |
| **Optimizers** | Adam vs SGD                      |
| **Framework**  | TensorFlow / Keras               |

---

## 📁 Project Structure

```
FinalProjectDL.ipynb   ← Main Jupyter Notebook (all steps included)
README.md              ← Project documentation
```

---

## 🧠 Model Architecture

The CNN model consists of **3 Convolutional Blocks** followed by fully connected layers:

```
Input (28×28×1)
    │
    ▼
Conv2D(32) → BatchNorm → MaxPooling
    │
    ▼
Conv2D(64) → BatchNorm → MaxPooling → Dropout(0.25)
    │
    ▼
Conv2D(64) → BatchNorm → Dropout(0.25)
    │
    ▼
Flatten
    │
    ▼
Dense(128) → BatchNorm → Dropout(0.5)
    │
    ▼
Dense(10, softmax)  ← Output (digits 0–9)
```

---

## ⚙️ Training Details

- **Loss Function:** Sparse Categorical Crossentropy  
- **Epochs:** Up to 25 (with Early Stopping)  
- **Batch Size:** 64  
- **Data Augmentation:** Rotation, Zoom, Width/Height Shift  
- **Callbacks:** EarlyStopping + ReduceLROnPlateau  

### Optimizers Compared

| Optimizer | Learning Rate | Momentum |
|-----------|--------------|----------|
| Adam      | 0.001        | —        |
| SGD       | 0.01         | 0.9      |

---

## 📊 Results

Both models are evaluated on the MNIST test set (10,000 images). The best model is automatically selected based on test accuracy and used for final predictions.

Evaluation includes:
- Accuracy & Loss curves (Train vs Validation)
- Confusion Matrix
- Classification Report (Precision, Recall, F1-Score per digit)
- Visual prediction samples (correct = green, wrong = red)
- Bar chart comparing Adam vs SGD accuracy

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies

```bash
pip install tensorflow numpy matplotlib seaborn scikit-learn
```

### 3. Run the Notebook

```bash
jupyter notebook FinalProjectDL.ipynb
```

Or open it directly in [Google Colab](https://colab.research.google.com/).

---

## 📦 Requirements

```
tensorflow >= 2.x
numpy
matplotlib
seaborn
scikit-learn
```

---

## 📚 Dataset

The **MNIST** dataset is loaded automatically via `tensorflow.keras.datasets`. It contains:
- **60,000** training images
- **10,000** test images
- Image size: **28×28 grayscale**
- Classes: **10** (digits 0 through 9)

---

## 🤝 Contributing

Pull requests are welcome! Feel free to open an issue for suggestions or improvements.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
