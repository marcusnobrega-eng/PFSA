# PFSA - Peak Flow Search Approach

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 📌 Overview

The **Peak Flow Search Approach (PFSA)** is an enhanced spreadsheet-based method to compute **peak runoff flows** from drainage areas with **dissimilar land use types**. This tool is based on the methodology proposed by Vasconcelos et al. (2025) and implemented in an interactive Excel spreadsheet by Marcus N. Gomes Jr.

PFSA improves upon the traditional Rational Method (RM) and Modified Rational Method (MRM) by introducing a flexible framework that:
- Separately considers subcatchments with different runoff coefficients and times of concentration ($T_c$)
- Applies an **Intensity-Duration-Frequency (IDF)** relationship to calculate rainfall intensities
- Searches for the **critical rainfall duration** that maximizes peak flow from the entire drainage system

---

## 🔧 Features

- Easy-to-use Microsoft Excel `.xlsm` tool
- Handles up to **100 subcatchments** with individual input parameters
- Includes support for:
  - Kerby, NRCS Velocity, and NRCS Lag methods for $T_c$
  - Sherman-type IDF curve
- Outputs:
  - Subarea peak flows
  - Combined peak flow over time
  - Critical rainfall duration
  - Comparison with Rational Method peak flows
- Compatible with manual goal-seeking or automated Solver optimization

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `PFSA_Method.xlsm` | Main Excel tool with editable input/output interface |
| `PFSA_User_Manual.pdf` | Full documentation and step-by-step guidance |
| `README.md` | GitHub landing page (you are reading it!) |

---

## 🧠 How It Works

The PFSA spreadsheet uses the following general equation to compute the total peak flow:

$$
Q(t) = \frac{B}{(t + D)^E} \sum_{j=1}^n C_j A_j \cdot \min\left(1, \frac{t}{T_{c,j}}\right)
$$

Where:
- $C_j$, $A_j$, and $T_{c,j}$ are the runoff coefficient, area, and time of concentration of subarea $j$
- $B$, $D$, and $E$ are constants from the local IDF curve
- $t$ is the rainfall duration being tested
- $Q(t)$ is the combined flow at time $t$
- $Q_p$ is the maximum of $Q(t)$ over the tested interval

---

## 🚀 Getting Started

### 1. Download and open `PFSA_Method.xlsm`
Enable macros when prompted.

### 2. Input your data
Fill in:
- Number of subcatchments
- $C_j$, $A_j$, $L_{sh}$, $L_{ch}$, $N$, $S$, $CN$, etc.
- IDF parameters ($B$, $D$, $E$)
- Simulation range (`tc0`, `tcf`, `Δtc`)

### 3. Run the model
The spreadsheet automatically computes $Q(t)$ for a range of durations.
You may use Excel's **Solver** or **Goal Seek** to pinpoint $t_{crit}$.

---

## 📚 Citation and Reference

If you use this tool for research or teaching, please cite:

> Vasconcelos, J.G., Gomes Jr., M.N., Oliveira, P.T.S., Yang, D., Fang, X. (2025).  
> *Reformulating the Rational Method Considering Dissimilar Land Use Types*.  
> Journal of Irrigation and Drainage Engineering, ASCE. DOI: [10.1061/JIDEDH.IRENG-10431](https://doi.org/10.1061/JIDEDH.IRENG-10431)

---

## ✉️ Contact

**Marcus N. Gomes Jr.**  
Postdoctoral Researcher Associate II  
Department of Hydrology and Atmospheric Sciences  
University of Arizona  
📧 [marcusnobrega.engcivil@gmail.com](mailto:marcusnobrega.engcivil@gmail.com)

---

## 🧾 License

This project is licensed under the MIT License. Feel free to use, adapt, and distribute with attribution.

---

## 🙌 Acknowledgments

This spreadsheet is based on the PFSA model developed by:

- **Jose G. Vasconcelos** – Auburn University  
- **Marcus N. Gomes Jr.** – University of Arizona  
- **Paulo Tarso S. Oliveira** – UFMS  
- **Dingyu Yang** – Auburn University  
- **Xing Fang** – Auburn University  
