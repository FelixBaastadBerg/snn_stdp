# 🧠 Unsupervised Time Series Forecasting with Spiking Neural Networks

This project explores the use of **Spiking Neural Networks (SNN)** and **Spike-Time Dependent Plasticity (STDP)** for **unsupervised time series forecasting**.  
It was developed as part of my work at MIT (Department of Electrical Engineering and Computer Science).

The model learns to predict one step ahead in stationary time series data — here, **detrended daily temperatures in Madrid** — without any supervision.  
The goal is to test whether biologically inspired, unsupervised learning rules can discover meaningful temporal structure in data traditionally modeled by supervised approaches.

---

## 🚀 Overview

- Implements a **biologically inspired learning algorithm (STDP)** using **Leaky Integrate-and-Fire neurons**
- Built using the [**Brian2**](https://brian2.readthedocs.io/) simulator in Python
- Trains an unsupervised spiking network to forecast one-step-ahead values
- Evaluates results using **Mean Squared Error (MSE)** and compares to **AR(5)** baseline
- Includes visualization of neuron firing activity, receptive fields, and synaptic weight evolution

---

## 🧩 Network Architecture

The architecture is based on **Diehl & Cook (2015)**:
- **Input layer** encodes data as firing rates (Poisson-distributed spike trains)
- **Excitatory layer** learns to represent distinct temporal patterns
- **Inhibitory layer** introduces lateral competition to promote diverse receptive fields  
- Learning occurs locally via the **Spike-Time Dependent Plasticity (STDP)** rule

<p align="center">
  <img src="architecture_diagram.png" alt="Architecture Diagram" width="500">
</p>

---

## 📊 Results Summary

- The SNN achieves meaningful temporal forecasting, though MSE remains higher than AR(5)
- The receptive fields form distinct patterns, revealing biologically interpretable neuron behavior
- Performance improves up to an optimal ratio between number of neurons and training data
- The model performs particularly well on **boolean or range-based forecasting** tasks

| Model | MSE (↓) | Correct Label % (↑) |
|--------|----------|--------------------|
| AR(5) | 412 | - |
| SNN (1000 neurons) | 670.8 | 18.1% |

---

## 🧠 Example Applications

- **Neuromorphic time-series forecasting**
- **Stock up/down prediction** (boolean forecasting)
- **Brain-inspired computational modeling**
- **Energy-efficient forecasting on neuromorphic chips**

---

## 🧪 Run the Code

You can open and run the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yourusername/unsupervised-spiking-forecasting/blob/main/notebooks/main.ipynb)

### Dependencies
```bash
pip install brian2 numpy pandas matplotlib scikit-learn

