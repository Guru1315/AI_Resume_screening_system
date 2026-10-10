# 🤖 AI Resume Screening System

An NLP-based system that compares multiple resumes with a job description and **ranks candidates by how closely they match the role**. Built in Google Colab as part of an AI internship project.

## 📌 Overview

Recruiters often receive hundreds of resumes for a single role. This project automates the first screening step: it extracts text from uploaded resumes, analyzes the content with NLP techniques, and produces a ranked list of candidates with an explanation of which required skills each one has or is missing.

## ✨ Features

- Upload **multiple resumes** at once (PDF, DOCX, TXT)
- **Text extraction** from resumes using `pdfplumber` and `python-docx`
- **NLP preprocessing**: lowercasing, noise removal, stopword removal, lemmatization (NLTK)
- **Three scoring methods** combined into one final score
- **Ranked results** with a verdict (Strong / Moderate / Weak match)
- **Explainability**: matched vs. missing skills for every candidate
- **Visualizations**: ranking bar chart and score-breakdown heatmap
- **CSV export** of the results
- Built-in **sample resumes** for a quick demo

## 🧠 How It Works

```
Resumes (PDF/DOCX/TXT) ─► Text Extraction ─► NLP Preprocessing ─┐
                                                                  ├─► Scoring ─► Final Score ─► Ranking
Job Description + Required Skills ───────────────────────────────┘
```

| Method | What it measures | Weight |
|---|---|---|
| **Sentence-BERT embeddings** (`all-MiniLM-L6-v2`) + cosine similarity | Semantic meaning match | 40% |
| **TF-IDF** (unigrams + bigrams) + cosine similarity | Keyword overlap | 30% |
| **Skill matching** | % of required skills found in the resume | 30% |

```
Final Score = 0.4 × BERT + 0.3 × TF-IDF + 0.3 × Skill Match
```

The weights can be changed in the notebook.

## 🛠️ Tech Stack

- **Language:** Python
- **NLP:** NLTK, Sentence-Transformers, scikit-learn (TF-IDF, cosine similarity)
- **Document parsing:** pdfplumber, python-docx
- **Data & visualization:** pandas, NumPy, Matplotlib, Seaborn
- **Platform:** Google Colab

## 🚀 Getting Started

1. Open `AI_Resume_Screening_System.ipynb` in [Google Colab](https://colab.research.google.com).
2. Run the install cell. If Colab asks, restart the session once.
3. Edit the **job title, job description and required skills** cell for your role.
4. Run the upload cell and select your resumes (or skip it to use the sample resumes).
5. Run the remaining cells in order to see the ranking, charts and CSV download.

> Tip: run cells one at a time rather than using *Run all*.

## 📂 Repository Structure

```
├── AI_Resume_Screening_System.ipynb   # Main Colab notebook
├── sample_resumes/                    # Sample PDF resumes for testing
├── resume_ranking_results.csv         # Example output
└── README.md
```

## 📊 Sample Output

Add your screenshots here after running the notebook:

```
![Ranking chart](images/ranking_chart.png)
![Score heatmap](images/score_heatmap.png)
```

The results table contains: **Rank, Resume, Semantic (BERT), Keyword (TF-IDF), Skill Match %, Final Score, Matched Skills, Missing Skills, Verdict**.

## ⚠️ Limitations

- Scanned (image-only) PDFs need OCR, which is not included.
- Skill matching depends on the skills list you provide.
- Experience years, education level and resume layout are not yet analyzed.
- AI hiring tools can reflect bias, so results should support a human recruiter, not replace one.

## 🔮 Future Improvements

- OCR support for scanned resumes
- Extraction of experience, education and certifications
- Automatic skill extraction using NER
- Bias and fairness checks
- Web interface using Streamlit or Gradio

## 🎓 Learning Outcomes

- Real-world use of AI in hiring systems
- NLP text preprocessing and similarity matching
- Comparing keyword-based and semantic-embedding approaches
- Building an explainable ranking pipeline

## 📄 License

This project was created for educational purposes as part of an AI internship.
