
# 🩺 Uncertainty-Aware Healthcare Machine Learning Project

## Overview

Most healthcare machine learning (ML) case studies stop after reporting high accuracy or AUC (often ~95%) and assume the model is reliable. This project takes a different approach.

Instead of asking **"How accurate is the model?"**, this project asks:

> **When should we *not* trust a model, even if it performs well overall?**

The goal is not diagnosis or treatment recommendation, but **risk-aware evaluation** — identifying regions where ML predictions are unstable, uncertain, or potentially harmful if automated.

---

## Dataset

* **Wisconsin Diagnostic Breast Cancer Dataset**
* Publicly available and de-identified
* 30 numeric tumor features derived from cell nuclei measurements
* Binary outcome: Benign (B) vs Malignant (M)

---

## Approach

The analysis follows a decision-focused evaluation pipeline:

* Built baseline and full-feature ML models (Logistic Regression)
* Quantified feature instability using variability measures
* Measured internal disagreement between feature summaries (mean vs worst)
* Combined these signals into an **uncertainty score**
* Grouped cases into **decision risk profiles**:

  * Low risk (stable)
  * Moderate risk (review required)
  * High risk / gray zone (automation should be deferred)
* Evaluated model errors and false negatives by risk zone
* Performed robustness checks beyond global accuracy

---

## Key Findings

* High overall accuracy does **not** imply uniform decision safety
* Decision **fragility** emerges near model boundaries, where small changes in features can flip predictions
* An explicit **uncertainty score** (derived from instability and internal disagreement) helps surface these fragile cases
* Cases can be meaningfully grouped into **risk profiles** (low, moderate, high/gray zone) with distinct error behaviors
* False negatives concentrate disproportionately in **moderate-risk regions**, not always in the obvious gray zone
* An **evaluation matrix** is designed that links uncertainty, instability, and harm direction provides clearer guidance than accuracy alone
* Increasing model complexity improves AUC but does not eliminate uncertainty-driven failure modes

---

## Why This Matters

In high-stakes domains such as healthcare, silent model failures can lead to unnecessary harm. This project demonstrates that:

* Accuracy metrics alone are insufficient for deployment decisions
* Uncertainty-aware evaluation helps identify where human oversight is mandatory
* Responsible ML requires knowing when to **stop automation**, not just how to optimize models

---

## Scope & Ethics

* This project is exploratory and educational
* It does **not** provide medical diagnosis or treatment recommendations
* ML is treated as decision-support, not a decision-maker
* Clinical judgment and human oversight take precedence in uncertain or high-risk cases
  
📄 Ethical considerations and usage boundaries are documented in `ETHICAL_SCOPE.md`.

---

## Repository Structure
- `uncertainty_aware_evaluation.ipynb` – main analysis notebook
- `ETHICAL_SCOPE.md` – ethical scope and usage boundaries
- `docs/` – results summaries and figures (to be added)

---

## Attribution & Usage

If you reference, adapt, or build upon the ideas or evaluation framework presented in this repository, please cite this repository and acknowledge the author. While the code is released under the MIT License, the conceptual framing and analysis are intended to be credited when reused.

## Author

**Bhargavi Chakrapani**
Healthcare Analytics | Responsible AI | Decision Intelligence

---

## License

MIT License



