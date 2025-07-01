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
The [CIFAKE dataset](https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images) provides 60,000 labeled 32×32 images:
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
We trained a binary image classifier based on the **CoaTNet architecture**, optimized specifically for 32×32 inputs. The model was trained using both clean and perturbed samples to enhance robustness:
- **CoaTNet (Convolution + Transformer)** backbone for better generalization on synthetic features  
- **Adversarial training** using pixel-level perturbations to improve detection of subtle generative patterns  
- Data augmentation including flipping, noise injection, and brightness changes to increase diversity and generalization

### Task 2:
For artifact detection and explanation generation, we focused on integrating powerful **vision-language models (VLMs)**:
- Fine-tuned large VLMs including **Pixtral-12B**, **Moondream**, and **Qwen-VL** to localize artifacts and generate natural language explanations  
- Curated a **custom dataset of 10,000+ real and AI-generated images**, synthesized via **Stable Diffusion**, with descriptive captions generated using **Gemini Flash 2.0**  
- Combined visual saliency with language reasoning to output interpretable, artifact-aware justifications


---

## Team — IIT Indore

- Vishnu Jaddipal — Team Lead  
- Prachi Patil  
- Abhinav Gangil  
- Rishabh Anand  
- Shreeyut Maheshwari  
- Utkarsh Singh  
