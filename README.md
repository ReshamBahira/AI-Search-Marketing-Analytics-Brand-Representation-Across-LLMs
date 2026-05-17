# AI-Search-Marketing-Analytics-Brand-Representation-Across-LLMs

## *How LLMs Represent Consumer Audio Brands — and What It Means for GEO*

## 🔍 Overview

As consumers increasingly turn to ChatGPT, Claude, and Gemini for product recommendations, a new challenge has emerged: **Generative Engine Optimization (GEO)** — the practice of ensuring your brand is visible, prominent, and positively framed in LLM-generated responses.

This project investigates how three leading LLMs represent headphone brands (**Sony**, **Beats**, **Soundcore**) across 26 standardized consumer queries, building a full text-mining pipeline to measure brand visibility, prominence, sentiment, and contextual positioning.

---

## 🌐 Why GEO Matters

Traditional SEO targets search engine rankings. **GEO targets the AI layer above search.**

LLMs don't return a list of links — they synthesize narrative recommendations. If your brand isn't in that narrative, it's invisible to a growing share of discovery-stage consumers.

| Channel | Output | Optimization Strategy |
|---|---|---|
| Google Search | Ranked URLs | SEO (backlinks, keywords) |
| LLM / AI Search | Narrative response | **GEO (content volume, framing, use-case coverage)** |

This study provides an empirical framework for auditing brand representation in LLM outputs — a foundational tool for any GEO strategy.

---

## 📊 Key Findings

### Brand Visibility & Prominence

| Metric | Sony | Beats | Soundcore |
|---|---|---|---|
| **Visibility** (% responses mentioning brand) | 91% | 48% | 38% |
| **Prominence** (% first-mentioned) | 63% | 9% | 10% |
| **Avg. Sentiment (VADER)** | 0.58 | 0.41 | 0.41 |

- **Sony dominates** across all three LLMs with 90–92% visibility and first-mention rates of 60–67%
- Brand hierarchy is **consistent across models** (Chi-square p = 0.19, non-significant), suggesting patterns reflect **training data distributions**, not model-specific bias
- All brands receive **positive sentiment** when mentioned (scores > 0.40)

### GEO Implications by Topic

| Use Case | Dominant Brand | Opportunity |
|---|---|---|
| Fitness / Gym | Sony (85–92%), Beats (35–58%) | Beats has real fitness niche traction |
| ANC / Noise Cancellation | Sony (75–92%) | Underserved by emerging brands |
| Price / Value / Budget | More balanced | **Best entry point for Soundcore-type brands** |
| Travel / Commuting | Sony + Sennheiser | Premium brand association dominates |

> **GEO Takeaway:** Smaller brands can compete by building high-quality, use-case-specific content that targets the niches where the dominant player is weakest.

---

## 🛠️ Methods

```
26 Queries (Reddit/forum-sourced, brand-agnostic)
    └── Run twice per model × 3 models = 180 responses
         └── Preprocessing (normalization, tokenization, alias resolution)
              ├── Dictionary-based NER → brand mentions
              ├── First-mention extraction → prominence scores
              ├── VADER sentiment → sentence-level scoring
              ├── TF-IDF topic modeling → use-case clustering
              └── Statistical validation (Chi-square, Cramer's V, t-tests, cosine similarity)
```

**Models evaluated:** ChatGPT (GPT-4) · Claude (Anthropic) · Gemini (Google)

**Topic clusters:** Fitness · Noise Cancellation · Price/Value · Travel · Work/Calls · Sound Quality

---

## 📁 Repository Structure

```
├── Final.ipynb               # Full analysis pipeline (reproducible)
├── data/
│   ├── raw_responses/        # 180 LLM responses (JSON)
│   └── processed/            # Cleaned corpus
├── outputs/
│   ├── visibility_heatmaps/  # Topic × Brand visibility charts
│   ├── sentiment_heatmaps/   # Topic × Brand sentiment charts
│   └── summary_tables/       # Aggregated metrics
├── report/
│   └── Brand_Visibility_in_AI_Search_Report.pdf
└── presentation/
    └── Brand_Visibility_in_AI_Search_Final_Presentation.pptx
```

---

## ⚙️ Setup & Reproduction

```bash
git clone https://github.com/<your-username>/brand-visibility-ai-search.git
cd brand-visibility-ai-search
pip install -r requirements.txt
jupyter notebook Final.ipynb
```

**Dependencies:** `nltk` · `vaderSentiment` · `scikit-learn` · `pandas` · `matplotlib` · `seaborn`

---

## 🤖 AI Usage Declaration

LLMs (ChatGPT, Claude) were used **only for data collection** — querying the models with product recommendation prompts to generate the response dataset.

**All analysis was performed in Python without AI assistance:**
- NER, sentiment scoring, topic modeling → `NLTK`, `VADER`, `scikit-learn`
- Statistical tests → `scipy`
- Visualizations → `matplotlib`, `seaborn`

No AI tools were used to generate or modify the content of the report.

---

## 🔮 Future Directions

- [ ] Extend to additional product categories (laptops, smartphones, appliances)
- [ ] Longitudinal analysis tracking how LLM representations shift as training data evolves
- [ ] More sophisticated NLP for aspect-based sentiment extraction
- [ ] Develop a GEO audit toolkit for practitioners

---

## 📚 References

1. Devlin et al. (2019). BERT: Pre-training of deep bidirectional transformers. *NAACL-HLT.*
2. Hutto & Gilbert (2014). VADER: A parsimonious rule-based model for sentiment analysis. *AAAI ICWSM.*
3. Bird, Klein & Loper (2009). *Natural Language Processing with Python.* O'Reilly Media.
4. Rathje et al. (2024). GPT is an effective tool for multilingual psychological text analysis. *PNAS.*
5. OpenAI (2024). *GPT-4 Technical Report.*

---

<p align="center">
  <em>In an age of AI-mediated discovery, <strong>GEO is the new SEO.</strong></em>
</p>
```
