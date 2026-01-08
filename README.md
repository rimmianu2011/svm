# Support Vector Machines (Interview Level) — FAANG-Level Hands-On

**Goal:** Build strong intuition for max-margin classification, kernels, and when SVMs fail.

**Outcome:** Students can:
- explain hard vs soft margin,
- understand hinge loss and margin,
- train LinearSVC/SVC in sklearn,
- reason about scaling, C, kernels, and failure modes.

---

# How to Start

1. **Fork** this repository.  
2. Open `svm_student_lab.ipynb` in **Google Colab**.  
3. Complete all **TODO** sections.  
4. **Restart runtime → Run All** cells.  
5. Push changes and submit a **Pull Request**.  

⚠️ **Do NOT edit notebooks directly on GitHub.**

---

## Lab Rules (FAANG Style)

- ✅ Always standardize features before SVM
- ✅ Compare linear vs RBF kernel
- ✅ Explain the role of `C` (regularization / margin)
- ✅ Separate decision boundary intuition from probability calibration (SVM is not probabilistic by default)

---

# Out of Scope

- Full dual optimization derivations
- SMO algorithm implementation

---

# Notebook Rules

- Do **NOT** rename the notebook  
- Do **NOT** delete TODOs  
- Do **NOT** hardcode outputs  
- Notebook must run **top-to-bottom**  

---

# Dataset

- Synthetic 2D datasets:
  - linearly separable
  - overlapping (soft margin)
  - XOR (needs kernel)

## Why?

- Makes margin and kernel behavior visually intuitive

---

## Section 1 — Margin + Hinge Loss

### Task 1.1: Compute hinge loss for a batch

Hinge loss (binary labels y in {-1, +1}):

`L = mean(max(0, 1 - y * (w·x + b)))`

**Checkpoint Questions:**

- Why does hinge loss encourage a margin?
- What happens when a point is correctly classified but inside the margin?

---

## Section 2 — Linear SVM in sklearn

### Task 2.1: Train LinearSVC with different C

**FAANG Gotcha:**

- Large C => low regularization (can overfit); small C => wider margin (more bias)

---

## Section 3 — Kernel SVM

### Task 3.1: XOR dataset

- Show linear SVM fails
- Show RBF kernel succeeds

**Interview Angle:**

- Why do kernels help? (implicit feature map)

---

## Section 4 — Failure Modes

### Task 4.1: Scaling + outliers

- show SVM sensitivity if features are unscaled

### Task 4.2: Probability calibration note

- SVM scores are margins, not calibrated probabilities

---

## Submission Expectations

- Completed notebook
- Short answers to checkpoint questions
- Results for linear vs RBF and C sweep

---

## FAANG Interview Evaluation Rubric

| Skill                    | Evaluated |
|--------------------------|-----------|
| Margin intuition         | ✅        |
| Hyperparameter reasoning | ✅        |
| Kernel intuition         | ✅        |
| Scaling awareness        | ✅        |
| Code correctness         | ✅        |

---

## Stretch Problems (Optional)

- Compare `LinearSVC` vs `SVC(kernel='linear')`
- Implement simple Platt scaling (conceptually)
- Visualize support vectors and margin width
