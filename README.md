# Cervical Cancer Diagnostic System

Final project (Tugas Akhir) — Biomedical Engineering, ITS 2026.

An end-to-end web-based diagnostic system for automated cervical cancer 
detection and classification from Pap smear slide images, built with NiceGUI.

## Pipeline
1. **ROI Detection** — YOLO11m detects individual cells on the whole slide
2. **Crop & Filter** — Detected cells are cropped and artifacts removed manually
3. **Smart Enhancement** — Spider Monkey Optimization (SMO) finds the best PMD+USM+CLAHE parameters per cell
4. **Classification** — XceptionNet classifies each cell as Normal / Benign / Malignant
5. **XAI Validation** — Saliency Map + Grad-CAM visualize what the model focuses on
6. **WSI Heatmap** — Grad-CAM++ stitched across the whole slide image

## Dataset
[SIPaKMeD](https://www.kaggle.com/datasets/prahladmehandiratta/cervical-cancer-largest-dataset-sipakmed) — Pap smear cervical cell dataset

## Stack
`Python` `NiceGUI` `PyTorch` `Ultralytics YOLO` `OpenCV`

## Run locally
```bash
pip install -r requirements.txt
python main.py
```

## Author
Nurul Annisa — 5023221031  
Supervisors: Prof. Dr. Tri Arief Sardjono, S.T., M.T. · Nabila Puspita Firdi, S.T., M.Sc.  
Department of Biomedical Engineering, Institut Teknologi Sepuluh Nopember
