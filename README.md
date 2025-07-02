# 🧠 K-Nearest Neighbors (KNN) on MNIST & Curse of Dimensionality Analysis

This project applies the **K-Nearest Neighbors (KNN)** algorithm to the **MNIST handwritten digit dataset** and investigates the limitations of KNN in high-dimensional spaces, commonly known as the **curse of dimensionality**.

---

## 📌 Project Highlights

### 1. 🖼️ KNN on MNIST (`KNNonMNIST.ipynb`)
- Implemented a **from-scratch KNN classifier** using NumPy.
- Evaluated performance for:
  - **k = 1** → Misclassification Rate: **3.09%**
  - **k = 3** → Misclassification Rate: **2.94%**
- **Total Inference Time**: `3148.6891 seconds` (~52 minutes)

🔍 **Insight**:
> Despite relatively low misclassification rates, the KNN algorithm is **extremely slow** when using brute-force distance computations, especially for large datasets like MNIST (60,000 training × 10,000 testing). This highlights a key drawback of KNN in practice.

---

### 2. 🧮 Curse of Dimensionality Analysis

This part of the project explores how the concept of "closeness" breaks down in high-dimensional spaces by simulating **random sampling from a unit cube**.

#### 📓 Files:
- **`KNNDimensionalityCurse.ipynb`**
  - Samples 1,000 random points from the unit cube across various dimensions.
  - Calculates and compares:
    - Mean of pairwise distances
    - Standard deviation of pairwise distances
  - Demonstrates how both metrics evolve as dimensions increase.
  - Concludes that the contrast between "nearest" and "farthest" neighbors shrinks with dimension.

- **`KnnDimensionalityCurseStatisticalAnalysis.pdf`**
  - A formal statistical report that supports the notebook with theoretical derivations.
  - Highlights how uniform distributions behave as dimensions scale.
  - Strengthens the experimental conclusions with mathematical backing.

---

## 📁 Project Structure
```.
├── KNNonMNIST.ipynb                          # Main notebook: KNN on MNIST + misclassification analysis
├── KNNDimensionalityCurse.ipynb              # Notebook: Curse of dimensionality via sampling
├── KnnDimensionalityCurseStatisticalAnalysis.pdf  # PDF report with formal statistical analysis
└── README.md                                 # This file
```


---

## 📊 Summary of Results

| k-Value | Misclassification Rate | Inference Time     |
|--------:|------------------------:|--------------------:|
| **k = 1** | 3.09%                  | (~52 min) |
| **k = 3** | 2.94%                  | (~52 min) |

> ⏳ **Conclusion**: Brute-force KNN, while accurate, is **not scalable** for large datasets without optimization.

---

## 📌 Key Takeaways

- ✅ **KNN Accuracy** is decent for MNIST.
- ❌ **Performance** is a major limitation due to O(n) search time per query.
- ⚠️ **Curse of Dimensionality**:
  - In high-dimensional spaces, distances become less meaningful.
  - The ratio of min/max distances tends to 1 → weakens KNN's ability to distinguish neighbors.

---

## 🚀 Potential Improvements

- Apply **PCA** or other **dimensionality reduction** techniques before using KNN.
- Use **efficient data structures** like KD-Trees or Ball Trees for neighbor search.
- Explore **approximate nearest neighbor** methods like **FAISS**, **Annoy**, or **HNSW**.
- Move to **scikit-learn's optimized KNN** or **GPU-accelerated libraries**.

---

## 📬 Contact

For questions, improvements, or feedback, feel free to reach out or open an issue.

---

## 📚 References

- MNIST Dataset: [http://yann.lecun.com/exdb/mnist/](http://yann.lecun.com/exdb/mnist/)
- Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
- Beyer et al. (1999). *When Is “Nearest Neighbor” Meaningful?*. In: ICDT.

---