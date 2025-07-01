# Inter-IIT Tech Meet 13.0 — Adobe ML Problem Statement

This repository contains our submission for **Inter-IIT Tech Meet 13.0**, developed by the team representing **IIT Indore** for the **Adobe Machine Learning Problem Statement**. The challenge focuses on the **detection of AI-generated images** and the **identification of distinguishing artifacts**, along with interpretable explanations.

---

## Problem Overview

### Task 1: AI-Generated Image Detection

**Objective:**  
Build a model to classify images as either **real** or **AI-generated**, focusing on those synthesized using diffusion models and other advanced generative techniques.  
Applications include:
- Deepfake detection  
- E-commerce authenticity verification  
- Personal identification  
- News/media trustworthiness  

**Dataset:**  
The [CIFAKE dataset](#) provides 60,000 labeled 32×32 images:
- `REAL`: Real-world images  
- `FAKE`: AI-generated images  

**Evaluation Metrics:**  
- Classification Accuracy  
- Precision / Recall  
- F1 Score  

---

### Task 2: Artifact Identification and Explanation

**Objective:**  
For each image classified in Task 1, identify **artifacts** that distinguish synthetic images from real ones, and generate **interpretable explanations** for the classification.

**Example Artifacts Include:**
- Unnatural Blending: Soft transitions between foreground and background  
- Anatomical Inconsistencies: Incorrect proportions or structures  
- Color Treatment: Uniform or artificial color palettes  
- Texture and Detail: Lack of fine details such as individual hair  
- Motion Effects: Unrealistic blur or unnatural sharpness  

**Evaluation Metric:**  
- Content similarity of explanations and artifact relevance  

---

## Our Approach

### Task 1:
We trained a deep CNN-based classifier tailored for low-resolution (32×32) image classification using:
- Data augmentation (flipping, jitter, noise)
- ResNet and EfficientNet variants adapted for small inputs
- Class-balanced sampling and Focal Loss to handle label imbalance

### Task 2:
To detect and explain artifacts, we employed:
- Grad-CAM and saliency methods for explanation generation
- Intermediate feature visualizations to locate artifact-prone areas
- Rule-based logic to translate visual anomalies into textual artifacts
- A lightweight text generation pipeline for explanation summaries

---

## Team — IIT Indore

- Vishnu Jaddipal — Team Lead  
- Prachi Patil  
- Abhinav Gangil  
- Rishabh Anand  
- Shreeyut Maheshwari  
- Utkarsh Singh  
