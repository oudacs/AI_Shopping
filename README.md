# 🛒 AI Shopping Assistant (المساعد الذكي للتسوق)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8-yellow.svg)
![EasyOCR](https://img.shields.io/badge/EasyOCR-Deep%20Learning-orange.svg)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20Search-success.svg)
![Gemini API](https://img.shields.io/badge/Gemini-3.5%20Flash-blueviolet.svg)

## 📌 Overview (نبذة عن المشروع)
An intelligent, multi-modal Retrieval-Augmented Generation (RAG) pipeline designed to assist users in physical shopping environments. The system processes real-world product images, reads Arabic/English labels, securely retrieves product metadata, and provides context-aware answers to user queries while strictly preventing AI hallucinations.

نظام ذكاء اصطناعي متكامل يهدف إلى مساعدة المستهلكين أثناء التسوق. يقوم النظام بتحليل صور المنتجات الواقعية، قراءة النصوص العربية والإنجليزية من عليها، استرجاع تفاصيل المنتج بدقة متناهية من قاعدة البيانات، والإجابة على أسئلة المستخدم بذكاء.

---

## 🚀 The Pipeline Architecture (هندسة النظام)
Our architecture is built for speed, accuracy, and strict anti-hallucination:

1. **Object Detection (YOLOv8):** Accurately detects and crops the target product from noisy backgrounds.
2. **Text Extraction (EasyOCR):** Extracts Multi-lingual text directly from the product packaging.
3. **Strict Vector Retrieval (ChromaDB + E5):** We strategically pivoted from FAISS to ChromaDB using `intfloat/multilingual-e5-base`. We implemented a strict Cosine Similarity threshold (<0.15) to ensure the system says "Product Not Found" rather than guessing.
4. **LLM Generation (Gemini 3.5 Flash API):** After facing resource exhaustion with local LLMs (Qwen2.5-3B), we pivoted to Gemini API for a production-ready, lightning-fast reasoning engine.

---

## 🛠️ Tech Stack (التقنيات المستخدمة)
* **Computer Vision:** `Ultralytics YOLO`, `OpenCV`
* **OCR Engine:** `EasyOCR` (PyTorch)
* **Vector Database:** `ChromaDB` (Strict Thresholding)
* **Embeddings:** `Sentence-Transformers` (E5-Base)
* **LLM Engine:** `Google GenAI SDK` (Gemini 3.5 Flash)
* **User Interface:** `Gradio`

---

## 💻 How to Run (كيفية التشغيل)

### 1. Clone the Repository
```bash
git clone [https://github.com/oudacs/AI_Shopping.git](https://github.com/oudacs/AI_Shopping.git)
cd AI_Shopping
