# AI-Resume_builder


🚀 AI Resume Forge & ATS Optimizer
📄 Overview
AI Resume Forge is an enterprise-grade resume optimization tool designed to bridge the gap between job seekers and Applicant Tracking Systems (ATS).

Modern hiring relies heavily on automated filters that reject up to 75% of resumes before they reach a human recruiter. This application leverages Google's Gemini AI (via advanced Large Language Models) to semantically analyze resumes against specific Job Descriptions (JDs), identify gaps, and autonomously rewrite content to maximize hiring potential.

Unlike basic keyword counters, this tool understands context, tone, and nuance, providing a truly "smart" optimization process.

✨ Key Features
1. 🛡️ Resilient "Auto-Switch" API Architecture
The core of this application is its custom-built failover engine designed for 99.9% uptime:

Smart Routing: The system prioritizes the newest AI models (e.g., Gemini 2.5 Flash).

Auto-Failover: If a model hits a rate limit (Error 429), the system instantly detects the failure and re-routes the request to a backup model (Gemini 2.0 Flash or Gemini 1.5 Flash) without user intervention.

Crash-Proof HTTP: Uses direct requests implementation to bypass client-library instability and prevent common "Illegal Header" crashes.

2. 📊 Semantic ATS Scoring
Deep Analysis: Evaluates the resume against the JD effectively acting as a strict Technical Recruiter.

Gap Analysis: Identifies missing hard skills, soft skills, and keywords.

Scorecard: Provides a 0-100% compatibility score with detailed reasoning for the rating.

3. ✍️ AI Content Enhancement
Contextual Rewriting: Autonomously rewrites the Professional Summary, Experience, and Skills sections to align with the target JD.

Structured Output: Generates clean JSON data to ensure formatting consistency across all export types.

4. 📂 Universal Export Engine
Offers three distinct export formats to suit any application requirement:

📄 PDF: Direct, pixel-perfect PDF generation (via FPDF).

📝 Word (.docx): Fully editable documents for manual fine-tuning.

📜 LaTeX (.tex): Raw source code with selectable templates (Classic, Modern, Technical) for professional rendering in Overleaf.

5. 🔒 Safety Valve & Input Sanitization
Text Truncation: Automatically truncates oversized PDF text (>10k chars) to prevent token overflow errors.

Key Sanitization: Strips invisible characters from API keys to prevent authentication failures.

🛠️ Tech Stack
Frontend: Streamlit (Python-based web framework)

AI Engine: Google Gemini API (v1beta via REST)

Document Parsing: PyPDF2 (PDF), python-docx (Word)

Document Generation: FPDF (PDF Construction), Jinja2 (LaTeX Templating)

Language: Python 3.x

🚀 Installation & Setup
Follow these steps to deploy the project locally on your machine.

Prerequisites
Python 3.10 or higher installed.

A Google Gemini API Key (Get it free from Google AI Studio).

Step 1: Clone the Repository
Bash

git clone https://github.com/yourusername/ai-resume-forge.git
cd ai-resume-forge
Step 2: Install Dependencies
This project relies on specific Python libraries. Install them using pip:

Bash

pip install -r requirements.txt
(Note: Ensure your requirements.txt contains the following)

Plaintext

streamlit
requests
pypdf2
python-docx
fpdf
jinja2
Step 3: Run the Application
Launch the Streamlit interface:

Bash

python -m streamlit run main.py
The app will open automatically in your default browser at http://localhost:8501.

📖 Usage Guide
Configuration:

Enter your Google Gemini API Key in the sidebar.

Select your preferred AI Model (defaults to gemini-2.5-flash).

Data Input:

Upload Resume: Supports PDF or DOCX files.

Job Description: Paste the full text of the job listing you are targeting.

ATS Analysis:

Click "Run ATS Check".

Review your Match Score, Missing Keywords, and AI suggestions.

Enhancement:

Click "Enhance" to let the AI rewrite your resume tailored to the job.

Wait for the JSON preview to confirm the data structure.

Export:

Choose your preferred format (PDF, Word, or LaTeX).

For LaTeX, select a template style (Classic/Modern/Technical) before downloading.


🤝 Contribution
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request
