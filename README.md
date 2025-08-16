# AIDI 1002 Final Project — SFCHD YOLOv8 (Reproduction + Contribution)

> YOLOv8 fine-tuning on the **Safety Helmet & Clothing Detection (SFCHD)** dataset, with a reproducible pipeline and a targeted contribution to improve practical utility.

---

## Project Overview
This project reproduces a YOLO-based approach for detecting **safety helmets**, **safety clothing**, and related classes in workplace/surveillance images, then adds a **significant contribution**: a robust, automated data-prep + split pipeline and tuned training setup that makes the method easier to run, audit, and extend.

**Key outcome:** Achieved **mAP50 = 0.489** overall; best per-class **mAP50 = 0.860** for `safety_helmet`.

---

## Paper & Context
- **Task:** Object detection for PPE (helmets/clothing).
- **Model:** Ultralytics **YOLOv8** (nano variant for speed on Colab).
- **Dataset:** SFCHD (images + YOLO-format labels).

> **Note:** Dataset files are **not included** in this repo. See **Dataset Access** below.

---

## My Contributions & Achievements
- **Automated dataset preparation** (scripts to mirror Drive→Colab, verify image–label pairs, and build `train/val/test` with correct YOLO structure).  
  *Result:* **100% image–label match** across splits; avoided missing-annotation errors.

- **Custom YOLO dataset config (YAML)** with exact class index mapping and stable paths.  
  *Result:* Seamless training/validation with zero manual path fixes.

- **Optimized training recipe** for Colab (batch size, epochs, image size, caching, deterministic seed).  
  *Result:* **mAP50 = 0.489** overall; **0.860** for `safety_helmet`.

- **Validation & error analysis** (per-class mAP, bbox inspection).  
  *Result:* Identified weak classes (e.g., blurred clothing) and tied underperformance to class imbalance.

- **Actionable roadmap** (bigger YOLO variants, stronger augmentation, deployment notes).  
  *Result:* Clear path to accuracy gains and real-time CCTV integration.

---

## Repository Structure
```plaintext
AIDI1002_Final_Project/
├── reproduction/        # Original paper reproduction code
├── contribution/        # YOLOv8 fine-tuning + improvements
├── dataset_preparation/ # Scripts for data prep and splitting
├── results/             # Evaluation metrics and predictions
└── README.md            # Project documentation

```

## Data
- **Dataset:** Safety Helmet & Clothing Detection (SFCHD)  
- **Source:** https://drive.google.com/drive/folders/1WHcIfqJW9nd7tDNFH03vznThIbuRsy9-?usp=drive_link 
- **Classes:** safety_helmet, safety_clothing, person, face  
- **Note:** Dataset is not stored in this repo due to size.
