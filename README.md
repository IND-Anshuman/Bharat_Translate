# 🌉 Bharat_Translate: Multilingual Indic Translation Pipeline

**Bharat_Translate** is a **production-quality AI translation system** for Indian languages built in Python.  
It performs **end-to-end translation** of *code-mixed* or *Romanized Indic text* (e.g., Hinglish, Tanglish, Marathiglish) using a modular pipeline featuring transliteration, translation, semantic confidence scoring, and intelligent LLM fallback.

---

## 🚀 Features

✅ **Automatic Language Detection** — Detects source language among 22+ Indic and English languages  
✅ **AI4Bharat Transliteration** — Converts Romanized text into native Indic scripts  
✅ **High-Quality Translation** — Uses **AI4Bharat IndicTrans2** or **Meta NLLB-200** (extensible backend)  
✅ **Confidence Scoring** — Semantic similarity evaluation via `sentence-transformers/all-MiniLM-L6-v2`  
✅ **Intelligent Fallback** — Contextual re-translation using **Gemini 2.5 Pro API** when confidence < 0.7  
✅ **Logging & Analytics** — All results logged in `translation_log.csv`  
✅ **GPU Support** — Automatic device detection (`torch.device`)  
✅ **Streamlit/Gradio UI** — Simple, clean user interface  
✅ **Unit Tests** — For transliteration, translation, and confidence validation  

---

## 🧠 Pipeline Overview

### 1️⃣ Transliteration Stage
- Detects the **source language** using `langdetect` or `fastText`.
- Uses **AI4Bharat IndicXlit** to convert Romanized Indic text into native script.
- Leaves English words unchanged.

### 2️⃣ Translation Stage
- Uses **AI4Bharat IndicTrans2** for translation between Indic and English.
- Modular backend — can easily switch to **Meta NLLB-200** or future models.

### 3️⃣ Confidence Evaluation
- Computes **semantic similarity** between source and translated text.
- If score < 0.7 → triggers fallback translation.

### 4️⃣ Fallback Translation
- Uses **Gemini 2.5 Pro** (via API key in `.env`) for high-quality re-translation.
- Logs fallback usage for analysis.

---

## 🗣️ Supported Languages

| Code | Language | Code | Language |
|------|-----------|------|-----------|
| hi | Hindi | ta | Tamil |
| te | Telugu | mr | Marathi |
| bn | Bengali | ml | Malayalam |
| gu | Gujarati | kn | Kannada |
| or | Odia | pa | Punjabi |
| as | Assamese | ur | Urdu |
| gom | Konkani | sa | Sanskrit |
| ks | Kashmiri | sd | Sindhi |
| mni | Manipuri | doi | Dogri |
| brx | Bodo | sat | Santali |
| ne | Nepali | en | English |

---

## 🧩 Architecture Diagram

