# On the Numerical Sensitivity and Iterative Regularization of Stochastic Volterra Equations in Wavelet Bases

This repository contains the official Python implementation and reproducible datasets for the **Robust Monitoring Wavelet Algorithm (RMWA)** as described in the paper:

> **"On the Numerical Sensitivity and Iterative Regularization of Stochastic Volterra Equations in Wavelet Bases"**  
> *Author: Mohsen Salehi*

---

## 🚀 Overview
High-order wavelet discretization (SKCW) for Stochastic Itô-Volterra Integral Equations (SIVIEs) fundamentally leads to **discrete ill-posed inverse problems**. This repository provides the RMWA framework, which addresses severe ill-conditioning through a synthesis of spectral and robust statistical theories:

- **Mathematical Backbone:** Orthonormal Second-Kind Chebyshev Wavelets (SKCW).
- **Solver Engine:** Huber-weighted IR-LSQR (Krylov subspace method) providing an iterative regularization effect.
- **Data-driven Monitoring:** An adaptive sensitivity index $S(M) = \kappa(M) \cdot \text{MAD}(\text{Res})$ that detects the optimal truncation resolution level without requiring prior knowledge of the analytical exact solution.

## 📁 Repository Structure

| File | Description |
| :--- | :--- |
| `Code1_robust_skcw_lsqr_siviey.py` | Functional logic for basis generation and the robust IR-LSQR solver. |
| `Updated_Code1_robust_skcw_lsqr_siviey.py` | **Main Research Engine:** Orchestrates Monte Carlo simulations ($N=2000$), identifies optimal stopping, and exports statistical data. |
| `Comparision_Methods.py` | Benchmark suite comparing the proposed method vs. Tikhonov and TSVD regularizations. |
| `Biological_Population_with_Cauchy_Environmental_Shocks.py` | Real-world case study: Restoration of biological growth trends under Cauchy "heavy-tailed" shocks. |
| `RMWA_Master_Results.csv` | Summary Table including condition numbers ($\kappa$), $S(M)$ indices, and Average MSEs. |
| `RMWA_Detailed_MSE_Dist.csv` | Raw 2,000-path realization data used for quantile-based Confidence Intervals and Boxplot profiling. |
| `Comprehensive_Comparison_Results.csv` | Data confirming the 16.6% accuracy gain over standard regularization schemes. |

## ⚙️ Technical Environment
- **Software:** Tested on Python 3.12+ (Requires `NumPy`, `SciPy`, `Pandas`, `Matplotlib`).
- **Hardware Validated:** 12th Gen Intel Core i5-1235U | 16GB RAM | Parallelized MC.

## 🏃 Execution Steps
1. Run `Updated_Code1_robust_skcw_lsqr_siviey.py` to identify the optimal $M^*$ level through adaptive monitoring.
2. Run `Comparision_Methods.py` for comparative stability metrics.
3. Run `Biological_Population_with_Cauchy_Environmental_Shocks.py` for a visual proof of physical resilience.

## 📈 Key Findings
- **Resolution-Conditioning Duality:** Captured an empirical polynomial ill-conditioning growth rate ($\alpha \approx 3.37$).
- **Efficiency:** Mitigation of the computational bottleneck; 2000 trajectories solved in ~677s.
- **Rigor:** Implementation of 95% Quantile-based Confidence Intervals for stochastic error reporting.

## Citation
If you use this code or find the algorithm useful for your research, please cite our paper:
*(Citation details will be updated after official publication)*

## License
MIT License. Feel free to use and cite our work.
