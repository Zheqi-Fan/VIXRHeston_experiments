# 📊 VIXRHeston_experiments 
Implementation of pricing VIX term structure under rough Heston and traditional affine jump diffusion models (INCOMPLETE version)

## 📦 Python package (PyPI)
The Python package is available on PyPI: [VIXRHeston](https://pypi.org/project/VIXRHeston/)

## 📁 Description of each file 

  - `utils`: 🧮 Core functions to compute model-based VIX term structure under the lifted Heston (LHeston) model, including analytical squared VIX calculations, parameter sensitivity derivatives, and efficient numerical helpers;

  - `approx for rHeston`: 📈 Visualization illustrations demonstrating the convergence of VIX term structure under the LHeston model to the rough Heston (rHeston) model. For full rHeston implementations, refer to [Prof. Jacquier's Github](https://github.com/JackJacquier). Comparative analysis (via moment generating function validation) is presented in `rHestonMGF_compare.ipynb`;
  
  - `estimation_RHeston-2011`: ⚙️ Detailed parameter estimation workflow for the RHeston model, leveraging daily VIX term structure data (2011–2019) and an iterative two-step calibration procedure with analytical gradients;
  - TBA

## ✨ What we do 
  - 📏 Derived a **closed-form analytical formula** for squared VIX under the RHeston model (via multi-factor Markovian approximation), validated via degenerated cases, Monte Carlo simulation;
  - 🚀 Designed an efficient simulation scheme for VIX derivatives (e.g., futures, call options) by integrating the analytical VIX formula with Monte Carlo methods, replacing computationally expensive nested simulation;
  - 📊 Conducted comprehensive empirical analysis (nine year VIX term structure data: 1M/2M/3M/6M/9M/12M maturities) comparing pricing performance across Heston, Bates, HestonCJ (SVCJ), and RHeston models;
  - 📈 Demonstrated that the RHeston (via LHeston) model outperforms traditional affine jump-diffusion models in **in-sample and out-of-sample fitting** (lower MAPE/RMSE), validated by Diebold-Mariano statistical tests, and provides more reliable implied spot volatility estimates;
  - 🛡️ Robustness via subperiod analysis: Confirmed superior performance of rHeston even in crisis periods (2006–2011, including 2008 financial crisis) and showed that roughness better captures VIX term structure dynamics than jump components;
  - 🔍 Proposed a framework to extract variance risk premium under the LHeston model, linking risk-neutral and physical dynamics via explicit pricing kernel specification;
  - 📉 Utilized an iterative two-step calibration procedure (with analytical gradients) to estimate model parameters and latent spot volatilities, ensuring stability and accuracy across long time horizons.

## 📚 References
Ye, Y., Fan, Z., & Kwok, Y. K. (2026), "VIX term structure in the rough Heston model via Markovian approximation ", *Journal of Futures Markets*, Forthcoming.
