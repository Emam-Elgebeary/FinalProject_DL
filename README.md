# Handwritten Digit Recognition using CNN (MNIST)

A Deep Learning project that trains a Convolutional Neural Network (CNN) to classify handwritten digits from the MNIST dataset, comparing two optimizers: Adam and SGD.

---

## Project Overview

This project builds and evaluates a CNN model on the MNIST handwritten digits dataset. The main goal is to compare the performance of two different optimizers (Adam vs SGD) and select the best-performing model.

---

## Project Structure

```
FinalProjectDL.ipynb   # Main Jupyter Notebook (all code)
data/                  # MNIST dataset (auto-downloaded on first run)
```

---

## Model Architecture

A custom CNN with the following layers:

| Block | Layers |
|-------|--------|
| Conv Block 1 | Conv2d(1->32) -> BatchNorm -> ReLU -> MaxPool -> Dropout(0.25) |
| Conv Block 2 | Conv2d(32->64) -> BatchNorm -> ReLU -> MaxPool -> Dropout(0.25) |
| Fully Connected | Flatten -> Linear(3136->128) -> ReLU -> Dropout(0.5) -> Linear(128->10) |

---

## Dataset

- Source: MNIST (loaded via torchvision.datasets)
- Training samples: 5,000
- Validation samples: 1,000
- Test samples: 10,000 (full MNIST test set)
- Augmentation: Random Rotation (+/-10 degrees), Normalization

---

## Experiments

| Experiment | Optimizer | Learning Rate | Momentum |
|------------|-----------|--------------|----------|
| 1 | Adam | 0.001 | - |
| 2 | SGD | 0.01 | 0.9 |

Both models are trained for 10 epochs with CrossEntropyLoss.

---

## Results

The notebook produces:
- Training accuracy and loss curves for both optimizers
- Confusion matrix on the test set
- Classification report (precision, recall, F1-score)
- Visual prediction samples (green = correct, red = wrong)
- Final bar chart comparing both models

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2. Install dependencies

```bash
pip install torch torchvision numpy matplotlib seaborn scikit-learn
```

### 3. Open the notebook

```bash
jupyter notebook FinalProjectDL.ipynb
```

Then run all cells in order (Kernel > Restart & Run All).

Note: The MNIST dataset will be downloaded automatically on first run (~11 MB).

---

## Requirements

- Python 3.8+
- PyTorch
- torchvision
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook

---

## Author

Made as a Final Project for a Deep Learning course.
