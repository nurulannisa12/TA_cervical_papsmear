# Cervical Cancer CAD System using SIPaKMeD Dataset

Computer-Aided Diagnosis (CAD) system for automated cervical cancer screening from Pap smear images, combining object detection, image enhancement, deep learning classification, and explainable AI (XAI).

> 🎓 Undergraduate Thesis (Tugas Akhir) — Biomedical Engineering, Institut Teknologi Sepuluh Nopember (ITS) Surabaya
> 📄 Published as: *"Multiclass Classification Model for Cervical Cancer Using Pap Smear Images Based on Interpretable Deep Learning"*

---

## 📖 Overview

This project implements a full end-to-end pipeline for cervical cancer screening from single-cell Pap smear images using the **SIPaKMeD dataset** (4,049 images, 5 morphological subclasses regrouped into 3 diagnostic classes: **Normal, Benign, Abnormal**).

The system integrates:
1. **ROI Detection** — YOLO11m for cell localization
2. **Image Enhancement** — Adaptive 5D Spider Monkey Optimization (SMO)
3. **Classification** — XceptionNet (transfer learning)
4. **Explainability** — Dual-layer XAI (Grad-CAM++ + Adaptive K-Means segmentation)
5. **GUI** — Interactive desktop-style application built with NiceGUI

## 🔬 Pipeline

```
Pap Smear Image
      │
      ▼
[1] YOLO11m ROI Detection  →  mAP50: 81.2% (Precision 0.746, Recall 0.745)
      │
      ▼
[2] Adaptive 5D SMO Enhancement  →  SSIM: 0.978
      │
      ▼
[3] XceptionNet Classification  →  Test Accuracy: 98.01% (Macro F1: 0.976)
      │
      ▼
[4] Dual-layer XAI
      ├── Grad-CAM++ heatmap visualization
      └── Adaptive K-Means segmentation → N/C ratio quantification
      │
      ▼
   Diagnosis Result (Normal / Benign / Malignant)
```

## 📊 Key Results

| Component | Metric | Score |
|---|---|---|
| YOLO11m ROI Detection | mAP50 | 81.2% |
| YOLO11m ROI Detection | Precision / Recall | 0.746 / 0.745 |
| Adaptive 5D SMO Enhancement | SSIM | 0.978 |
| XceptionNet Classification | Test Accuracy | 98.01% |
| XceptionNet Classification | Macro F1-Score | 0.976 |
| XAI Segmentation | DSC | 0.71 – 0.90 |

## 🖥️ GUI Preview

<!-- Tambahkan screenshot GUI di sini -->
`assets/gui_screenshot.png`

## 🛠️ Tech Stack

- **Detection:** YOLO11m (Ultralytics)
- **Enhancement:** Adaptive 5D Spider Monkey Optimization
- **Classification:** XceptionNet (TensorFlow/Keras)
- **Explainability:** Grad-CAM++, Adaptive K-Means Segmentation
- **GUI Framework:** NiceGUI
- **Language:** Python

## 📂 Repository Structure

```
├── notebooks/          # Training notebooks (YOLO, SMO, XceptionNet)
├── gui/                 # NiceGUI application source code
├── src/                  # Core pipeline modules (segmentation, XAI, utils)
├── assets/             # Diagrams, figures, screenshots
├── requirements.txt
├── .gitignore
└── README.md
```

## ⚙️ Installation

```bash
# Clone the repository
git clone https://github.com/nurulannisa12/cervical-cancer-cad-sipakmed.git
cd cervical-cancer-cad-sipakmed

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## ▶️ Running the Application

```bash
python gui/main.py
```

The application will launch in your browser at `http://127.0.0.1:8081`.

> ⚠️ Model weights are not included in this repository due to file size (>100MB). Download them from [Google Drive](https://drive.google.com/drive/folders/1Go-JdFwSGVGpoCvlgFPsJpdSlh6pv1RQ?usp=sharing) and place them in the `models/` directory before running.

## 📁 Dataset

Manuscript: Multiclass Classification Model for Cervical Cancer Using Pap Smear Images Based on Interpretable Deep Learning
🔗 [SIPaKMeD Dataset Official Source](https://www.cs.uoi.gr/~marina/sipakmed.html)
🔗 [SIPaKMeD Dataset on Kaggle](https://www.kaggle.com/datasets/prahladmehandiratta/cervical-cancer-largest-dataset-sipakmed)

## 👩‍💻 Author

**Nurul Annisa**
Biomedical Engineering, Institut Teknologi Sepuluh Nopember (ITS) Surabaya
[LinkedIn](https://www.linkedin.com/in/nurul-annisa12) | [Email](mailto:annisa.nrll12@gmail.com)

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
