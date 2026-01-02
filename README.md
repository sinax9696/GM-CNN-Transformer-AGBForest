# Gaussian Mixture Integration of CNN and Transformer Models for Forest Biomass Estimation  
### A Multi-Sensor Fusion Approach with Explicit Uncertainty Quantification

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN%20%7C%20Transformer-orange)
![Remote Sensing](https://img.shields.io/badge/Remote%20Sensing-Sentinel--1%20%7C%20Sentinel--2-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📌 Overview

This repository accompanies the research paper:

**Gaussian Mixture Integration of CNN and Transformer Models for Forest Biomass Estimation:  
A Multi-Sensor Fusion Approach with Explicit Uncertainty Quantification**

This work introduces a **probabilistic ensemble framework** that integrates **Convolutional Neural Networks (CNNs)** and **Transformer-based architectures** for estimating **Above-Ground Biomass (AGB)** in forest ecosystems using **multi-sensor satellite data**.

A key contribution of this framework is **explicit uncertainty quantification**, achieved through **Gaussian Mixture-based ensemble averaging**, enabling uncertainty-aware biomass mapping.

---

## 🎯 Key Contributions

- Systematic comparison of **CNNs** (ResNet, DenseNet) and **Transformers** (ViT, Swin Transformer)
- Multi-sensor data fusion using:
  - Sentinel-2 optical imagery
  - Sentinel-1 SAR data
  - LiDAR-derived topographic indices (slope, aspect)
- Patch-based learning aligned with coarse-resolution AGB reference maps
- Transfer learning for cross-region generalization
- Gaussian Mixture Ensemble for:
  - Robust prediction fusion
  - Epistemic & aleatoric uncertainty estimation
- Generation of AGB mean maps and uncertainty maps

---
## 🌍 Study Scope
<img width="40%" alt="Study Area" src="Figures\Study Area.jpg" />   

- **Study area:** Rocky Mountains (Montana & Idaho, USA)
- **Forest type:** Temperate coniferous forests
- **Spatial resolution:** 900 m
- **Reference year:** 2016
---

## ⚙️ Methodological Workflow
<img width="50%" alt="AGB Framework" src="Figures\Flowchart.png" />
---
## 🛰️ Datasets

### Remote Sensing Inputs
- **Sentinel-2**: 13 multispectral bands (10–20 m)
- **Sentinel-1 SAR**: VV & VH polarizations
- **Topographic indices**: slope and aspect (LiDAR-derived)

All inputs are co-registered at **10 m spatial resolution**.

### Reference Data
- Above-Ground Biomass maps from the **US Carbon Monitoring System (CMS)**
- Aggregated to **900 m resolution** for stable supervision

---

## 🧠 Deep Learning Models

### CNN-based Models
- ResNet-20 / 32 / 44 / 56 / 110 / 164  
- DenseNet-100  

### Transformer-based Models
- Vision Transformer (ViT)  
- Swin Transformer (lightweight adapted architecture)

Each model processes **90 × 90 × 15** patches, corresponding to one 900 m AGB reference pixel.

---

## 🔀 Gaussian Mixture Ensemble

Each model prediction is treated as a Gaussian distribution:

yᵢ(x) ~ N(μᵢ(x), σᵢ²)


The ensemble prediction is obtained via Gaussian Mixture Averaging, yielding:
- Mean AGB estimate
- Total predictive uncertainty:
  - **Epistemic** (model disagreement)
  - **Aleatoric** (AGN reference data noise)

---

## 📊 Evaluation Metrics

- RMSE  
- nRMSE  
- MAE  
- R²  
- Mean Bias Error (MBE)  
- Standard Deviation of residuals  

Evaluation is performed across:
- AGB value ranges
- Topographic classes (slope and aspect)



---

## ⚙️ Requirements

```bash
Python >= 3.9
TensorFlow >= 2.10
NumPy
SciPy
Rasterio
GDAL
Scikit-learn
Matplotlib
Seaborn
```

Install dependencies:
```bash
pip install -r requirements.txt
```

---

## 🚀 Workflow (High-Level)

1. Preprocess Sentinel-1, Sentinel-2, and topographic data  
2. Generate multi-band image patches  
3. Train CNN and Transformer models  
4. Apply transfer learning on target region  
5. Perform Gaussian Mixture ensemble  
6. Generate AGB mean and uncertainty maps  

---
## 🧾 Citation
If you use this repository or its methodology, please cite:

> Irannejad, S., & Bagheri, H. (2026).  
> **Gaussian Mixture Integration of CNN and Transformer Models for Forest Biomass Estimation: A Multi-Sensor Fusion Approach with Explicit Uncertainty Quantification**.  
> *(Manuscript under review)*

---

## 🪴 License
This project is licensed under the **MIT License** – free to use, modify, and share with proper attribution.

---

## 📬 Contact
**Author:** Sina Irannejad  sinax9696@gmail.com    
 
**Corresponding author:** Dr. Hossein Bagheri  h.bagheri@cet.ui.ac.ir 

Faculty of Civil Engineering and Transportation  
University of Isfahan, Iran  

---

## 📦 Data Availability

All datasets used in this study are publicly available on Zenodo:

🔗 
