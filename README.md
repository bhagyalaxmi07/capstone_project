# 🎓 Student Engagement Intelligence System

> LMS + Behavior → Learning → Placement | Built with Python + Streamlit

---

## 📁 Project Structure

```
student_engagement/
├── data/
│   └── student_data_engament_Project_8.csv   ← PUT YOUR CSV HERE
├── models/                                    ← Auto-created on training
├── assets/                                    ← Auto-created (plots saved here)
├── utils/
│   └── data_loader.py                         ← Data cleaning + feature engineering
├── config.py                                  ← All constants and column names
├── eda.py                                     ← Exploratory Data Analysis
├── train_model.py                             ← ML pipeline (train + save)
├── app.py                                     ← Streamlit Dashboard
├── requirements.txt
└── README.md
```

---

## ⚙️ Setup (One-Time)

```bash
# 1. Create virtual environment
python -m venv venv

# 2. Activate it
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
```

---

## 🗂️ Step 1 — Add Dataset

Download the dataset and place it here:
```
data/student_data_engament_Project_8.csv
```

Dataset URL:
```
https://raw.githubusercontent.com/pragyanaischool/VTU_Internship_DataSets/refs/heads/main/student_data_engament_Project_8.csv
```

---

## 🔬 Step 2 — Run EDA

```bash
python eda.py
```

**What it does:**
- Cleans data, engineers features, generates segments
- Saves 5 publication-quality plots to `assets/`
- Prints key statistical insights to terminal

**Outputs:**
| File | Content |
|------|---------|
| `assets/01_overview.png` | Placement distribution, segments, dept analysis |
| `assets/02_engagement_vs_placement.png` | Core metrics vs placement |
| `assets/03_composite_scores.png` | Engagement/Readiness scores |
| `assets/04_correlation_heatmap.png` | Feature correlations |
| `assets/05_risk_matrix.png` | Attendance × Quiz risk matrix |

---

## 🤖 Step 3 — Train ML Model

```bash
python train_model.py
```

**What it does:**
- Compares 3 models: Logistic Regression, Random Forest, Gradient Boosting
- Handles class imbalance with SMOTE
- Selects best model by CV ROC-AUC score
- Saves model to `models/placement_model.pkl`

**Outputs:**
| File | Content |
|------|---------|
| `models/placement_model.pkl` | Trained model artifact |
| `assets/06_model_evaluation.png` | Confusion matrix + ROC curve + feature importance |
| `assets/07_model_comparison.png` | Model comparison bar chart |

---

## 📊 Step 4 — Run Dashboard

```bash
streamlit run app.py
```

Open browser at: **http://localhost:8501**

### Dashboard Pages:
| Page | What You See |
|------|-------------|
| 🏠 Overview | KPIs, placement pie, segment breakdown |
| 📊 Engagement Analysis | Attendance, login, time spent analysis |
| 🧠 Learning Analytics | Quiz scores, video completion, effectiveness |
| 💬 Interaction Insights | Doubts, events, peer discussions |
| 🚨 Risk Detection | At-risk heatmap + exportable student list |
| 🏆 Leaderboard | Top students ranked by engagement + radar chart |
| 🔮 Placement Predictor | Input any student data → get placement probability |

---

## 🧠 Feature Engineering

| Feature | Formula |
|---------|---------|
| `Attendance_Score` | `Attendance_% / 100 × 25` |
| `Activity_Score` | `(Login + Time + ActiveDays) / 3 × 25` |
| `Learning_Score` | `(Video_Completion + Quiz_Score) / 2 × 25` |
| `Interaction_Score` | `(Doubts + Events + Peers) / 3 × 25` |
| `Engagement_Score` | `Sum of all 4 scores (0–100)` |
| `Learning_Effectiveness` | `Quiz_Score × Video_Completion / 100` |
| `Placement_Readiness` | `Engagement×0.5 + Effectiveness×0.3 + Interaction×0.2` |

---

## 🏷️ Student Segments

| Segment | Criteria | Action |
|---------|---------|--------|
| 🏆 High Performer | High engagement + quiz + doubts | Placement ready |
| 📺 Passive Learner | High activity, low interaction | Encourage doubts |
| 🤔 Active but Confused | High activity, low quiz score | Needs mentoring |
| 🚨 Disengaged | Low everything | High dropout risk |

---

## 📬 Contact
Built for PragyanAI — VTU Internship Project

# capstone_project
