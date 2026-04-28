# Resume Scorer & ATS Checker

**Live demo → [your-username.github.io/resume-scorer](https://your-username.github.io/resume-scorer)**  
*(Replace with your actual GitHub Pages URL once deployed)*

---

## The problem

Most job seekers send the same generic resume to every role and wonder why they hear nothing back. The reason is usually invisible: Applicant Tracking Systems (ATS) — the software 98% of large companies use to filter resumes before a human ever reads them — reject candidates based on keyword mismatches, formatting issues, and missing role-specific language. Candidates get no feedback, no score, no explanation. They just don't get called.

On top of that, rewriting a resume for every job description is time-consuming and unclear — most people don't know what to change, what to add, or how close they actually are to what the employer wants.

---

## What this tool does

An instant, browser-based resume scorer and ATS compatibility checker. Paste your resume and a job description, and the tool gives you:

- **Overall match score** out of 100 with a visual ring indicator
- **ATS pass rate** — how likely your resume is to clear automated filters
- **Keyword analysis** — which JD keywords you've used (green) and which are missing (red)
- **Benchmark comparison** — your score vs. the estimated average applicant
- **Category breakdown** — scored across skills match, experience, education, keyword density, achievements, and format clarity
- **Prioritised issues list** — High / Medium / Low severity problems, each with a specific fix
- **Quick wins** — role-specific and general tips to improve your score fast
- **Job market insight** — current hiring trends for the target role
- **Edit & re-analyze** — tweak your resume and re-run without starting over

Five preset roles are included out of the box: Product Manager, Data Analyst, Software Engineer, Business Analyst, and Marketing Manager. A custom mode lets you paste any job description.

---

## Tech used

| Layer | Detail |
|---|---|
| Language | Vanilla HTML, CSS, JavaScript — no frameworks, no build tools |
| Styling | Custom CSS with variables for light/dark mode support |
| Fonts | DM Sans + DM Mono via Google Fonts |
| Scoring engine | Local keyword extraction and NLP heuristics (runs entirely in the browser) |
| APIs | None — no backend, no API keys, no server |
| Hosting | GitHub Pages (free static hosting) |
| File size | Single self-contained `.html` file, ~609 lines |

The entire tool runs client-side. There is no server, no database, no API calls, and no data ever leaves the user's browser. Resume text is never stored or transmitted anywhere.

### How the scoring works

The scoring engine runs four independent analyses:

1. **Keyword scoring** — extracts meaningful terms from the job description, cross-references against a curated role-specific keyword bank, and measures overlap with the resume
2. **Experience scoring** — detects action verbs, quantified achievements (numbers, percentages, currency), date ranges, and impact language
3. **Education scoring** — recognises degree types, institution tiers, and GPA patterns
4. **Format scoring** — checks for professional profile URLs, dedicated skills sections, appropriate length, and structural completeness

These are weighted and combined into the overall score:

```
Overall = (keyword × 0.35) + (experience × 0.30) + (education × 0.15) + (format × 0.20)
```

---

## Running it locally

No installation needed. Download `index.html` and open it in any browser:

```bash
# Option 1 — just double-click the file in your file explorer

# Option 2 — serve it locally
npx serve .
# then open http://localhost:3000
```

---

## Project structure

```
resume-scorer/
├── index.html      # Entire app — HTML, CSS, and JS in one file
└── README.md       # This file
```

---

## Built with

Built using [Claude](https://claude.ai) — designed, scored, and iterated entirely through conversation with no manual coding.

---

## License

MIT — free to use, modify, and deploy.
