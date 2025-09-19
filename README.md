# Bank Marketing Dataset – SVM Classification  

This project applies **Support Vector Machines (SVM)** to the **Bank Marketing Dataset** (UCI / Kaggle) to predict whether a customer subscribes to a term deposit after a marketing campaign.  

---

## Dataset & Preprocessing  

- Source: [Bank Marketing Dataset (UCI)](https://archive.ics.uci.edu/ml/datasets/bank+marketing)  
- Target variable: **`y`** (1 = subscribed, 0 = not subscribed)  

### Preprocessing Steps  
1. Converted `y` into binary (`yes → 1`, `no → 0`).  
2. Applied **one-hot encoding** (via `pd.get_dummies`) to categorical features (`job`, `marital`, `education`, etc.).  
3. Left numeric features (`age`, `balance`, `duration`, etc.) unchanged.  
4. Standardized numeric features before training SVM.  
5. Split dataset into **train/test (80/20)**.  

---

## 🧠 Models Evaluated  

1. **Linear SVM (unweighted)**  
2. **RBF SVM**  
3. **Polynomial SVM**  
4. **Linear SVM with class weights (`class_weight="balanced"`)**  

---

## 📈 Results  

### Linear SVM (Unweighted)  
- Accuracy: **90.5%**  
- Recall (class 1): 0.34  
- Strong accuracy, but weak at detecting subscribers.  

### RBF SVM  
- Accuracy: **89.5%**  
- Recall (class 1): 0.21  
- Slightly worse recall than Linear.  

### Polynomial SVM  
- Accuracy: **89.5%**  
- Recall (class 1): 0.22  
- Similar to RBF, still poor subscriber detection.  

### Linear SVM with Class Weights  
- Accuracy: **85.8%**  
- Recall (class 1): **0.88**  
- Precision (class 1): 0.44  
- Much better subscriber detection, though with more false positives.  

