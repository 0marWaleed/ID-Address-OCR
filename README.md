# 🆔 ID Address OCR with CRNN

## 📖 Project Overview
Identity documents such as national IDs, passports, and licenses often contain **critical address information** that needs to be extracted for digital records.  
Manual entry is **time-consuming, error-prone, and costly**. Traditional OCR tools like Tesseract struggle with ID formats because of **complex layouts, noisy backgrounds, and varying fonts**.  

This project develops a **deep learning–based OCR system** to automatically extract **address text** from ID images.  
Using a **Convolutional Recurrent Neural Network (CRNN)** with **Connectionist Temporal Classification (CTC) loss**,  
the system can recognize variable-length text sequences without requiring character-level alignment.

---

## 🌟 Why This Project Matters
- **Automation at scale** → Process thousands of IDs in seconds.  
- **Accuracy where it matters** → Reduces errors in sensitive domains like banking and government.  
- **Practical impact** → Enables faster KYC (Know Your Customer) verification, smoother onboarding, and digitization of citizen services.  
- **Adaptability** → Can be retrained on other structured documents beyond IDs.  

---

## 📂 Dataset
The dataset is organized as paired images and text labels:  
- **`.jpg`** → Scanned ID image.  
- **`.txt`** → Ground-truth address.  

Each `.txt` file contains the corresponding address for the image.  

---

## 🏗️ Methodology

### 🔧 Preprocessing
- Images loaded with **OpenCV**.  
- Normalized and resized to a fixed height for consistency.  
- Address text converted into sequences of characters for training.  

### 🧠 Model: CRNN + CTC
- **CNN layers** → Extract spatial features from ID images.  
- **Bidirectional LSTMs** → Model sequential text dependencies.  
- **CTC Loss** → Align predicted character sequences with labels without manual segmentation.  

This design is widely used for scene-text recognition and document OCR.  

---

## 📊 Results
- The model successfully learns to read **complete address strings** from ID images.  
- Unlike traditional OCR, it is **robust to distortions, fonts, and noise**.  

Sample output:  

| ID Image | Ground Truth | Predicted |
|----------|--------------|-----------|
| ![sample](sample.jpg) | `123 Nile Street, Cairo` | `123 Nile Street, Cairo` |

*(Add plots and screenshots from your notebook here: loss curves, prediction examples, etc.)*

---

## ⚙️ Installation
Clone the repo and install the requirements:
```bash
git clone https://github.com/0marWaleed/ID-Address-OCR.git
cd ID-Address-OCR
