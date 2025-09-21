# Repository Description for QSVM-AI-Text-Attribution

## Short Description (for GitHub repo description field):
Pre-trained Quantum Support Vector Machine models for AI-generated text attribution. Includes 20 models across 4D-10D quantum feature spaces using cuTensorNet and StatevectorSimulator backends. Trained on 4,640 samples distinguishing Qwen 2.5 from Gemma 3 text.

## Detailed Description (for README.md):

### 🎯 Overview
This repository contains pre-trained Quantum Support Vector Machine (QSVM) models for distinguishing AI-generated text from different large language models. The models were trained on a comprehensive dataset of 4,640 training samples and validated on 1,160 hold-out samples, focusing on attribution between Qwen 2.5 and Gemma 3 generated text.

### 🔬 Research Context
These models accompany the research paper:
**"Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights"**
*Authors: [Your Name], [Institution]*

### 🧠 Model Architecture
- **Quantum Backends**: cuTensorNet (GPU-accelerated) and StatevectorSimulator (deterministic)
- **Feature Engineering**: TF-IDF + 18 linguistic features → PCA → Quantum kernel
- **Dimensions**: 4D, 6D, 8D, 10D quantum feature spaces
- **Shot Counts**: 512, 1024, 2048, 4096 (cuTensorNet only)
- **Training**: 5-fold cross-validation with parallel execution

### 📊 Model Performance Highlights
- **Best Performance**: 4D Deterministic (ROC-AUC: 0.8891)
- **Noise Robustness**: 8D cuTensorNet shows peak performance (ROC-AUC: 0.6326)
- **Quantum Advantage**: Deterministic models achieve 80-89% accuracy on unseen test data
- **Feature Insights**: 14-17 of 18 linguistic features consistently important across models

### 🏗️ What's Included
**20 Complete Model Packages:**
- 4 Deterministic models (4D, 6D, 8D, 10D)
- 16 cuTensorNet models (4 dimensions × 4 shot counts)

**Each package contains:**
- Trained QSVM model (.joblib)
- Classical SVM baseline (.joblib)
- Complete preprocessing pipeline (TF-IDF, PCA, scalers)
- Quantum normalization parameters
- Metadata with training configuration

### 💻 Technical Specifications
- **Training Data**: 5,800 total samples (4,640 train / 1,160 validation)
- **Text Sources**: Qwen 2.5-32B-Instruct vs Gemma 3-27B-IT
- **Computational Resources**: HEMUS supercomputer (A100 GPUs, 128-core CPUs)
- **Training Time**: 44-216 hours per model (parallel CV execution)
- **Memory Requirements**: 10-55 GB peak usage (dimension-dependent)

### 🎯 Use Cases
- **Research**: Quantum machine learning baselines and comparisons
- **Applications**: AI text detection and attribution systems
- **Education**: Quantum SVM implementation examples
- **Benchmarking**: Performance evaluation against classical methods

### 📈 Key Scientific Contributions
1. **Scaling Analysis**: Performance vs dimensionality in quantum feature spaces
2. **Noise Characterization**: Quantum-noiseless vs measurement-noise effects
3. **Feature Engineering**: Linguistic feature importance in quantum kernels
4. **Computational Insights**: Parallel quantum ML training strategies

### 🔧 Quick Start
```python
import joblib
import numpy as np

# Load a pre-trained model
qsvm = joblib.load('models/Deterministic/4D/QSVM_model.joblib')
preprocessor = joblib.load('models/Deterministic/4D/tfidf_vectorizer.joblib')

# Make predictions on new text
text_sample = ["Your AI-generated text here..."]
features = preprocessor.transform(text_sample)
prediction = qsvm.predict(features)
```

### 📚 Citation
If you use these models in your research, please cite:
```bibtex
@article{kopanov2024scaling,
  title={Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights},
  author={Kopanov, Kalin},
  journal={[Journal Name]},
  year={2024},
  doi={[DOI when available]}
}
```

### 🤝 Contributing
We welcome contributions, bug reports, and feature requests. Please open an issue or submit a pull request.

### 📄 License
[Choose appropriate license - MIT, Apache 2.0, or CC BY 4.0 recommended for research]

### 🙏 Acknowledgments
- HEMUS supercomputer facility at IICT-BAS
- Qiskit and cuQuantum development teams
- [Any funding sources or collaborators]

---
*Repository maintained by: Kalin Kopanov (kalin.kopanov@iict.bas.bg)*
*Institution: Institute of Information and Communication Technologies, Bulgarian Academy of Sciences*
