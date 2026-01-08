# Classical ML Failure Modes — FAANG-Level Hands-On (Titanic)

**Goal:** Learn the failure modes that actually break ML in production and in interviews: leakage, bias, spurious correlations, dataset shift, and improper validation.

**Outcome:** Students can detect leakage, design correct splits, debug spurious correlations, and build robust baselines.

---

# How to Start

1. **Fork** this repository.  
2. Open `failure_student_lab.ipynb` in **Google Colab**.  
3. Complete all **TODO** sections.  
4. **Restart runtime → Run All** cells.  
5. Push changes and submit a **Pull Request**.  

⚠️ **Do NOT edit notebooks directly on GitHub.**

---

## Lab Rules (FAANG Style)

- ✅ Treat validation as a product requirement: no leakage
- ✅ Always justify your split strategy
- ✅ Prefer simple baselines before fancy models
- ✅ Always do slice-based error analysis

---

# Out of Scope

- Kaggle leaderboard optimization
- Heavy feature engineering

---

# Notebook Rules

- Do **NOT** rename the notebook  
- Do **NOT** delete TODOs  
- Do **NOT** hardcode outputs  
- Notebook must run **top-to-bottom**  

---

# Dataset — Kaggle Titanic

We use the **Kaggle Titanic** dataset.

## Expected file path

Place the Kaggle files at:

- `data/titanic/train.csv`
- `data/titanic/test.csv` (optional for later)

## How to download

### Option A (Manual)

1. Kaggle: https://www.kaggle.com/competitions/titanic/data
2. Download `train.csv` and `test.csv`
3. Put them under `data/titanic/`

### Option B (Kaggle CLI)

- Install Kaggle CLI and configure credentials (Kaggle token).
- Download and unzip into `data/titanic/`.

---

## Section 1 — Baseline + Correct Validation

### Task 1.1: Define a minimal baseline

**Checkpoint Questions:**

- Why is a simple baseline useful?
- What does a “strong baseline” mean?

---

### Task 1.2: Split strategy

- Random split vs stratified split

**FAANG Gotcha:**

- If you tune on the validation set repeatedly, you overfit to it.

---

## Section 2 — Leakage

### Task 2.1: Create a leaky feature intentionally

**Checkpoint Questions:**

- What makes a feature “leaky”?
- How do you detect leakage quickly?

---

## Section 3 — Spurious Correlations

### Task 3.1: Analyze slice performance

- By sex, age bucket, passenger class

**Interview Angle:**

- Why can a model appear good overall but fail badly in slices?

---

## Section 4 — Dataset Shift / Drift (Toy simulation)

### Task 4.1: Simulate shift

- Train on one distribution, validate on shifted distribution

---

## Submission Expectations

- Completed notebook
- Written answers to checkpoint questions
- Evidence of at least 2 failure modes and how you mitigated them

---

## FAANG Interview Evaluation Rubric

| Skill                         | Evaluated |
|------------------------------|-----------|
| Leakage detection             | ✅        |
| Validation discipline         | ✅        |
| Slice-based error analysis    | ✅        |
| Reasoning clarity             | ✅        |
| Baseline thinking             | ✅        |

---

## Stretch Problems (Optional)

- GroupKFold-style validation by `Ticket` or `Cabin` prefix (proxy for family groups)
- Compare calibration before/after (ECE)
- Create a drift monitor metric
