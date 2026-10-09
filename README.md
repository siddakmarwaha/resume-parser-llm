# LLM Resume Parser

![Python](https://img.shields.io/badge/python-3.9%2B-blue) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange) ![OpenAI](https://img.shields.io/badge/OpenAI-GPT-412991) ![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

Prototype built in 2024 for an early-stage career-matching startup: a pipeline that ingests resumes (PDF, DOCX, TXT), uses an LLM to extract a **typed, schema-validated profile** (education, experience, skills), and normalizes skills against the U.S. Department of Labor **O*NET** occupational database.

## Highlights

- File ingestion for PDF/DOCX/TXT with MIME detection (`python-magic`, `PyPDF2`, `python-docx`).
- Structured extraction with OpenAI function calling via **Instructor** and **Pydantic** models.
- Skill normalization against O*NET using sentence-transformer embeddings and cosine similarity.
- Exploratory analysis of O*NET abilities, education and job-zone tables.

## Contents

- [`notebooks/01_onet_data_exploration.ipynb`](notebooks/01_onet_data_exploration.ipynb) — exploring O*NET tables
- [`notebooks/02_resume_parsing_llm.ipynb`](notebooks/02_resume_parsing_llm.ipynb) — main LLM extraction pipeline
- [`notebooks/03_skill_matching_api.ipynb`](notebooks/03_skill_matching_api.ipynb) — embedding-based skill matching

## Repository Structure

```text
resume-parser-llm/
├── notebooks/
│   ├── 01_onet_data_exploration.ipynb
│   ├── 02_resume_parsing_llm.ipynb
│   └── 03_skill_matching_api.ipynb
├── .env.example
├── LICENSE
├── README.md
└── requirements.txt
```

## Tech Stack

Python, OpenAI API, Instructor, Pydantic, sentence-transformers, scikit-learn, pandas

## Getting Started

```bash
git clone https://github.com/siddakmarwaha/resume-parser-llm.git
cd resume-parser-llm
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Data

Notebook outputs are cleared because they contained parsed resume content. O*NET data can be downloaded from https://www.onetcenter.org/database.html (place the Excel export in `db_28_1_excel/`). The OpenAI key is read from the `OPENAI_API_KEY` environment variable.

## Author

**Siddak Marwaha**

## License

Code in this repository is released under the [MIT License](LICENSE).
