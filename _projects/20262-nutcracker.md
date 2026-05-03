---
layout: project
title: Bending in Nutcracker Arms
description: Building off of my nutcracker design with additional understanding in bending
image: /assets/images/cover-photo.png
---


# High-Efficiency Nutcracker Design Analysis

This project builds off of my previous nutcracker design while adding my new understanding of bending and moments of inertia. I use this to create a mass-efficient nutcracker handle using a statically indeterminate beam model and advanced composite materials.

---

## 1. Static Analysis & Modeling

The handle is modeled as a **simply supported beam with an overhanging load**. Based on human grip strength and the mechanical requirements for cracking a standard nut:

* **Applied Grip Force ($F_G$):** 392 N (Approx. 40 kg)
* **Reaction at Nut ($F_N$):** 2352 N
* **Pivot Distance ($L_{BC}$):** 20 mm
* **Handle Overhang ($L_{AB}$):** 100 mm

By summing moments about the pivot ($C$), we confirm the mechanical advantage:
$$\sum M_C = 0 \implies F_N = \frac{L_{AB} + L_{BC}}{L_{BC}} F_G = 6 F_G$$

---

## 2. Elastic Deformation Constraints

To ensure a "stiff" feel and prevent structural failure, the design requirement limits vertical deflection to **< 2% of the total length**.

* **Total Length ($L$):** 120 mm
* **Deflection Limit ($\delta_{max}$):** 2.4 mm

The deflection at the handle tip ($A$) is derived using the method of superposition:
$$\delta_A = \frac{F_G L_{AB}^2}{3EI} (L_{BC} + L_{AB})$$

---

## 3. Material & Geometry Optimization

To achieve maximum mass efficiency, we transitioned from a solid steel rod to a **High-Modulus Carbon Fiber Reinforced Polymer (CFRP)** hollow box section.

### Material Properties (CFRP)
Young's Modulus ($E$): 150 GPa
Density ($\rho$): 1600 kg/m³

### Optimized Geometry: Hollow Square Section
To satisfy $\delta_A \le 2.4\text{ mm}$, the required Second Moment of Area ($I$) was calculated:
$$I_{req} \approx 435\text{ mm}^4$$

**Final Specifications:**
* **Outer Width ($b$):** 9 mm
* **Wall Thickness ($t$):** 1 mm
* **Total Handle Mass:** ~6.1 g

Prototype generation:

![prototype]({{ "/assets/images/prototype.png" | relative_url }}){: .center-image style="width: 500px"}

---

## 4. Conclusion
The resulting design is over **10x lighter** than a traditional steel equivalent while maintaining the necessary rigidity to crack a nut with an average force requirement of 2205 N. This demonstrates the power of combining beam theory with high-performance material selection.

---

## 5. Detailed Mathematical Derivation

### A. Calculating Required Stiffness (EI)
To find the required Moment of Inertia ($I$), we rearrange the deflection formula:

$$\delta_A = \frac{F_G L_{AB}^2 (L_{BC} + L_{AB})}{3EI}$$

Substituting the design constraints:
* $F_G = 392\text{ N}$
* $L_{AB} = 0.1\text{ m}$
* $L_{BC} = 0.02\text{ m}$
* $E = 150 \times 10^9\text{ Pa}$
* $\delta_{max} = 0.0024\text{ m}$

$$I = \frac{(392)(0.1)^2(0.12)}{3(150 \times 10^9)(0.0024)}$$
$$I = \frac{0.4704}{1.08 \times 10^9} = 4.35 \times 10^{-10}\text{ m}^4$$

### B. Geometry Selection (Thin-Walled Approximation)
For a hollow square section with outer width $b$ and thickness $t$, the Second Moment of Area is:
$$I = \frac{b^4 - (b-2t)^4}{12}$$

Using the thin-walled approximation ($I \approx \frac{2}{3}b^3t$) for $t = 1\text{ mm}$:
$$435\text{ mm}^4 = \frac{2}{3} b^3 (1\text{ mm})$$
$$b^3 = 652.5 \implies b \approx 8.67\text{ mm}$$
*Rounding up to **$9\text{ mm}$** for a standard manufacturing profile.*

### C. Mass Estimation
The cross-sectional area $A$ of the hollow box is:
$$A = b^2 - (b-2t)^2 = 9^2 - 7^2 = 32\text{ mm}^2$$

Convert to meters squared:
$$A = 32 \times 10^{-6}\text{ m}^2$$

Mass ($m$) for one handle ($L = 0.12\text{ m}$):
$$m = \rho \cdot A \cdot L$$
$$m = (1600\text{ kg/m}^3)(32 \times 10^{-6}\text{ m}^2)(0.12\text{ m})$$
$$m = 0.006144\text{ kg} \approx 6.14\text{ g}$$
