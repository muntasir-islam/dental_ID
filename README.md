# 🦷 Dental-ID: AI-Powered Forensic & Diagnostic System

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.95+-green.svg)
![YOLOv8](https://img.shields.io/badge/AI-YOLOv8-orange.svg)
![Deployment](https://img.shields.io/badge/Deployed-DigitalOcean-blueviolet.svg)

**Dental-ID** is an automated medical imaging system that uses Computer Vision to analyze Panoramic Dental X-rays (OPGs). It detects dental caries (cavities), creates a visualization of the damage, and auto-generates a forensic PDF report for dentists.

> **Live Demo:** [Insert Link if you keep it running]
> **Video Preview:** [Link to a YouTube/Loom video]

---

## 🏗️ Architecture



The system follows a microservice-style architecture deployed on a DigitalOcean Droplet:
1.  **Input:** User uploads a raw X-ray via the web interface.
2.  **Processing (FastAPI):** The image is passed to a Python backend.
3.  **Inference (YOLOv8):** A custom-trained YOLOv8 model scans the X-ray for anomalies (caries/lesions).
4.  **Report Engine (WeasyPrint):** The system draws bounding boxes and compiles a PDF report with timestamps and patient status.
5.  **Output:** A downloadable PDF is returned to the client.

---

## 🚀 Key Features

* **Automated Diagnostics:** Replaces manual visual inspection with AI detection.
* **Forensic Reporting:** Generates a legal-grade PDF report automatically.
* **Computer Vision:** Uses YOLOv8 trained on the **Tufts Dental Database**.
* **Cloud Native:** Fully deployed on a Linux VPS (DigitalOcean) using Systemd and Nginx.

---

## 🛠️ Tech Stack

* **AI/ML:** PyTorch, Ultralytics YOLOv8, OpenCV
* **Backend:** FastAPI (Python), Uvicorn
* **Frontend:** HTML5, JavaScript (Fetch API)
* **DevOps:** DigitalOcean Droplet (Ubuntu), Systemd Service
* **Reporting:** WeasyPrint, Jinja2 Templating

---

## 💻 Installation & Usage

### Prerequisites
* Python 3.8+
* GTK+ libraries (for PDF generation)

### 1. Clone the repo
```bash
git clone [https://github.com/yourusername/dental-id.git](https://github.com/yourusername/dental-id.git)
cd dental-id
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Server
```bash
uvicorn main:app --reload
```
The API will be available at `http://localhost:8000`.

---

## 📊 Model Performance
* **Dataset:** Trained on 500+ annotated panoramic X-rays.
* **Precision:** 89% (Example)
* **Inference Speed:** ~200ms per image on CPU.

## 🤝 License
Distributed under the MIT License. See `LICENSE` for more information.