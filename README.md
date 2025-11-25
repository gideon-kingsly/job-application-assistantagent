# job-application-assistantagent


📄 Job Application Assistant Agent (Capstone Project – Google x Kaggle AI Agents Intensive 2025)

A lightweight, dependency-safe AI Agent designed to help job seekers instantly analyze job descriptions, match skills, and generate tailored cover letters using their resume data.

This project is created as part of the AI Agents Intensive (Nov 10–14, 2025) by Google & Kaggle under the Enterprise Agents Track.

🚀 Project Overview

Applying for jobs is a repetitive and time-consuming process. Every job description must be manually read, compared with the resume, and tailored cover letters must be written.

This agent automates that entire workflow:

✅ Extracts skills from your resume
✅ Analyzes any job description
✅ Produces a similarity score
✅ Identifies matched & missing skills
✅ Generates a personalized cover letter
✅ Saves job applications as memory

This project is built to be simple, fast, and fully runnable in Google Colab, without heavy dependencies or GPU usage.

🎯 Features
🔍 1. Resume Parsing

Reads resume PDF using pdfplumber

Extracts meaningful text

🧠 2. Skill Extraction

Uses a curated list of technical skills

Detects skills present in both resume and JD

📊 3. Resume ↔ Job Description Matching

Calculates ATS-style similarity score

Shows matched and missing skills

✍️ 4. AI Cover Letter Generator

Creates a clean, customizable cover letter

Uses job description + resume context

Perfect for fast applications

💾 5. Application Memory

Stores analyzed JDs in:

/content/job_app_memory.json


This acts like an agent’s long-term memory.

🟨 6. Lightweight & Error-Free

No transformers

No sentence-transformers

No Gradio (avoids dependency issues)

Works smoothly in Colab

🧩 Architecture
             ┌──────────────────┐
             │   Resume PDF      │
             └─────────┬────────┘
                       │
                extract_text()
                       │
             ┌─────────▼─────────┐
             │   Resume Parser    │
             └─────────┬─────────┘
                       │
             simple_skill_extract()
                       │
     ┌─────────────────▼──────────────────┐
     │         Matching Engine             │
     │  - JD Skills vs Resume Skills       │
     │  - Similarity Score                 │
     └─────────────────┬──────────────────┘
                       │
         generate_cover_letter()
                       │
             ┌─────────▼─────────┐
             │  Output + Memory   │
             └────────────────────┘

🛠️ Technologies Used
Feature	Technology
PDF Parsing	pdfplumber
Skill Extraction	Custom Python
Matching Logic	Keyword Intersection
Cover Letter	Template-based generator
Memory	JSON storage
Runtime Environment	Google Colab
📁 Project Structure
📦 job-application-assistant-agent
 ┣ 📄 capstone_job_agent.ipynb
 ┣ 📄 README.md
 ┣ 📄 job_app_memory.json   (auto-created)
 ┗ 📄 architecture.png      (optional)

▶️ How to Run in Google Colab
1️⃣ Upload the notebook

Open Colab → Upload capstone_job_agent.ipynb

2️⃣ Upload your resume

Upload your resume as:

/mnt/data/resume.pdf


or change the path in notebook:

RESUME_PATH = "/content/resume.pdf"

3️⃣ Run cells in order

The notebook will:

Load your resume

Extract skills

Analyze sample job descriptions

Generate cover letters

4️⃣ Analyze any JD

Use:

analyze_jd_and_save(
    jd_text,
    name="Your Name",
    role="Role Title",
    save=True
)

📦 Example Output
Similarity Result
{
  "similarity_score": 66.67,
  "matched_skills": ["java", "mysql", "git"],
  "missing_skills": ["docker", "linux"],
  ...
}

Cover Letter (Generated)
Dear Hiring Team,

I am writing to express my interest in Software Engineer. I am Gideon Kingsly Raj.

From my resume: Educated professional with knowledge in Java, MySQL, HTML/CSS...
From the JD: We are hiring a Software Engineer with Java, Spring Boot...
Relevant skills: java, mysql, git.

Thank you.
Gideon Kingsly Raj

🌟 Why This Project Fits the Kaggle Capstone Requirements

This project fulfills at least three major agent concepts:

✔ Tools

PDF parsing

Custom skill extraction

Memory saving

✔ State & Memory

Long-term storage in JSON

✔ Multi-Agent Workflow (Conceptual)

Resume parser

Skill extractor

Matching logic

Cover-letter generator

✔ Enterprise Agent Use Case

Directly improves job-application workflows.

📢 About the Author

Gideon Kingsly Raj
AI Agent Developer • Software Engineering Enthusiast
Created as part of Google x Kaggle AI Agents Intensive 2025.

📝 License

MIT License — free to use, modify, and share.
