# [WIP] 🛒 E-commerce Customer Churn Prediction

*A machine learning model to identify at-risk customers with **92.5% accuracy**, enabling proactive retention strategies.*

## 📊 Model Performance

### **Key Metrics**
| Metric          | Score    | Interpretation                                                                 |
|-----------------|----------|-------------------------------------------------------------------------------|
| **Accuracy**    | 0.9251   | **92.5%** of predictions are correct overall.                                |
| **Precision**   | 0.7417   | When predicting churn, **74.2%** are truly at risk (low false positives).     |
| **Recall**      | 0.8318   | Captures **83.2%** of actual churners (low false negatives).                 |
| **F1-Score**    | 0.7841   | Balanced measure of precision and recall.                                     |
| **ROC AUC**     | 0.9623   | **96.2%** ability to distinguish churners from non-churners (excellent).     |

### **Confusion Matrix Breakdown**
|                | Predicted: Not Churn | Predicted: Churn |
|----------------|-----------------------|------------------|
| **Actual: Not Churn** | 516 (True Negatives)  | 31 (False Positives) |
| **Actual: Churn**     | 18 (False Negatives)  | 89 (True Positives)  |

**Business Impact:**  
- Correctly identified **89/107 churners** (83.2% recall).  
- Minimized false alarms (**31 false positives** out of 120 churn predictions).  

---

## 🚀 How to Use
1. **Predict Churn Risk**  
   ```python
   from model import predict_churn
   # Sample customer features
   customer_data = {
       'total_purchases': 15,
       'avg_order_value': 120.50,
       'days_since_last_login': 30
   }
   churn_risk = predict_churn(customer_data)  # Returns probability (0-1)
   ```

2. **Interpret Results**  
   - Probability ≥ 0.5 → High churn risk (trigger retention offer).  
   - Probability < 0.5 → Low risk (monitor periodically).  

---

## 📈 Performance Insights
- **Strength:** Exceptional at ranking customers by risk (ROC AUC = 0.96).  
- **Limitation:** Precision (74.2%) means ~1 in 4 flagged customers may be false alarms.  
- **Recommended Actions:**  
  - Focus on **high-probability churners** (≥0.7) for targeted campaigns.  
  - Combine with **customer lifetime value (CLV)** to prioritize high-value accounts.  

---

## 🔧 Technical Details
**Model:** Random Forest Classifier  
**Features Used:**  
- Purchase frequency  
- Session duration  
- Customer support interactions  
- Discount redemption rate  

**Dependencies:**  
```python
scikit-learn==1.4.2
pandas>=2.0.0
```
