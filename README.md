# AI Resume Assistant (ATS Checker)

Upload a resume (PDF or DOCX) and get an ATS score, strengths, weaknesses, and concrete suggestions. Optionally paste a job description to get a match score and missing keywords.

**Score = 40% format/structure checks (rule-based) + 60% AI content review (Gemini).**

## Run locally
```bash
pip install -r requirements.txt
export GEMINI_API_KEY="your-key"
streamlit run app.py
```

## Deploy on Streamlit Community Cloud
1. Push `app.py`, `requirements.txt`, `README.md` to a GitHub repo.
2. On share.streamlit.io, create a new app pointing at `app.py`.
3. In **Settings → Secrets**, add:
   ```toml
   GEMINI_API_KEY = "your-key"
   ```

## Notes
- Model is set by `MODEL` at the top of `app.py`; change it if Google retires the model.
- Scanned/image-only PDFs can't be read (ATS systems can't read them either).
