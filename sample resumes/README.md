# Sample resumes

Six made-up resumes in PDF format, for trying out the upload step of the [AI Resume Screening System](../README.md). The names, emails and phone numbers are examples, not real people.

| File | Role in the resume |
|---|---|
| `Arjun_Kumar_ML_Engineer.pdf` | ML Engineer |
| `Priya_Sharma_Data_Scientist.pdf` | Data Scientist |
| `Sneha_Reddy_AI_Student.pdf` | AI student |
| `Ananya_Iyer_Data_Analyst.pdf` | Data Analyst |
| `Rahul_Verma_Web_Developer.pdf` | Web Developer |
| `Vikram_Singh_Accountant.pdf` | Senior Accountant |

The roles range from close to a Machine Learning Engineer job (ML Engineer, Data Scientist) to unrelated (Accountant), so the ranking has something to separate. No scores for these six are stored in the repository.

## How to use them

1. Download the PDFs you want to test with.
2. Open the notebook in Google Colab and run the cells up to the upload cell.
3. Select the PDFs in the file picker.
4. Run the remaining cells to get the ranking.

If you skip the upload, the notebook uses five short text resumes built into it instead, and those are different from these six.

## Adding your own

Any PDF, DOCX or TXT file works. Text-based PDFs are read directly; scanned (image-only) PDFs are not supported because the project has no OCR step. Do not commit real candidates' resumes to a public repository.
