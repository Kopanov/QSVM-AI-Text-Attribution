# QSVM AI Text Attribution Models

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Models: 20](https://img.shields.io/badge/Models-20-blue.svg)]()
[![Python: 3.8+](https://img.shields.io/badge/Python-3.8+-green.svg)]()

Pre-trained Quantum Support Vector Machine models for AI-generated text attribution. Includes 20 models across 4D-10D quantum feature spaces using cuTensorNet and StatevectorSimulator backends.

## 🎯 Overview

This repository contains pre-trained Quantum Support Vector Machine (QSVM) models for distinguishing AI-generated text from different large language models. The models were trained on 4,640 training samples and validated on 1,160 hold-out samples, focusing on attribution between **Qwen 2.5** and **Gemma 3** generated text.

## 🔬 Research Paper

These models accompany the research paper:
**"Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights"**

*Author: Kalin Kopanov*  
*Institution: Institute of Information and Communication Technologies, Bulgarian Academy of Sciences*

## 📊 Model Performance Highlights

- **🏆 Best Performance**: 4D Deterministic (ROC-AUC: **0.8891**)
- **⚡ Noise Robustness**: 8D cuTensorNet shows peak performance (ROC-AUC: 0.6326)
- **🎯 Quantum Advantage**: Deterministic models achieve 80-89% accuracy on unseen test data
- **🧠 Feature Insights**: 14-17 of 18 linguistic features consistently important across models

## 📁 Model Organization

### 🎯 Deterministic Models (Exact Quantum Simulation)
- `models/4D_deterministic/` - **Best Performance** (ROC-AUC: 0.8891)
- `models/6D_deterministic/` - (ROC-AUC: 0.7995)
- `models/8D_deterministic/` - (ROC-AUC: 0.8269) 
- `models/10D_deterministic/` - (ROC-AUC: 0.8236)

### ⚡ cuTensorNet Models (GPU-Accelerated)
#### 4D Models:
- `models/4D_cuTensorNet_512shots/`, `models/4D_cuTensorNet_1024shots/`, `models/4D_cuTensorNet_2048shots/`, `models/4D_cuTensorNet_4096shots/`

#### 6D Models:
- `models/6D_cuTensorNet_512shots/`, `models/6D_cuTensorNet_1024shots/`, `models/6D_cuTensorNet_2048shots/`, `models/6D_cuTensorNet_4096shots/`

#### 8D Models:
- `models/8D_cuTensorNet_512shots/`, `models/8D_cuTensorNet_1024shots/`, `models/8D_cuTensorNet_2048shots/`, `models/8D_cuTensorNet_4096shots/`

#### 10D Models:
- `models/10D_cuTensorNet_512shots/`, `models/10D_cuTensorNet_1024shots/`, `models/10D_cuTensorNet_2048shots/`, `models/10D_cuTensorNet_4096shots/`

## 📈 Performance Analysis & ROC Curves

### 🎯 Complete Performance Benchmarks
This repository includes comprehensive performance analysis with ROC curves, PR-AUC metrics, and calibration scores for all 20 models.

**📊 [View Performance Visualizations →](ROC/)**

#### 🏆 Deterministic Models (StatevectorSimulator)
- **4D**: ROC-AUC **0.8891** (Best Overall Performance)
- **6D**: ROC-AUC **0.7995** 
- **8D**: ROC-AUC **0.8269**
- **10D**: ROC-AUC **0.8236**

#### ⚡ cuTensorNet Models (Shot-based, GPU-Accelerated)
- **4D**: Mean ROC-AUC **0.5121** (across 512-4096 shots)
- **6D**: Mean ROC-AUC **0.5167** (across 512-4096 shots)
- **8D**: Mean ROC-AUC **0.6326** (Peak cuTensorNet Performance)
- **10D**: Mean ROC-AUC **0.5705** (across 512-4096 shots)

#### 📊 Key Performance Insights
- **Quantum vs Classical**: Linear SVM baseline achieves ROC-AUC ≈ 0.999
- **Shot Stability**: cuTensorNet performance remarkably stable across shot counts
- **Dimensional Sweet Spot**: 4D deterministic and 8D cuTensorNet show optimal performance
- **Noise Robustness**: 8D cuTensorNet demonstrates superior resilience to sampling noise

### 📁 ROC Analysis Contents
```
ROC/
├── 🖼️ QSVM_ROC_StatevectorSimulator_all_dimensions.png
├── 🖼️ QSVM_ROC_cuTensorNet_all_dimensions.png  
├── 🖼️ QSVM_ROC_cuTensorNet_k[4,6,8,10]_mean.png (individual dimensions)
├── 📊 Performance summaries with exact AUC values
└── 📈 PR-AUC and Brier score analysis with 95% confidence intervals
```

## 🔍 Feature Space Visualizations (t-SNE)

### 🎯 Quantum Feature Space Analysis
Explore how quantum kernels transform text features into separable representations with t-SNE visualizations of 5 key models.

**🖼️ [View t-SNE Visualizations →](t-SNE/)**

#### 📊 Featured Models:
- **🏆 4D Deterministic**: Best overall performance (AUC: 0.8891)
- **🎯 8D Deterministic**: Strong deterministic performance (AUC: 0.8269)  
- **🔢 10D Deterministic**: High-dimensional analysis (AUC: 0.8236)
- **⚡ 8D cuTensorNet-2048**: Peak GPU performance (AUC: 0.6326)
- **📈 4D cuTensorNet-512**: Efficient baseline (AUC: 0.5121)

#### 🔍 Visualization Types:
- **Holdout Predictions**: Model quality on unseen data (~1.2MB each)
- **Quantum Feature Space**: PCA-reduced quantum representations (~3.5MB each)  
- **Quantum vs Classical**: Decision boundary comparisons (~4.5MB each)

#### 🎯 Strategic Selection (15 files from 100 available)
**Available t-SNE Files**: All 20 models × 5 visualization types = **100 total files**
**Selected**: **15 files (15%)** - Highly curated for maximum scientific impact

**Featured Models in t-SNE Visualizations:**
```
✅ 4D_deterministic                    (AUC: 0.8891) - Best overall
✅ 8D_deterministic                    (AUC: 0.8269) - Strong deterministic  
✅ 10D_deterministic                   (AUC: 0.8236) - High-dimensional
✅ 8D_cuTensorNet_2048shots           (AUC: 0.6326) - Peak cuTensorNet
✅ 4D_cuTensorNet_512shots            (AUC: 0.5121) - Efficient baseline

📝 Note: All 20 trained models are available in the models/ directory
    t-SNE visualizations showcase 5 representative models for clarity
```

**Visualization Types (3 per featured model):**
- `*_holdout_predictions.png` - Model quality assessment
- `*_quantum_feature_space.png` - PCA-reduced quantum representations  
- `*_quantum_vs_classical.png` - Decision boundary comparisons

#### 💡 Key Insights:
- **Feature Transformation**: See how quantum kernels create non-linear separations
- **Model Quality**: Visual correlation between clustering and ROC-AUC performance
- **Quantum Advantage**: Compare quantum and classical decision boundaries
- **Dimensional Effects**: Observe how feature dimension impacts separability

## 🏗️ What's Included

**Each model package contains:**
- `QSVM_model.joblib` - Trained Quantum SVM model
- `SVM_model.joblib` - Classical SVM baseline
- `tfidf_vectorizer.joblib` - Text preprocessing pipeline
- `QSVM_pca_quantum.joblib` - PCA transformer for quantum features
- `linguistic_scaler.joblib` - Linguistic feature scaler
- `label_encoder.joblib` - Label encoder
- `metadata.json` - Training configuration and parameters
- `QSVM_quantum_normalization_params.npz` - Quantum preprocessing parameters
- `QSVM_kernel_mode.json` - Quantum kernel configuration

## 🚀 Quick Start

```python
import joblib
import numpy as np

# Load a pre-trained model (best performer)
qsvm = joblib.load('models/4D_deterministic/QSVM_model.joblib')
vectorizer = joblib.load('models/4D_deterministic/tfidf_vectorizer.joblib')
pca = joblib.load('models/4D_deterministic/QSVM_pca_quantum.joblib')
scaler = joblib.load('models/4D_deterministic/linguistic_scaler.joblib')

# Example usage (you'll need to implement full preprocessing pipeline)
text_sample = ["Your AI-generated text here..."]
# Note: Full preprocessing includes TF-IDF + linguistic features + PCA
# See metadata.json for complete configuration
```

## 💻 Technical Specifications

- **Training Data**: 5,800 total samples (4,640 train / 1,160 validation)
- **Text Sources**: Qwen 2.5-32B-Instruct vs Gemma 3-27B-IT
- **Computational Resources**: HEMUS supercomputer (A100 GPUs, 128-core CPUs)
- **Training Time**: 44-216 hours per model (parallel CV execution)
- **Memory Requirements**: 10-55 GB peak usage (dimension-dependent)

## 🎯 Key Scientific Contributions

1. **Scaling Analysis**: Performance vs dimensionality in quantum feature spaces
2. **Noise Characterization**: Quantum-noiseless vs measurement-noise effects  
3. **Feature Engineering**: Linguistic feature importance in quantum kernels
4. **Computational Insights**: Parallel quantum ML training strategies

## 📚 Citation

If you use these models in your research, please cite our paper:

```bibtex
@article{kopanov2025scaling,
  title={Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights},
  author={Kopanov, Kalin},
  journal={[Journal Name]},
  year={2025},
  doi={[DOI when available]}
}
```

## 📦 Repository Structure

```
QSVM-AI-Text-Attribution/
├── 📄 README.md                    # This comprehensive guide
├── 📄 LICENSE                      # MIT License
├── 📄 CITATION.cff                 # Citation metadata
├── 📄 requirements.txt             # Python dependencies
├── 📁 models/                      # 20 pre-trained QSVM models (31MB)
│   ├── 🎯 4D_deterministic/        # Best performer (AUC: 0.8891)
│   ├── 🎯 6D_deterministic/
│   ├── 🎯 8D_deterministic/
│   ├── 🎯 10D_deterministic/
│   ├── ⚡ 4D_cuTensorNet_[512-4096]shots/
│   ├── ⚡ 6D_cuTensorNet_[512-4096]shots/
│   ├── ⚡ 8D_cuTensorNet_[512-4096]shots/  # Peak cuTensorNet (AUC: 0.6326)
│   └── ⚡ 10D_cuTensorNet_[512-4096]shots/
├── 📁 ROC/                         # Performance analysis (1.2MB)
│   ├── 🖼️ ROC curve visualizations
│   ├── 📊 Performance summaries
│   └── 📈 PR-AUC & Brier analysis
├── 📁 t-SNE/                       # Feature space visualizations (91MB)
│   ├── 🔍 Quantum feature space analysis
│   ├── 🎯 Model decision boundaries
│   └── 📊 5 key models × 3 visualization types
```

## 📋 Installation & Requirements

### Basic Installation
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/QSVM-AI-Text-Attribution.git
cd QSVM-AI-Text-Attribution

# Install dependencies
pip install -r requirements.txt
```

### Core Dependencies
- **Python 3.8+**
- **scikit-learn** (ML algorithms)
- **qiskit + qiskit-machine-learning** (quantum computing)
- **numpy, pandas, scipy** (scientific computing)
- **joblib** (model serialization)
- **matplotlib, seaborn** (visualization)

### GPU Acceleration (Optional)
For cuTensorNet models with GPU acceleration, install additional packages:
```bash
# For CUDA 11.x
pip install cupy-cuda11x cuquantum-python

# For CUDA 12.x  
pip install cupy-cuda12x cuquantum-python
```

**Requirements:** NVIDIA GPU with Compute Capability 7.0+, CUDA 11.x/12.x

## 🤝 Contributing

We welcome contributions, bug reports, and feature requests. Please open an issue or submit a pull request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

We acknowledge the provided access to the e-infrastructure of the Centre for Advanced Computing and Data Processing (HPC - HEMUS), with financial support from Grant No BG05M2OP001-1.001-0003, financed by the Science and Education for Smart Growth Operational Program (2014-2020) and co-financed by the European Union through the European Structural and Investment funds.

## 💰 Funding

**Sources of Funding for Research Presented in a Scientific Article or Scientific Article Itself**

The presented study is supported by the National Science Fund at the Ministry of Education and Science of Bulgaria, with Contract No КП-06-Н85/16.

---
*Repository maintained by: Kalin Kopanov (kalin.kopanov@iict.bas.bg)*  
*Institution: Institute of Information and Communication Technologies, Bulgarian Academy of Sciences*
