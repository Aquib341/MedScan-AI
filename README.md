# 🩺 MedScan AI

**"Your lab report, explained in plain language"**

MedScan AI is a comprehensive, end-to-end AI web application that simplifies complex medical reports (PDFs) for non-medical users. Utilizing cutting-edge OCR and Google's Gemini models, it transforms confusing lab results into understandable, actionable, and trackable health insights.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.28%2B-red)
![Gemini](https://img.shields.io/badge/Google_Gemini-1.5_Flash-orange)
![LangChain](https://img.shields.io/badge/LangChain-Integration-green)

---

## ✨ Features

- 📄 **Dual PDF Processing Pipeline**: Seamlessly extracts text and tabular data from both native digital reports and scanned image-based PDFs using a hybrid approach (`PyMuPDF` and `EasyOCR`).
- 🧠 **AI-Powered Translations**: Leverages Google Gemini and LangChain to break down medical jargon, assign risk levels, and explain test-by-test severity metrics in plain language.
- 🚨 **Emergency Alert System**: Automatically evaluates test thresholds against critical markers. If life-threatening conditions (like extreme glucose levels) are detected, it triggers a high-visibility emergency banner with quick links to nearby hospitals via Google Maps.
- ⚖️ **Longitudinal Report Comparison**: Upload historical and current lab reports to automatically trace your health progress. Generates comparative tables with trend arrows, calculated percentage changes, and actionable patient advice.
- 🗣️ **Multilingual & Accessibility Support**: Provides explanations in English, Hindi, and "Hindlish". Includes built-in Text-to-Speech (`gTTS`) to narrate summaries for elderly or visually impaired users.
- 💊 **Medication Tracker**: An easy-to-use dashboard to log active prescriptions, dosages, and treatment schedules.
- 📥 **Downloadable Actionable Reports**: Packages the AI analysis into a clean, downloadable PDF report (via `ReportLab`), complete with severity trackers and a QR code for easy sharing with your doctor.

## 🏗️ Architecture & Tech Stack

- **Frontend / UI**: Streamlit, Custom CSS
- **AI & Processing Pipeline**: LangChain framework, `gemini-1.5-flash` model
- **PDF Extraction**: `PyMuPDF` (digital), `EasyOCR` + `pdf2image` (scanned)
- **PDF Generation**: `ReportLab`, `qrcode[pil]`, `Pillow`
- **Text-to-Speech**: `gTTS`
- **Environment**: `python-dotenv`

## 🚀 Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd "MedScan AI"
   ```

2. **Create a virtual environment (Recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   *> Note: For OCR on scanned PDFs, your system may require `poppler` to be installed independently (e.g., `brew install poppler` on macOS or via `apt` on Linux).*

4. **Environment Variables:**
   Copy `.env.example` to `.env` and configure your API key.
   ```bash
   cp .env.example .env
   # Open .env and add your GEMINI_API_KEY
   ```

5. **Run the Application:**
   ```bash
   streamlit run app.py
   ```

## 🌐 Deployment
This app is fully compatible with Streamlit Community Cloud. Connect your GitHub repository, ensure `requirements.txt` is in the root directory, and add the `GEMINI_API_KEY` to the Streamlit Advanced settings in Secrets.

## 🔒 Privacy Notice
No medical data is stored on our servers. All uploaded PDFs and analyzed reports are temporarily processed and securely deleted immediately after the session ends.

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 📜 License
This project is licensed under the MIT License.

