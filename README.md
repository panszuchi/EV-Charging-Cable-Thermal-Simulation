# Electro-Thermal & CFD Simulation of High-Power EV Charging Cables (600A)

[![CAD](https://img.shields.io/badge/CAD-SolidWorks-red.svg)](https://www.solidworks.com/)
[![CFD](https://img.shields.io/badge/CFD-Siemens%20FloEFD-blue.svg)](https://plm.sw.siemens.com/en-US/simcenter/floefd/)
[![Institution](https://img.shields.io/badge/Institution-NTUT-green.svg)](https://www me.ntut.edu.tw/)

> **Academic Project** | Department of Energy and Refrigerating Air-Conditioning Engineering, National Taipei University of Technology (NTUT)  
> **Authors:** Szuchi Pan, Bing-Xuan Ho  
> **Advisor:** Dr. Ching-Chi Chen  

---

## 📌 Project Overview

High-power DC fast-charging technology significantly reduces electric vehicle (EV) charging times. However, transmitting ultra-high currents (600A) induces rapid Joule heating within charging cables, posing severe safety risks and structural degradation. 

This project presents a 3D numerical **Conjugate Heat Transfer (CHT)** simulation to model thermal dissipation in a 5-meter 600A liquid-cooled EV charging cable. Using **SolidWorks** for 3D geometric modeling and **Siemens FloEFD** for CFD fluid-thermal analysis, we evaluate and compare the thermal management efficacy of two distinct cooling fluids: **Water** versus **Dimethyl Silicone Oil (DSO)** under extreme electrical loads.

---

## 📐 Cable Geometry & Component Dimensions

The 5-meter liquid-cooled EV charging cable consists of multiple concentric functional layers designed to isolate heat, electrical current, and cooling fluid.

| Parameter / Dimension | Symbol | Value (mm) | Description |
| :--- | :---: | :---: | :--- |
| **Cooling Channel Inner Diameter** | $D_1$ | 6.00 mm | Fluid flow core diameter |
| **Conduit Outer Diameter** | $D_2$ | 8.00 mm | Isolates cooling channel from conductors |
| **Conductor Outer Diameter** | $D_3$ | 9.79 mm | Stranded copper wire ($25\text{ mm}^2$ cross-section) |
| **Insulation Layer Diameter** | $D_4$ | 12.79 mm | Electrical isolation layer |
| **Filler Layer Diameter** | $D_5$ | 38.92 mm | Internal structural filler |
| **Cable Outer Diameter** | $D_6$ | 42.92 mm | Outer protective jacket |
| **Total Cable Length** | $L$ | 5.00 m | Cable axial length |

<p align="center">
  <img src="assets/cable_cross_section.png" width="70%" alt="Cable Cross-Section and Longitudinal Diagram">
  <br>
  <em>Figure 1: Cross-sectional and longitudinal view of the 600A liquid-cooled charging cable model.</em>
</p>

---

## ⚙️ Simulation Setup & Boundary Conditions

The 3D CHT simulation was set up in **Siemens FloEFD** with the following thermal-fluid boundary conditions:

### 1. Joule Heat Source Generation
* **Current Load ($I$):** $600\text{ A}$ (DC)
* **Conductor Material:** Stranded Copper ($A = 25\text{ mm}^2$)
* **Electrical Resistivity ($\rho$):** $1.92 \times 10^{-8} \ \Omega\cdot\text{m}$

### 2. Fluid Flow & Thermal Boundaries
* **Inlet Flow Velocity:** $0.5\text{ m/s}$ (Velocity Inlet)
* **Outlet Boundary:** Pressure Outlet
* **Fluid Wall Condition:** Standard No-slip wall
* **Ambient Air Temperature:** $40^\circ\text{C}$
* **External Surface Heat Transfer Coefficient ($h$):** $5\text{ W/(m}^2\cdot\text{K)}$ (Natural Convection)
* **Inlet/Outlet Cut Planes:** Adiabatic boundary
* **Initial Solid Temperature:** $40^\circ\text{C}$

---

## 📊 Results & Comparative Analysis

We evaluated three distinct operating scenarios to assess heat dissipation capacity and outer cable surface temperatures (critical for user safety / touch thermal limits):

1. **Case A:** Water cooling at $15.73^\circ\text{C}$ (Chilled Water)
2. **Case B:** Dimethyl Silicone Oil (DSO) cooling at $15.73^\circ\text{C}$
3. **Case C:** Water cooling at $40.00^\circ\text{C}$ (Ambient Temperature Water)

### Temperature Distribution Contours

| Location | Case A: Water ($15.73^\circ\text{C}$) | Case B: DSO ($15.73^\circ\text{C}$) | Case C: Water ($40^\circ\text{C}$) |
| :---: | :---: | :---: | :---: |
| **Near Inlet (0.4m)** | <img src="assets/fig3.png" width="220"> | <img src="assets/fig4.png" width="220"> | <img src="assets/fig5.png" width="220"> |
| **Near Outlet (4.6m)** | <img src="assets/fig6.png" width="220"> | <img src="assets/fig7.png" width="220"> | <img src="assets/fig8.png" width="220"> |

### Key Quantitative Findings:

* **Coolant Performance Comparison (Inlet @ 0.4m):**
  * **Water ($15.73^\circ\text{C}$):** Maintains cable surface temperature around **$\sim 30^\circ\text{C}$**.
  * **DSO ($15.73^\circ\text{C}$):** Cable surface temperature reaches **$\sim 50^\circ\text{C}$**.
* **Thermal Accumulation along Cable Length (Outlet @ 4.6m):**
  * **Water ($15.73^\circ\text{C}$):** Cable surface temperature reaches **$\sim 50^\circ\text{C}$**.
  * **DSO ($15.73^\circ\text{C}$):** Surface temperature surges up to **$\sim 70^\circ\text{C}$**, posing a high risk of user burn injuries upon contact.
* **Chilled vs. Ambient Water Cooling:**
  * Comparing $15.73^\circ\text{C}$ water with $40^\circ\text{C}$ ambient water, both coolants maintain outlet surface temperatures close to **$\sim 50^\circ\text{C}$**.

---

## 💡 Major Conclusions & Engineering Takeaways

1. **Inadequacy of Dimethyl Silicone Oil (DSO):** DSO exhibits significantly lower heat transfer performance than water due to its thermodynamic liquid properties. It fails to effectively remove core Joule heat, forcing the system to rely primarily on external ambient natural convection. Thus, **DSO is not recommended as a direct liquid coolant** for 600A ultra-fast charging cables.
2. **Efficacy of Ambient Water Cooling:** Using **water at ambient temperature ($40^\circ\text{C}$)** provides sufficient heat removal capacity to keep surface temperatures safe ($\le 50^\circ\text{C}$).
3. **System Cost & Energy Optimization:** Because ambient water cooling achieves acceptable thermal equilibrium along the 5-meter cable without requiring active chilling, EV charging stations can avoid complex refrigeration units, reducing system complexity and parasitic power consumption.

---

## 🛠️ Tools & Technologies Used

* **CAD Modeling:** SolidWorks
* **CFD & Thermal Analysis:** Siemens FloEFD (Conjugate Heat Transfer)
* **Domain Applications:** Electric Vehicle (EV) Infrastructure, Thermal Management, Power Electronics Cooling

---

## ✒️ Authors & Citation

* **Szuchi Pan (潘思齊)** & **Bing-Xuan Ho (何秉軒)**
* Department of Energy and Refrigerating Air-Conditioning Engineering
* **National Taipei University of Technology (NTUT / Taipei Tech)**

*Special thanks to **Dr. Ching-Chi Chen (陳清祺 博士)** for project guidance.*
