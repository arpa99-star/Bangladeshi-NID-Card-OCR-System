# Bangladeshi-NID-Card-OCR-System
**Automated Bangla-English NID Card Information Extraction using Deep Learning**

This project implements an **end-to-end OCR pipeline for Bangladeshi National ID (NID) cards** to support **electronic Know Your Customer (eKYC)** processes. The system enhances low-quality images, extracts multilingual text, detects key identity fields, and evaluates extraction reliability using confidence scores.

---

### Project Capabilities

* Handles low-resolution NID images
* Supports Bangla and English text recognition
* Performs automated identity field detection
* Provides confidence-based reliability evaluation
* Allows dataset-level OCR evaluation

---

### Key Features

#### **Image Enhancement**
* Uses **Real-ESRGAN** super-resolution model to improve low-quality or blurry NID images.
* Enhances image clarity before OCR processing.

#### **Image Preprocessing**
Applies multiple computer vision techniques to improve OCR performance:
* Grayscale conversion
* Noise removal (Non-Local Means Denoising)
* Contrast enhancement (CLAHE)
* Adaptive binarization (Otsu Thresholding)

#### **Multilingual OCR**
Utilizes **EasyOCR** to extract text in both:
* Bangla
* English

#### **Field Extraction**
Automatically detects key NID information using pattern matching:
* Name
* Date of Birth
* NID Number

#### **Confidence Scoring**
Implements a field-wise confidence evaluation system:
* Name confidence
* DOB confidence
* NID confidence
* Overall OCR reliability score

#### **Batch Processing**
* Generates structured outputs for analysis

#### **Result Export**
* Saves OCR outputs and confidence scores to CSV format
* Enables further analytics and evaluation

#### **Interactive Image Upload**
* Supports manual testing using image upload interface
* Runs full OCR pipeline on uploaded images

---

### System Pipeline

```bash
NID_eKYC_OCR_System
│
├── Input NID Image
│   └── ↓
├── Image Enhancement (Real-ESRGAN)
│   └── ↓
├── Image Preprocessing
│   ├── Grayscale + Denoising
│   ├── CLAHE (Contrast Enhancement)
│   └── Otsu Thresholding
│   └── ↓
├── Multilingual OCR (EasyOCR)
│   └── ↓
├── Field Detection (Regex-based patterns)
│   └── ↓
├── Confidence Score Calculation
│   └── ↓
└── Output Results
    ├── Extracted Text
    ├── Field-wise Confidence
    └── Overall Confidence Score

---

### Limitations

#### **Limited Dataset Availability**
The dataset used in this project is relatively small. Due to the limited amount of training data, it was not feasible to train a deep learning model from scratch for NID field detection or OCR improvement.

#### **Rule-Based Field Extraction**
Key identity fields such as Name, Date of Birth, and NID Number are extracted using regex-based pattern matching rather than a fully trained document understanding model.

#### **Limited Confidence Evaluation**
Confidence scoring is currently calculated only for three main fields: Name, Date of Birth, and NID Number. Other textual information present on the NID card is not included in the confidence evaluation.

---
