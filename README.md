<h1 align="center">🧠 Neurodegenerative Disease Detection using Custom CNN</h1>

<p align="center">
  <b>🎓 Undergraduate Thesis Project (Completed)</b><br>
  <i>Detection of Alzheimer’s, Parkinson’s & FTD from MRI using Deep Learning</i><br><br>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square">
  <img src="https://img.shields.io/badge/Data-ADNI,PPMI,NIFTD-orange?style=flat-square">
  <img src="https://img.shields.io/badge/Model-SadNetV1-green?style=flat-square">
</p>

---

## 🚀 Overview

This research tackles early diagnosis of **Alzheimer’s**, **Parkinson’s**, and **Frontotemporal Dementia (FTD)** using **2D sagittal MRI slices** via a **pseudo-3D deep learning pipeline**.

Our custom model, **SadNetV1**, integrates **MobileNetV2** with **Squeeze-and-Excitation (SE) attention blocks** for a lightweight yet highly effective classification pipeline.

> 🧾 Successfully submitted & defended at **BRAC University, Dept. of CSE**  
> 🔐 Code & datasets are private to uphold ethical and academic guidelines.

---

## 📚 Datasets Used

- 🧠 **ADNI** – Alzheimer's Disease Neuroimaging Initiative  
- 🧠 **PPMI** – Parkinson’s Progression Markers Initiative  
- 🧠 **FTD** – Frontotemporal Dementia Neuroimaging (via IDA)

### 🧼 Preprocessing Steps

- Intensity Clipping → `[0–255]`
- Gamma Correction → `Conditional Gamma Correction`
- Contrast Enhancement → `Conditional CLAHE`
- Image Resize → `224×224`
- Normalization → `Standard scaling`
- Saved format → `.png` files for CNN input

### 🧪 Sample MRI Slice
<img width="395" alt="Sample Slice" src="https://github.com/user-attachments/assets/99c39dec-581a-4882-bfbf-8ff2e7b9097a" />

---

## 🔄 Preprocessing Pipeline

<img width="438" alt="Preprocessing Flowchart" src="https://github.com/user-attachments/assets/374aa9c8-e204-496d-a6cb-b1b95e3cef39" />

---

## 🧬 Data Augmentation & Split

- Dataset divided into `Train`, `Validation`, and `Test`
- Augmentations: **rotation**, **zoom**, **flip**, **contrast adjustments**

### 📊 Data Split Summary
<img src="https://github.com/user-attachments/assets/d1160f6f-b775-4f2d-9283-992b45e8ef7f" style="width:50%; height:auto;" />

### 🔁 Augmentation Pipeline
<img src="https://github.com/user-attachments/assets/9e7cef07-9eaa-4517-abcc-d84917fe8b81" width="70%" />

---

## ⚙️ Model Workflow

<img src="https://github.com/user-attachments/assets/31602497-0db4-4f0f-9d06-38f9df7dfa15" width="75%" />

---

## 🧠 Model Architecture – SadNetV1

- 📌 **Backbone**: MobileNetV2  
- 🧩 **Attention Layer**: Squeeze-and-Excitation (SE)  
- 🖼️ **Input**: Pseudo-3D (stacked 2D MRI slices)  
- 🧮 **Optimizer**: Adam (`lr=1e-5`)  
- ❌ **Loss**: Categorical Crossentropy  

```mermaid
graph LR
A[Input MRI Slice] --> B[Preprocessing]
B --> C[MobileNetV2 + SE Blocks]
C --> D[Classification Head]
D --> E[Predicted Disease]
```

---

## 📊 Model Performance

> ✅ Our SadNetV1 model showed consistent, strong results:

- 🟢 **Train Accuracy**: 96.84%  
- 🟡 **Validation Accuracy**: 97.11%  
- 🔵 **Test Accuracy**: 96.15%

---

## 📈 Results & Visualizations

