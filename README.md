# 🖼️ Image Super-Resolution using SwinIR and ESRT

A PyTorch implementation of **Single Image Super-Resolution (SISR)** using two state-of-the-art transformer-based architectures:

* **SwinIR (Swin Transformer for Image Restoration)**
* **ESRT (Efficient Super-Resolution Transformer)**

This project presents a comparative study of multiple model configurations trained on the **DIV2K** dataset for **2× image super-resolution**.

---

# 📌 Features

* Transformer-based image super-resolution
* Comparison of **6 model configurations**
* Trained on the DIV2K dataset
* Configurable model sizes
* Checkpoint saving during training
* PSNR and SSIM evaluation
* PyTorch implementation

---

# 📂 Repository Structure

```
├── SwinIR_Small.ipynb
├── SwinIR_Medium.ipynb
├── SwinIR_Default.ipynb
│
├── esrt-model.ipynb
```

---

# 🏗️ Models Implemented

## SwinIR Models

| Model          |  Parameters | Epochs |
| -------------- | ----------: | -----: |
| SwinIR Small   | **0.553 M** |     20 |
| SwinIR Medium  | **0.844 M** |     20 |
| SwinIR Default | **1.235 M** |     50 |

---

## ESRT Models

| Model        |  Parameters | Epochs |
| ------------ | ----------: | -----: |
| ESRT Small   | **0.190 M** |     20 |
| ESRT Medium  | **0.752 M** |     20 |
| ESRT Default | **1.686 M** |     20 |

---

# 📂 Dataset

The models were trained using the **DIV2K** dataset.

Dataset statistics:

* **800** Training Images
* **100** Validation Images
* **100** Testing Images

Images are downsampled using **Bicubic Interpolation** to generate the corresponding low-resolution images.

Scale Factor:

```
×2
```

---

# ⚙️ Training Configuration

| Parameter     | Value    |
| ------------- | -------- |
| Framework     | PyTorch  |
| Optimizer     | Adam     |
| Loss Function | L1 Loss  |
| Learning Rate | 2e-4     |
| Dataset       | DIV2K    |
| Scale         | ×2       |
| Device        | CUDA GPU |

---

# 📊 Experimental Results

## SwinIR

| Model   | PSNR      | SSIM       |
| ------- | --------- | ---------- |
| Small   | **22.26** | **0.6188** |
| Medium  | **22.28** | **0.6249** |
| Default | **22.52** | **0.6331** |

---

## ESRT

| Model   | PSNR      | SSIM       |
| ------- | --------- | ---------- |
| Small   | **23.72** | **0.7163** |
| Medium  | **24.35** | **0.7380** |
| Default | **24.44** | **0.7499** |

---

## Bicubic Baseline

| Method  | PSNR      | SSIM       |
| ------- | --------- | ---------- |
| Bicubic | **23.59** | **0.7030** |

---

# 📈 Performance Comparison

| Model          | Parameters (M) |  PSNR |   SSIM |
| -------------- | -------------: | ----: | -----: |
| SwinIR Small   |          0.553 | 22.26 | 0.6188 |
| SwinIR Medium  |          0.844 | 22.28 | 0.6249 |
| SwinIR Default |          1.235 | 22.52 | 0.6331 |
| ESRT Small     |          0.190 | 23.72 | 0.7163 |
| ESRT Medium    |          0.752 | 24.35 | 0.7380 |
| ESRT Default   |          1.686 | 24.44 | 0.7499 |

---

# 🚀 How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/smruti-123-lang/swinIR.git

cd swinIR
```

---

## 2. Install Dependencies

```bash
pip install torch torchvision timm matplotlib numpy pillow opencv-python scikit-image
```

---

## 3. Download the Dataset

Download the DIV2K dataset and update the dataset path in the notebooks.

```
DIV2K_train_HR/
DIV2K_train_LR_bicubic/X2/
```

---

## 4. Train the Models

Run any notebook:

```
SwinIR_Small.ipynb

SwinIR_Medium.ipynb

SwinIR_Default.ipynb

ESRT_Small.ipynb

ESRT_Medium.ipynb

ESRT_Default.ipynb
```

---

# 📚 Evaluation Metrics

The models are evaluated using:

* **PSNR (Peak Signal-to-Noise Ratio)**
* **SSIM (Structural Similarity Index Measure)**

These metrics measure reconstruction quality by comparing the generated high-resolution image with the ground-truth image.

---

# 🔮 Future Improvements

* Train all models for 100+ epochs
* Support ×4 and ×8 super-resolution
* Add inference script for custom images
* Export trained models to ONNX
* Deploy using Streamlit or Flask
* Compare with ESRGAN and RCAN

---

# 🛠️ Technologies Used

* Python
* PyTorch
* OpenCV
* NumPy
* Matplotlib
* torchvision
* timm
* scikit-image

---

# 👩‍💻 Author

**Smruti Misra**

Electronics and Communication Engineering

GitHub: https://github.com/smruti-123-lang

---

# ⭐ Acknowledgement

This project was completed as part of a **B.Tech Internship** on **Transformer-Based Image Super-Resolution**. It focuses on implementing and comparing SwinIR and ESRT architectures using the DIV2K dataset under identical experimental settings.
