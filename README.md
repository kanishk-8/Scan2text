
# Scan2text

<img src="https://res.cloudinary.com/dzdgpwtox/image/upload/w_450,c_scale,f_auto/v1712912790/designer-tool-uploads/bucket_3267/1712912786991.png" alt="chipi" height="250">
Scan2text is a repository containing multiple models designed to extract text from images (and PDFs, if needed) and convert it into editable text. Inspired by the Amazon ML Challenge, and while I am only a participant in the challenge, this project showcases a variety of OCR approaches using state-of-the-art deep learning and traditional methods.


## Table of Contents

- [Dataset Structure](#dataset-structure)
- [Features](#features)
- [Models](#models)
  - [Paligemma with Keras](#paligemma-with-keras)
  - [BERT NER](#bert-ner)
  - [BERT-Base NER](#bert-base-ner)
  - [BERT-Large Cased (CoNLL03)](#bert-large-cased-conll03)
  - [BERT-Optimised](#bert-optimised)
  - [BERT-Tesseract Pipeline](#bert-tesseract-pipeline)
  - [BLIP Image Captioning Base](#blip-image-captioning-base)
  - [XLNet Tesseract](#xlnet-tesseract)
- [Overview](#overview)
## Dataset Structure

The repository is designed to work seamlessly with the Amazon ML Challenge dataset (available on Kaggle). Below is a suggested directory layout for the dataset:

```
66e31d6ee96cd_student_/
├── student_resource_3/
│   ├── dataset/
│   │   ├── sample_test.csv
│   │   ├── sample_test_out_f.csv
│   │   ├── test.csv
│   │   └── train.csv
│   ├── src/
│   │   ├── constants.py
│   │   ├── sanity.py
│   │   ├── test.ipynb
│   │   └── utils.py
│   ├── README.md
│   └── sample_code.py
└── archive/
        ├── train/
        │   ├── image_001.png
        │   └── ... 
        └── test/
            ├── image_001.png
            └── ... 
```

## Features

- **Multi-Model OCR:** Implements several models to extract text from images.
- **Flexible Input Handling:** Supports various image formats (JPEG, PNG, etc.) and PDFs.
- **Modular Architecture:** Allows swapping or updating OCR models independently.
- **Batch Processing:** Capable of processing single files or entire directories.
- **Challenge-Driven:** Developed in the context of the Amazon ML Challenge to explore diverse OCR techniques.

## Models

### Paligemma with Keras
<img src="https://machinelearningmastery.com/wp-content/uploads/2021/08/attention_research_1.png" alt="Paligemma with Keras" height="250">

**Overview:**  
A baseline deep learning model built with Keras. It uses convolutional neural networks (CNNs) for feature extraction followed by sequence modeling layers to quickly transform image features into readable text.

**Key Points:**
- **Simple & Fast:** An initial prototype for OCR tasks.
- **Benchmarking:** Serves as a baseline for comparing more advanced techniques.

---

### BERT NER
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrBZYuRm6i3nDz07SqtHaVLZdNgVjJrnJDLVE1gn0sFL7lu2N2BtSNG4kjldSSBlwrwvA&usqp=CAU" alt="BERT NER" height="250">

**Overview:**  
Utilizes the BERT transformer architecture fine-tuned for Named Entity Recognition (NER) to process raw OCR outputs, identifying and labeling entities such as names, dates, and organizations.

**Key Points:**
- **Context-Aware Refinement:** Corrects misrecognized entities.
- **Improved Accuracy:** Particularly beneficial for documents where entity recognition is critical.

---

### BERT-Base NER
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcStdVyIlGWgJVjWtBMNOCfK7GA2CAWPuVqhDFUiTrw9y7I0Qzx63t4fDF-irj02uiGYVnM&usqp=CAU" alt="BERT-Base NER" height="250">

**Overview:**  
A lighter variant of the standard BERT-base model fine-tuned for NER. It strikes a balance between accuracy and inference speed.

**Key Points:**
- **Efficiency:** Ideal for real-time applications or limited-resource environments.
- **Competitive Performance:** Maintains accuracy while speeding up processing.

---

### BERT-Large Cased (CoNLL03)
<img src="https://miro.medium.com/v2/resize:fit:1400/1*IHT7lqvEiuu1BzVIXXD0hA.png" alt="BERT-Large Cased (CoNLL03)" height="250">

**Overview:**  
This model uses a larger, cased version of BERT pre-trained on the CoNLL03 dataset, excelling in capturing fine-grained textual nuances.

**Key Points:**
- **High Accuracy:** Robust recognition even in complex or noisy text.
- **Detailed Output:** Preserves capitalization cues for correct interpretation.

---

### BERT-Optimised
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQgmMpEY8CqGlMRT2OHIeyNW6wHWtlm1L02Cpe5esFGbuRFn6BXE5KWbA7J26pNXAT1sA&usqp=CAU" alt="BERT-Optimised" height="250">

**Overview:**  
An enhanced version of the BERT approach, further fine-tuned for OCR challenges to reduce errors and improve overall text quality.

**Key Points:**
- **Tailored Optimization:** Designed specifically for handling OCR-specific errors.
- **Error Reduction:** Enhances clarity and readability of extracted text.

---

### BERT-Tesseract Pipeline
<img src="https://i0.wp.com/neptune.ai/wp-content/uploads/2022/10/Attention_diagram_transformer.png?ssl=1" alt="BERT-Tesseract Pipeline" height="250">

**Overview:**  
A hybrid model that combines Tesseract OCR’s raw text extraction with BERT’s contextual refinement to produce more accurate text.

**Key Points:**
- **Combined Strengths:** Integrates traditional OCR with modern language modeling.
- **Versatile:** Performs well in scenarios where standalone OCR might struggle.

---

### BLIP Image Captioning Base
<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2024/03/BLIP-Model-architecture-pretraining.webp" alt="BLIP Image Captioning Base" height="250">

**Overview:**  
Repurposes the BLIP model—originally designed for image captioning—to extract descriptive text. It interprets both explicit text and the overall visual context.

**Key Points:**
- **Contextual Understanding:** Captures explicit text and implicit contextual details.
- **Enhanced Descriptions:** Ideal for images where text is intertwined with visual elements.

---

### XLNet Tesseract
<img src="https://machinereads.wordpress.com/wp-content/uploads/2020/05/image-5.png" alt="XLNet Tesseract" height="250">

**Overview:**  
Starts with Tesseract for initial OCR extraction, then uses XLNet to refine the output. XLNet improves sentence coherence by reordering and refining the text.

**Key Points:**
- **Advanced Refinement:** Leverages XLNet’s bidirectional context understanding.
- **Improved Coherence:** Produces more natural and accurate text output.

---

## Overview:
Scan2text is a repository showcasing multiple approaches to optical character recognition (OCR). While I’m only a participant in the Amazon ML Challenge, this project explores how different models—ranging from CNN-based architectures in Keras to advanced transformer-based techniques like BERT and XLNet—can extract and refine text from images or PDFs. By providing a modular structure, recommended dataset organization, and an array of scripts and notebooks, Scan2text aims to help users experiment with and compare various OCR methods in terms of performance, accuracy, and practical application.
