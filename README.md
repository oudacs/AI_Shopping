# 🛒 AI Shopping Assistant

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8-yellow.svg)
![EasyOCR](https://img.shields.io/badge/EasyOCR-Deep%20Learning-orange.svg)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20Search-success.svg)
![Gemini API](https://img.shields.io/badge/Gemini-3.5%20Flash-blueviolet.svg)

## 📌 Overview
An intelligent, multi-modal Retrieval-Augmented Generation (RAG) pipeline designed to assist consumers in physical shopping environments. The system processes real-world product images, reads Arabic/English labels, securely retrieves product metadata, and provides context-aware answers to user queries while strictly preventing AI hallucinations.

---

## 🚀 Pipeline Architecture & Engineering Decisions
Our architecture is built for speed, accuracy, and reliability, featuring specific strategic pivots to ensure a production-ready system:

1. Object Detection (YOLOv8): Accurately detects and crops the target product from noisy, real-world backgrounds.
2. Text Extraction (EasyOCR): Extracts multi-lingual text directly from the product packaging.
3. Strict Vector Retrieval (ChromaDB + E5): We explicitly replaced FAISS with ChromaDB. By implementing a strict Cosine Similarity threshold (<0.15) and a common-word intersection filter, the pipeline acts as a hard gatekeeper to state "Product Not Found" rather than fabricating data.
4. LLM Generation (Gemini 3.5 Flash API): We initially deployed a local LLM (Qwen2.5-3B) for maximum privacy. However, due to severe hardware resource exhaustion, we made a strategic pivot to the Google Gemini API to ensure a stable, lightning-fast reasoning engine.

---

## 🛠️ Tech Stack
* Computer Vision: Ultralytics YOLO, OpenCV
* OCR Engine: EasyOCR (PyTorch)
* Vector Database: ChromaDB (Strict Thresholding)
* Embeddings: Sentence-Transformers (E5-Base)
* LLM Engine: Google GenAI SDK (Gemini 3.5 Flash)
* User Interface: Gradio

---

## 💻 How to Run

### 1. Clone the Repository
Command to clone:
git clone https://github.com/oudacs/AI_Shopping.git

### 2. Install Dependencies
Command to install libraries:
pip install chromadb easyocr sentence-transformers duckduckgo-search google-genai ultralytics opencv-python-headless gradio

### 3. Download Model Weights & Database
Due to GitHub's file size limitations, the heavy machine learning model weights (best.pt) and the ChromaDB database files are hosted securely on Google Drive.

🔗 Download Link: https://drive.google.com/drive/folders/1M2o003rEfO9Z-lesOOUI5dp46GrpiY-T?usp=sharing

Once downloaded, place them in your directory exactly like this:
ai shopping/
  models/
    best.pt
    easyocr_weights/
  chroma_db/

### 4. Run the Interface
Execute the Jupyter Notebook (.ipynb) or the main Python script. When prompted, securely paste your Google Gemini API key into the hidden input field. A local Gradio link will be generated automatically.

---

## 👥 Team Members
* [Ahmed Hussnien] - The Visionary (Core Idea, Target Audience & Societal Impact)
* [Abdelrahman Ouda] - The Architect (Tech Stack, Pipeline Engineering & LLM Pivot)
* [Ziad Eslam] - The Executor (Live Demo, System Accuracy & Threshold Execution)
* [Eslam Hussnein] - The Strategist (Future Scope, Scalability & Economic Value)

---
🎓 Developed by Abdelrahman Ouda and team as an Academic Technical Presentation / Graduation Project.
