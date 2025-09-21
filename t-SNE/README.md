# 🔍 t-SNE Visualizations: Strategic Selection from 100 Available Files

This folder contains **15 carefully selected t-SNE visualizations** from **100 total available files** (20 models × 5 visualization types), representing the most scientifically impactful quantum feature space analyses.

## 📊 Strategic Selection Rationale

### 🎯 **Available vs Selected**
- **Total Available**: 100 t-SNE files across all trained models
- **Selected**: 15 files (15%) - Highly curated for maximum insight
- **Selection Criteria**: Performance diversity, scientific impact, interpretability

### ✅ **Selected Models (5 of 20)**

#### 🏆 **Deterministic Models (3 of 4 selected)**
```
✅ 4D_deterministic                    (AUC: 0.8891) - Best overall performance
✅ 8D_deterministic                    (AUC: 0.8269) - Strong deterministic
✅ 10D_deterministic                   (AUC: 0.8236) - High-dimensional analysis
❌ 6D_deterministic                    (AUC: 0.7995) - Excluded (redundant with others)
```

#### ⚡ **cuTensorNet Models (2 of 16 selected)**
```
✅ 8D_cuTensorNet_2048shots           (AUC: 0.6326) - Peak cuTensorNet performance
✅ 4D_cuTensorNet_512shots            (AUC: 0.5121) - Efficient baseline
❌ 14 other cuTensorNet variants      (AUC: 0.51-0.57) - Similar within shot ranges
```

### 🖼️ **Selected Visualization Types (3 of 5 per model)**
```
✅ tsne_quantum_predictions_holdout_true_labels     → *_holdout_predictions.png
✅ tsne_pca_reduced_true_labels                     → *_quantum_feature_space.png  
✅ tsne_quantum_predictions_comparison              → *_quantum_vs_classical.png
❌ tsne_original_features_true_labels               (Excluded - less quantum-specific)
❌ tsne_classical_predictions_comparison            (Excluded - covered in quantum_vs_classical)
```

## 📁 File Organization

### 🎯 **Deterministic Models**
```
4D_deterministic_holdout_predictions.png           (1.2MB) - Best model quality
4D_deterministic_quantum_feature_space.png         (3.3MB) - Quantum transformation
4D_deterministic_quantum_vs_classical.png          (4.2MB) - Decision boundaries

8D_deterministic_holdout_predictions.png           (1.2MB) - Strong performance
8D_deterministic_quantum_feature_space.png         (3.6MB) - Higher-dimensional space
8D_deterministic_quantum_vs_classical.png          (5.2MB) - Complex boundaries

10D_deterministic_holdout_predictions.png          (1.2MB) - High-dimensional quality
10D_deterministic_quantum_feature_space.png        (3.5MB) - Maximum dimension analysis
10D_deterministic_quantum_vs_classical.png         (4.8MB) - Dimensional effects
```

### ⚡ **cuTensorNet Models**
```
8D_cuTensorNet_2048shots_holdout_predictions.png   (1.2MB) - Peak GPU performance
8D_cuTensorNet_2048shots_quantum_feature_space.png (3.3MB) - Noise-robust features
8D_cuTensorNet_2048shots_quantum_vs_classical.png  (4.4MB) - Shot-based boundaries

4D_cuTensorNet_512shots_holdout_predictions.png    (1.3MB) - Efficient baseline
4D_cuTensorNet_512shots_quantum_feature_space.png  (3.3MB) - Minimal shot analysis
4D_cuTensorNet_512shots_quantum_vs_classical.png   (4.3MB) - Low-shot comparison
```

## 🔬 Scientific Insights from Selection

### 🎯 **Performance Spectrum Coverage**
- **Best (0.8891)** → **Good (0.8269)** → **High-dim (0.8236)** → **Peak GPU (0.6326)** → **Baseline (0.5121)**
- **Complete range** from quantum advantage to baseline performance
- **Both backends** represented (deterministic + shot-based)

### 📈 **Dimensional Analysis**
- **4D**: Optimal efficiency (both deterministic and cuTensorNet)
- **8D**: Peak performance for respective backends
- **10D**: High-dimensional effects and scaling

### ⚡ **Backend Comparison**
- **Deterministic**: Exact quantum simulation (no sampling noise)
- **cuTensorNet**: GPU-accelerated with sampling effects
- **Shot Analysis**: 512 (minimal) vs 2048 (optimal) shots

## 💡 **Interpretation Guide**

### 🔍 **What Each Visualization Shows**

#### **Holdout Predictions** (`*_holdout_predictions.png`)
- **Purpose**: Model quality on completely unseen data
- **Good Signs**: Tight, separated clusters by color
- **Concerning**: Mixed-color regions (classification errors)
- **Size**: ~1.2MB (compact, high-impact)

#### **Quantum Feature Space** (`*_quantum_feature_space.png`)
- **Purpose**: PCA-reduced quantum kernel representations
- **Shows**: How quantum transformation creates separability
- **Insight**: Non-linear quantum advantage visualization
- **Size**: ~3.5MB (detailed feature structure)

#### **Quantum vs Classical** (`*_quantum_vs_classical.png`)
- **Purpose**: Side-by-side decision boundary comparison
- **Shows**: Where quantum and classical models agree/disagree
- **Insight**: Quantum advantage regions identification
- **Size**: ~4.5MB (comprehensive comparison)

### 🎨 **Visual Elements**
- **🔵 Blue Points**: Qwen 2.5 generated text
- **🔴 Red Points**: Gemma 3 generated text
- **Clustering Quality**: Tighter = better separation = higher AUC
- **Decision Boundaries**: Quantum often shows non-linear advantages

## 📚 **Research Applications**

### 🔬 **For Researchers**
- **Quantum ML Validation**: Visual proof of quantum kernel advantages
- **Feature Engineering**: Understanding quantum transformation effects
- **Model Selection**: Visual guide for choosing optimal configurations

### 🎓 **For Education**
- **Quantum Concepts**: Intuitive understanding of quantum feature spaces
- **ML Interpretability**: Connecting quantitative metrics to visual patterns
- **Comparative Analysis**: Quantum vs classical decision-making visualization

### 💻 **For Practitioners**
- **Model Quality Assessment**: Quick visual validation of performance
- **Debugging**: Identifying classification problem regions
- **Performance Optimization**: Understanding dimensional trade-offs

## 🔗 **Related Analysis**

- **📊 Quantitative Metrics**: See [`../ROC/`](../ROC/) for numerical performance
- **🏗️ Model Artifacts**: See [`../models/`](../models/) for trained model files
- **📋 Technical Details**: See model `metadata.json` for training configurations

---

*These visualizations represent a strategic 15% selection from 100 available t-SNE files, chosen for maximum scientific impact and interpretability. They accompany the paper "Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights" by Kalin Kopanov, IICT-BAS.*

**Total Size**: 91MB (15 files) vs 1.8GB+ (100 files) - **95% size reduction** with **100% key insights preserved**
