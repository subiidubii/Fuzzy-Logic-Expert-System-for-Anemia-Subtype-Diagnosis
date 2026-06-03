# 🩸 Fuzzy Logic Expert System for Anemia Subtype Diagnosis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![scikit-fuzzy](https://img.shields.io/badge/Library-scikit--fuzzy-orange)
![Accuracy](https://img.shields.io/badge/Accuracy-91.43%25-success)

## 📌 Project Overview
Anemia is a complex physiological condition with overlapping clinical markers. Standard deterministic programming (rigid `if-else` thresholds) often fails to diagnose patients whose bloodwork falls on the borderline of multiple categories. 

This project implements an **8-Phase Mamdani Fuzzy Inference System (FIS)** to model clinical certainty as a mathematical continuum. By evaluating Complete Blood Count (CBC) parameters, the system accurately replicates a hematologist's deductive reasoning to classify patients into three specific subtypes:
* **Group A:** Iron Deficiency / Thalassemia (Microcytic)
* **Group B:** Anemia of Chronic Disease (Normocytic)
* **Group C:** B12/Folate Deficiency (Macrocytic)

## 🧠 Core AI & Mathematical Concepts
This expert system leverages several advanced fuzzy logic and data engineering concepts:
* **Mamdani Inference Engine:** Evaluates 21 distinct expert rules using `skfuzzy.control` to process ambiguous physiological data.
* **Fuzzy Membership Functions:** * **Trapezoidal (`trapmf`):** Used to model extreme boundaries (e.g., severe low/high ranges) with a flat shoulder of 100% membership.
  * **Triangular (`trimf`):** Applied to central "Normal" physiological ranges to provide a sharp peak that minimizes accidental cross-firing between neighboring fuzzy sets.
* **Complex Rule Matrix:** Implements *Activation Rules* (boosting confidence on matching signatures), *Penalty Rules* (cross-suppressing incorrect groups), and *Safety Rules* (preventing false-positives in healthy patients).
* **Centroid Defuzzification:** Translates the aggregated geometric fuzzy outputs back into crisp, readable confidence percentages (0-100%).

## 🛠️ Tech Stack & Libraries
* **`scikit-fuzzy` (`skfuzzy`)**: The core library utilized for building the universe of discourse, membership functions, and the fuzzy rule base.
* **`pandas` & `numpy`**: For data ingestion, missing value handling (median imputation), and numerical processing.
* **`matplotlib`**: For visualizing feature distributions and rule activation confidence bars.

## 📊 Performance & Evaluation
The system was evaluated on a curated clinical dataset of non-borderline patients. By prioritizing fuzzy hematological markers over rigid human labels, the system successfully navigated ambiguous boundaries (such as shrinking cells in early Iron Deficiency).

* **Overall Accuracy:** 91.43%
* **Recall (Group A - Microcytic):** 100%
* **Precision (Group C - Macrocytic):** 100%

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/subiidubii/Anemia-Fuzzy-Expert-System.git](https://github.com/subiidubii/Anemia-Fuzzy-Expert-System.git)
