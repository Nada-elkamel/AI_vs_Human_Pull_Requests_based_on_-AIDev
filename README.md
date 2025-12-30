# AI vs Human Pull Requests: An Empirical Study on GitHub

This repository contains the data processing scripts and analysis pipeline used in the paper:

**“The Visibility–Acceptance Paradox: A Large-Scale Study of AI-Generated Pull Requests in Open-Source Software”**

The project investigates how **AI-generated pull requests (PRs)** compare to **human-generated PRs** in terms of:
- processing speed,
- community feedback,
- and acceptance (merge likelihood).

---

## 📌 Research Motivation

Autonomous AI agents are now capable of submitting pull requests without human intervention.  
While these contributions are technically valid and highly active, their integration into open-source communities remains unclear.

This project aims to answer the following question:

> **Do AI-generated pull requests perform as well as human pull requests in real open-source workflows?**

---

## 🔬 Research Questions

The study is structured around three research questions:

### RQ1 – Speed  
Are AI-generated PRs processed faster than human PRs?
- Time to first comment
- Time to first review
- Total PR duration

### RQ2 – Feedback  
Do AI PRs receive different feedback compared to human PRs?
- Number of comments
- Review approval rate
- Average comment length

### RQ3 – Acceptance  
Are AI PRs more likely to be merged, and in what contexts?
- Merge rate
- Number of commits
- Linkage to GitHub issues

---

## 📊 Dataset

This project uses the **AIDev dataset**:

> Li et al., *AIDev: A Dataset of AI Agent Contributions to GitHub*, 2025.

The dataset includes:
- pull requests
- users
- comments
- reviews
- commits
- related issues

**Scale of analysis:**  
📦 **932,791 pull requests**

### Author Classification
- PRs are labeled as **AI-generated** if the author login contains `"bot"` (case-insensitive)
- Otherwise, PRs are labeled as **human-generated**

---

## 🧠 Key Findings

The analysis reveals a phenomenon called the **Visibility–Acceptance Paradox**:

- AI PRs receive **faster initial reactions**, often from automated tools.
- They attract **more comments** and are **more frequently linked to issues**.
- However, they:
  - stay open significantly longer,
  - and are **merged less often** than human PRs.

This suggests that AI agents are technically active but struggle with **social integration** in open-source communities.

---

## 🛠️ Project Structure

```text
.
├── data/
│   ├── raw/                  # Raw AIDev tables (PRs, comments, reviews, etc.)
│   └── processed/            # Cleaned and merged datasets
│
├── scripts/
│   ├── build_analysis_table.py   # Builds PR-level analysis table
│   ├── compute_metrics.py        # Computes RQ1–RQ3 metrics
│
├── results/
│   ├── figures/              # Plots and visualizations
│   └── tables/               # Aggregated result tables
│
├── aidev_analysis_ready_table.parquet
├── README.md
└── paper/
    └── main.tex               # LaTeX paper
