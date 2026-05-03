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
| Property | Value |
| :--- | :--- |
| Young's Modulus ($E$) | 150 GPa |
| Density ($\rho$) | 1600 kg/m³ |

### Optimized Geometry: Hollow Square Section
To satisfy $\delta_A \le 2.4\text{ mm}$, the required Second Moment of Area ($I$) was calculated:
$$I_{req} \approx 435\text{ mm}^4$$

**Final Specifications:**
* **Outer Width ($b$):** 9 mm
* **Wall Thickness ($t$):** 1 mm
* **Total Handle Mass:** ~6.1 g

Prototype generation:

<div style="text-align: center;">
  ![Prototype](/assets/images/prototype.png)
</div>

---

## 4. Conclusion
The resulting design is over **10x lighter** than a traditional steel equivalent while maintaining the necessary rigidity to crack a nut with an average force requirement of 2205 N. This demonstrates the power of combining beam theory with high-performance material selection.
