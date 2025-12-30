# AI vs Human Pull Requests

This project compares **AI-generated pull requests** and **human-generated pull requests** on GitHub.

The goal is to understand how AI contributions are reviewed, discussed, and accepted in open-source projects.

---

## What is this project about?

Autonomous AI agents can now create pull requests by themselves.
They write code, fix issues, and submit changes without human help.

This project studies:
- How fast AI pull requests are reviewed
- How much feedback they receive
- How often they are merged compared to human pull requests

---

## Research Questions

1. **Speed**
   - Time to first comment
   - Time to first review
   - Total time before merge or close

2. **Feedback**
   - Number of comments
   - Review approval rate
   - Average comment length

3. **Acceptance**
   - Merge rate
   - Number of commits
   - Link to GitHub issues

---

## Dataset

We use the **AIDev dataset**, which contains GitHub activity such as:
- pull requests
- users
- comments
- reviews
- commits
- issues

Pull requests are labeled as:
- **AI** if the author username contains `bot`
- **Human** otherwise

Total analyzed pull requests: **932,791**

---

## Main Findings

- AI pull requests get **very fast initial comments**, mostly from automated tools.
- They receive **more comments** and are often linked to issues.
- However, they:
  - stay open longer
  - are merged less often than human pull requests

This behavior is called the **Visibility–Acceptance Paradox**.

---

## Project Structure

```text
.         
├── jupyter notebook       # Python analysis scripts    
├── README.md
└── paper          # LaTeX paper
