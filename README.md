
## 🚗 License Plate Recognition (LPR): A Comparative Analysis of Three OCR Approaches

This project presents a comparative study of **three License Plate Recognition (LPR) models** using different OCR engines and preprocessing techniques. It highlights strengths, weaknesses, and accuracy across multiple datasets with varying difficulty.

---

### 📌 Objectives

* Evaluate performance of different OCR-based LPR models.
* Analyze effects of preprocessing on recognition accuracy.
* Provide implementation guidance for different LPR use cases.

---

### ⚙️ Models Compared

#### **Model 1: PaddleOCR with Advanced Preprocessing**

* **OCR Engine**: PaddleOCR (with angle classification)
* **Pipeline**: Multi-stage preprocessing
* **Steps**:

  * Grayscale conversion
  * Image resizing (2x)
  * Bilateral filter
  * Gaussian blur
  * Adaptive thresholding
  * Morphological ops
  * Canny edge detection & dilation
* **Strengths**: Works well on challenging images.
* **Weaknesses**: Computationally heavy, may overprocess.

---

#### **Model 2: EasyOCR with Minimal Preprocessing**

* **OCR Engine**: EasyOCR
* **Pipeline**: Lightweight preprocessing
* **Steps**:

  * Accurate cropping
  * Best candidate selection logic (5–13 characters)
* **Strengths**: Highest overall accuracy (83%), simple, fast.
* **Weaknesses**: Adds spaces between characters.

---

#### **Model 3: PaddleOCR with IVP (Image Vision Processing)**

* **OCR Engine**: PaddleOCR (with angle classification)
* **Pipeline**: Balanced preprocessing
* **Steps**:

  * Grayscale
  * Histogram equalization
  * Gaussian blur
  * Morphological closing
  * Canny edge detection
* **Strengths**: Simple and interpretable.
* **Weaknesses**: Lowest accuracy on difficult datasets.

---

### 📊 Performance Summary

| Model                  | Dataset 1  | Dataset 2  | Dataset 3  | Overall Accuracy |
| ---------------------- | ---------- | ---------- | ---------- | ---------------- |
| **Model 1** (Advanced) | 43.3%      | 47.73%     | 26.67%     | **42%**          |
| **Model 2** (EasyOCR)  | **73.33%** | **90.91%** | **76.67%** | **83%**          |
| **Model 3** (IVP)      | 31.28%     | 36%        | 23.33%     | **30%**          |

---

### 🔍 Key Observations

* **Model 2 (EasyOCR)** consistently outperforms others in all datasets.
* **Model 1** performs best on the most challenging dataset due to advanced preprocessing.
* **Model 3** underperforms despite a balanced pipeline.

---

### 📌 Dataset-Level Insights

| Dataset   | Description               | Best Model                   |
| --------- | ------------------------- | ---------------------------- |
| Dataset 1 | Clean images              | Model 2 (EasyOCR)            |
| Dataset 2 | Medium difficulty         | Model 2 (EasyOCR)            |
| Dataset 3 | Challenging (noise, blur) | Model 1 (PaddleOCR Advanced) |

---

### ⚖️ Strengths & Weaknesses

#### **Model 1: PaddleOCR + Advanced Preprocessing**

* ✅ Comprehensive, handles poor images
* ❌ Complex & slower, risk of feature loss

#### **Model 2: EasyOCR + Simple Preprocessing**

* ✅ Best accuracy, fast, robust
* ❌ Minor spacing issues in output

#### **Model 3: PaddleOCR + IVP**

* ✅ Simple pipeline with visual tools
* ❌ Struggles on noisy/complex images

---

### 🧠 Why Model 2 Wins

* Efficient and clean preprocessing
* Strong OCR recognition and candidate filtering
* Balanced character cleaning and length-based filtering

---

### 🧪 Use Case Recommendations

| Model       | Best For                                      |
| ----------- | --------------------------------------------- |
| **Model 2** | High-accuracy production systems, general use |
| **Model 1** | Research, educational projects, edge cases    |
| **Model 3** | Lightweight systems with basic OCR needs      |

---

### 🚀 Future Improvements

* Combine EasyOCR and PaddleOCR into a hybrid model
* Add:

  * Adaptive preprocessing based on image quality
  * Perspective correction
  * Super-resolution enhancement
  * Plate format validation
* Ensemble predictions across models

---

### ✅ Conclusion

* **Model 2 (EasyOCR)** is the best general-purpose model (83% accuracy).
* **Model 1** is more suitable for harder conditions but is slower.
* **Model 3** offers simplicity but requires improvement.
* Dataset quality and preprocessing significantly impact results.
* A **hybrid approach** could yield optimal results across diverse inputs.

---

### 📁 Repository Contents

```
📂 datasets/         → Datasets with license plate images
📂 models/           → OCR logic and preprocessing pipelines
📂 results/          → Inference output, metrics, visualizations
📜 comparative_analysis.md → Full technical report
📜 README.md         → This file
```

---

