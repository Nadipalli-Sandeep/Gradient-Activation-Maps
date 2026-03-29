# 🔍 Gradient Activation Map Analysis (3D vs 2D vs 1D)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/14E7P9t3T6sbeKjvS5DXhBxPgcsZfgNxd?usp=sharing)

👉 Click the badge above to run the notebook instantly in Google Colab

---

## 🎯 Objective

This project explores how gradient-based explanations behave across different signal representations for the **same image**:

* **3D Signal** → Object Detection using Transformer (DETR)
* **2D Signal** → Image Classification using Vision Transformer (ViT)
* **1D Signal** → RGB Histogram representation

---

## 🧠 Models Used

* **DETR (Transformer-based Object Detection)**
* **Vision Transformer (ViT-B/16)**
* **MLP (for 1D histogram signal)**

---

## 🖼️ Input Image

![Input Image](images/input.png)

---

# 📊 Results & Analysis

---

## 🔹 1. 3D Signal — Object Detection (DETR + Grad-CAM)

![3D GradCAM](images/gradcam_3d_object_detection.png)

### 📌 Observations

* Captures **object-level spatial structure**
* Highlights **regions corresponding to detected objects**
* Attention distributed across **multiple objects in the scene**

---

## 🔹 2. 2D Signal — Classification (ViT + Grad-CAM)

![2D GradCAM](images/gradcam_2d_classification.png)

### 📌 Observations

* Focuses on **discriminative patches**
* Highlights key object regions (e.g., faces, edges)
* Coarser localization due to **patch-based processing (14×14 grid)**

---

## 🔹 3. 1D Signal — RGB Histogram

![Histogram](images/histogram_1d_signal.png)

![1D Gradient](images/gradcam_1d_histogram.png)

### 📌 Observations

* No spatial information ❌
* Captures only **color intensity importance**
* Cannot localize objects

---

## 🔹 4. Per-Channel Gradient Analysis (1D)

![Per Channel](images/1d_per_channel_saliency.png)

### 📌 Observations

* Different color channels contribute differently
* Peaks indicate **important intensity ranges**
* Still lacks spatial context

---

## 🔹 5. Statistical Comparison

![Stats](images/stats_all_signals.png)

### 📌 Insights

* **2D (ViT)** → Lowest entropy → most focused attention
* **1D (Histogram)** → Highest entropy → most dispersed
* **3D (DETR)** → Highest resolution → richest spatial detail

---

## 🔹 6. Final Comparison (All Signals)

![Final Comparison](images/comparison_all_signals.png)

### 📌 Key Insight

> Gradient-based explanations strongly depend on input representation.

---

# 🧠 Final Observations

* **3D (DETR)** captures full spatial and object-level structure
* **2D (ViT)** identifies important regions but at patch-level granularity
* **1D (Histogram)** loses all spatial structure and only reflects color importance

👉 Spatial information is **critical for meaningful interpretability**

---

# ⚠️ Limitations

* Grad-CAM is an **approximation for transformer-based models**
* Attention mechanisms are **not strictly equivalent** to gradient-based importance
* ViT explanations depend on **token reshaping into spatial grids**

---

# 🚀 How to Run

1. Click the **Colab badge** above
2. Upload any image
3. Run all cells

---

# 📁 Repository Structure

```
Gradient-Activation-Maps/
├── Gradient_Activation_Map_Analysis.ipynb
├── README.md
└── images/
```

---

# 👨‍💻 Author

**Nadipalli Jaya Sandeep**
M.Tech Data Science & AI
IIT Tirupati
