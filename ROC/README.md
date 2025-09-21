# 📈 Performance Analysis & ROC Curves

This folder contains comprehensive performance analysis for all 20 QSVM models, including ROC curves, PR-AUC metrics, and calibration analysis.

## 🎯 Overview

All models were evaluated on an independent **200-sample test set** (100 Qwen 2.5 + 100 Gemma 3) that was never used during training, cross-validation, or hold-out evaluation. This ensures unbiased performance assessment.

## 📊 Performance Visualizations

### 🖼️ ROC Curve Plots

#### Deterministic Models (StatevectorSimulator)
- **[`QSVM_ROC_StatevectorSimulator_all_dimensions.png`](QSVM_ROC_StatevectorSimulator_all_dimensions.png)**
  - Single ROC curve per dimension (4D, 6D, 8D, 10D)
  - Exact quantum simulation (no sampling noise)
  - **Best Performance**: 4D with AUC = **0.8891**

#### cuTensorNet Models (GPU-Accelerated)
- **[`QSVM_ROC_cuTensorNet_all_dimensions.png`](QSVM_ROC_cuTensorNet_all_dimensions.png)**
  - Combined overview of all dimensions
  - Mean curves with min-max bands across shot counts (512-4096)
  - **Peak Performance**: 8D with mean AUC = **0.6326**

#### Individual Dimension Analysis
- **[`QSVM_ROC_cuTensorNet_k4_mean.png`](QSVM_ROC_cuTensorNet_k4_mean.png)** - 4D analysis
- **[`QSVM_ROC_cuTensorNet_k6_mean.png`](QSVM_ROC_cuTensorNet_k6_mean.png)** - 6D analysis  
- **[`QSVM_ROC_cuTensorNet_k8_mean.png`](QSVM_ROC_cuTensorNet_k8_mean.png)** - 8D analysis (best cuTensorNet)
- **[`QSVM_ROC_cuTensorNet_k10_mean.png`](QSVM_ROC_cuTensorNet_k10_mean.png)** - 10D analysis

## 📋 Performance Summaries

### 📊 Numerical Results

#### [`QSVM_ROC_StatevectorSimulator_all_dimensions_summary.md`](QSVM_ROC_StatevectorSimulator_all_dimensions_summary.md)
Exact AUC values for deterministic models:
- **4D**: AUC = **0.8891** 🏆
- **6D**: AUC = **0.7995**
- **8D**: AUC = **0.8269**
- **10D**: AUC = **0.8236**

#### [`QSVM_ROC_cuTensorNet_all_dimensions_summary.md`](QSVM_ROC_cuTensorNet_all_dimensions_summary.md)
Mean AUC values across shot counts (512-4096):
- **4D**: Mean AUC = **0.5121** (σ = 0.0009)
- **6D**: Mean AUC = **0.5167** (σ = 0.0024)
- **8D**: Mean AUC = **0.6326** (σ = 0.0024) 🏆
- **10D**: Mean AUC = **0.5705** (σ = 0.0021)

### 📈 Calibration Analysis

#### [`QSVM_PR_Brier_cuTensorNet_summary.md`](QSVM_PR_Brier_cuTensorNet_summary.md)
Complete analysis including:
- **PR-AUC** with 95% bootstrap confidence intervals
- **Brier scores** for probability calibration assessment
- **Comparison with LinearSVM baseline** (AUC ≈ 0.999)

## 🔬 Key Scientific Insights

### 1. **Quantum vs Classical Performance Gap**
- **Classical LinearSVM**: AUC ≈ **0.999** (near-perfect)
- **Best Quantum (4D Deterministic)**: AUC = **0.8891**
- **Gap Analysis**: Quantum models show promise but classical methods still superior

### 2. **Noise Robustness Patterns**
- **Shot Stability**: cuTensorNet performance remarkably stable across 512-4096 shots
- **Dimensional Effects**: 8D cuTensorNet shows best noise resilience
- **Sampling vs Quantum Noise**: cuTensorNet introduces measurement noise, not quantum decoherence

### 3. **Optimal Operating Points**
- **For Accuracy**: Use 4D Deterministic model
- **For GPU Acceleration**: Use 8D cuTensorNet (any shot count)
- **For Efficiency**: Lower shot counts (512) provide similar performance to higher counts

### 4. **Calibration Challenges**
- **Brier Scores**: All quantum models show calibration issues (0.26-0.27 vs 0.166 for classical)
- **Confidence Intervals**: Wide CIs indicate uncertainty in probability estimates
- **Recommendation**: Apply post-hoc calibration for probability-dependent applications

## 🎯 Model Selection Guide

### Choose **4D Deterministic** if:
- ✅ Maximum accuracy required
- ✅ CPU resources available
- ✅ Exact quantum simulation desired

### Choose **8D cuTensorNet** if:
- ✅ GPU acceleration needed
- ✅ Good noise robustness required
- ✅ Balanced performance/efficiency desired

### Choose **Classical LinearSVM** if:
- ✅ Near-perfect accuracy required
- ✅ Fast inference needed
- ✅ Well-calibrated probabilities essential

## 📚 Methodology Notes

- **Test Set**: 200 samples (stratified: 100 Qwen 2.5, 100 Gemma 3)
- **Evaluation**: ROC-AUC (threshold-free discrimination)
- **Calibration**: Platt scaling applied for PR-AUC and Brier calculations
- **Confidence Intervals**: 95% class-stratified bootstrap (10,000 resamples, seed=42)
- **Baseline**: Calibrated LinearSVM on identical test set

---

*These results accompany the paper "Scaling Quantum Support Vector Machines for AI-Generated Text Attribution: Dimensionality, Shots, and Linguistic Feature Insights" by Kalin Kopanov, IICT-BAS.*