<table>
  <tr>
    <td align="center"><b>📊 Accuracy Graph</b></td>
    <td align="center"><b>📉 Loss Graph</b></td>
  </tr>
  <tr>
    <td><img width="100%" src="https://github.com/user-attachments/assets/3549ab69-192d-40a6-ad66-80da3b83bb07" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/dcf23989-f534-4ef9-9bc7-8474860c57e1" /></td>
  </tr>
</table>

---

## 🧮 Confusion Matrix – Test & Validation

<table>
  <tr>
    <td align="center"><b>Test Confusion Matrix</b></td>
    <td align="center"><b>Validation Confusion Matrix</b></td>
  </tr>
  <tr>
    <td><img width="100%" src="https://github.com/user-attachments/assets/821a565f-a8ca-43a6-96c2-d4fad21dc40e" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/b9c42e05-7d3a-4fa4-bc13-bf6f2008521c" /></td>
  </tr>
</table>

---

## 🧠 Prediction Results (By Class)

<table>
  <tr>
    <td align="center"><b>Predicted: Alzheimer’s Disease (AD)</b></td>
    <td align="center"><b>Predicted: Parkinson’s Disease (PD)</b></td>
    <td align="center"><b>Predicted: Frontotemporal Dementia (FTD)</b></td>
  </tr>
  <tr>
    <td><img width="100%" src="https://github.com/user-attachments/assets/078dd72b-b226-4ba0-84e9-950e293652ba" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/d62e0406-77ab-4f43-970e-3f9585466056" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/f9b63741-7837-4679-ba9d-434bb281e9d4" /></td>
  </tr>
</table>

---

## 🔬 Grad-CAM Heatmaps

<table>
  <tr>
    <td align="center"><b>AD: Grad-CAM</b></td>
    <td align="center"><b>PD: Grad-CAM</b></td>
    <td align="center"><b>FTD: Grad-CAM</b></td>
  </tr>
  <tr>
    <td><img width="100%" src="https://github.com/user-attachments/assets/0d6e59e7-165d-4afb-a79e-ba941c545e51" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/e425b94e-1647-4f6f-a6e4-217498b25813" /></td>
    <td><img width="100%" src="https://github.com/user-attachments/assets/8f799a5b-a19c-4e0f-bea0-0cbb473a0990" /></td>
  </tr>
</table>

---

## 🔭 Future Directions

- 🚀 Deploy as an interactive web app (upload MRI, view prediction)
- 🔗 Fuse MRI + PET data for multi-modal learning

---

## 🛠 Tech Stack

- 🐍 Python
- 🔥 PyTorch
- 🎞 OpenCV,Keras
- 📊 Pandas, NumPy
- 📉 Matplotlib, Seaborn
- 🧬 NiBabel, pydicom
- 📓 Jupyter Notebook

---

## 🙋‍♂️ Author, Co-author & Contact

**👨‍💻 Shahabuddin Ahmed Khan**  
🎓 B.Sc in Computer Science & Engineering  
🏫 BRAC University, Dhaka, Bangladesh  
📧 [shawon2012.sk@gmail.com](mailto:shawon2012.sk@gmail.com)  
🔗 GitHub: [@ShahabuddinAhmedKhan](https://github.com/ShahabuddinAhmedKhan)  

**👨‍💻 Shadman Rahman Sameen**  
🎓 B.Sc in Computer Science & Engineering  
🏫 BRAC University, Dhaka, Bangladesh  
📧 [shadmanrahmansameen@gmail.com](mailto:shadmanrahmansameen@gmail.com)  
🔗 GitHub: [@ShadmanRahman786](https://github.com/ShadmanRahman786)  

**👨‍💻 Mir Md. Muktasif Sakib**  
🎓 B.Sc in Computer Science & Engineering  
🏫 BRAC University, Dhaka, Bangladesh  
📧 [mir.muktasif.sakib@g.bracu.ac.bd](mailto:mir.muktasif.sakib@g.bracu.ac.bd)  
🔗 GitHub: [@Muktasif-Sakib](https://github.com/Muktasif-Sakib)

---

<p align="center"><i>“Turning pixels into predictions, one scan at a time.”</i></p>
