# MSCS 634 – Lab 2  
**Title:** Exploring K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) on the Wine Dataset  
**Name:** Aryan Shrestha  

---

### **Purpose of the Lab**
The purpose of this lab is to explore and compare the performance of two classification algorithms — **K-Nearest Neighbors (KNN)** and **Radius Neighbors (RNN)** — using the **Wine dataset** from scikit-learn.  
By varying parameters such as the number of neighbors (*k*) and the radius distance, the lab demonstrates how these hyperparameters affect model accuracy and helps identify optimal values for classification tasks.

---

### **Key Insights and Observations**
- **KNN achieved higher and more consistent accuracy** across different *k* values. The best results were observed when *k* was between 5 and 15, where the model balanced noise sensitivity and generalization.
- **RNN performance was less stable**, largely depending on the choice of radius. Smaller radii occasionally resulted in “empty neighborhoods,” while larger radii included too many samples, reducing accuracy.
- The **accuracy trend plots** showed that KNN’s accuracy curve had a clear peak, whereas RNN’s curve fluctuated with radius size. This indicates that **KNN is generally easier to tune and more robust** for structured datasets like Wine.
- When features are standardized, KNN tends to perform better because it relies on relative distance, while RNN can be more sensitive to feature scale and data density.

---

### **Challenges and Decisions**
- **Empty neighborhood issue in RNN:** The Radius Neighbors Classifier occasionally found no points within the specified radius. To handle this, the `outlier_label` parameter was set to the most common class label.
- **Scaling choice:** KNN was implemented with **StandardScaler** to normalize features, but RNN was intentionally run on **raw features** to match the large radius values specified in the instructions.
- **Parameter sensitivity:** KNN’s *k* value was easy to interpret and tune, while RNN required careful adjustment of radius size and data scaling for meaningful performance.
- **Result interpretation:** Large radius values in RNN blurred class boundaries, illustrating why KNN is often the more practical choice for datasets with balanced density and distinct clusters.

---

### **Conclusion**
Overall, **KNN outperformed RNN** in both stability and accuracy on the Wine dataset.  
KNN is preferable for most structured datasets due to its consistent performance and intuitive parameter tuning, while RNN may be advantageous for tasks where data density varies significantly or when adaptive distance-based classification is needed.
