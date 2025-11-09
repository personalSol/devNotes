---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-09T13:00
---
---

![[Pasted image 20251109123559.png]]
![[Pasted image 20251109123912.png]]

### 🧩 Model Testing, Overfitting & Underfitting

**Model testing** is always done on **test data** — data the model has **never seen before**.

Both **underfitting** and **overfitting** are examples of a model that has **not generalized well**.

---

### ⚙️ Ideal Model Behavior

- An **ideal model** should have **slightly lower accuracy on the test set** than on the training set.
- If test accuracy is **much lower**, → **underfitting** or **overfitting**.
- If training accuracy is **much higher** than test accuracy → **overfitting**.
- If both are **low**, → **underfitting** (model not trained well or too simple).

---

### 📉 Underfitting

- Happens when the model is **too simple** or **not trained enough**.
- also happens when the training data has different features that test data
- It **fails to learn important patterns**, leading to **poor accuracy** on both training and test data.
- to fix/avoid underfitting:
	- train longer
	- increase hyperparameters
	- reduce amount of features
	- try a different model

---

### 📈 Overfitting

- Happens when the model is **too complex** or has **seen test data (data leakage)**.
- It **memorizes** the training data instead of learning **general patterns**.
- Shows **very high accuracy on training data** but **poor performance on new (test) data**.
- No model is perfect — if it performs **too perfectly**, it’s a sign of possible **overfitting or data leakage**(memorization).
- to fix/avoid overfitting:
	- collect more data
	- try a less advanced model

---

### 🧠 Summary Table

|Type|Training Accuracy|Test Accuracy|Cause|Key Idea|
|---|---|---|---|---|
|**Underfitting**|Low|Low|Model too simple or not trained enough|Didn’t learn patterns → bad on all data.|
|**Good Fit (Ideal)**|High|Slightly lower|Right complexity, good training|Learns general patterns → works well on new data.|
|**Overfitting**|Very High|Much lower|Too complex or data leakage|Memorizes training data → fails on new data.|

---

### ⚡ Quick Summary

- ✅ Use **unseen test data** for real testing.
- ⚖️ Small gap between train & test = **good generalization**.
- ❌ Large gap = **overfitting**.
- ❌ Both low = **underfitting**.
- one best performance metric doesn't mean the best modal. Sometimes model with higher accuracy may take more time but our requirements are for a faster model even if not that much accurate. 

---

