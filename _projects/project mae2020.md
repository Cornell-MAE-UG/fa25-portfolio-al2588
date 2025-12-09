---
layout: project
title: Design of an actuator
description: An actuator and its application that I designed as part of my assignment for MAE 2020
image: /assets/images/IMG_0684.jpeg
---

Given a 2D design space of 150cm long and 50cm tall, a rigid bar of a fixed length (of my choice), 3 pin supports of which two need to be mounted on the ground and a linear actuator (use max force values only), I needed to design a frame/mechanism to lift the maximum possible weight to the highest possible height, assuming all the supports and bar/actuator are rigid.

My design included actuator IMA 22, and the maximum weight that could be lifted that I calculated was 1.25 N, according to the dimensions in the online catalog, as displayed in the image.

Given: 
Peak thrust = 1.45 kN
lenght of actuator = 12.86 cm
stroke length = 30.48 cm
W=?

Solution:
Taking moment about A:
W(150) = 1.45(130.02)
W = 1.26 kN is the maximum weight that could be lifted

# Portfolio Mechanism Analysis

## Step 1 — Rigid-Bar Mechanism

### (a) Problem, Constraints, and Degrees of Freedom

**Problem:**  
Design a lifting mechanism inside a 150 cm × 50 cm workspace using a rigid 150 cm bar, three pin supports (two on ground), and a linear actuator that can deliver up to **1.45 kN**. The objective is to lift the maximum possible weight to a vertical height of **50 cm**.

**Constraints:**
- Operating space: 150 cm horizontal × 50 cm vertical  
- Bar length: 150 cm  
- Actuator force acts along its axis  
- Weight attached at far end of bar  
- Actuator attaches at 75 cm from pivot  
- Bar treated as rigid for Step 1  

**Degrees of Freedom:**
- Placement of ground supports  
- Bar pivot location  
- Actuator base location  
- Actuator attachment point on bar  
- Weight location on bar  

---

### (b) Static Analysis of the Rigid Bar

The bar lifts the weight when it rotates to an angle:

\[
\theta = \tan^{-1}\left(\frac{50}{150}\right)
= 18.43^\circ
\]

**Coordinates (cm):**

| Point | x (cm) | y (cm) |
|-------|--------|--------|
| A (pivot) | 0 | 0 |
| C (actuator attach, 75 cm) | \(75\cos\theta = 71.3\) | \(75\sin\theta = 23.7\) |
| D (weight, 150 cm) | \(150\cos\theta = 142.7\) | \(150\sin\theta = 47.4\) |

The actuator is mounted vertically below C, so its force is:

\[
F_{\text{act}} = 1.45\ \text{kN} = 1450\ \text{N}
\]

**Moment arms:**

- Actuator moment arm about A: 71.3 cm  
- Weight moment arm about A: 142.7 cm  

**Moment equilibrium about A:**

\[
1450(71.3) = W(142.7)
\]

Solving:

\[
W = 724\ \text{N}
\]

#### Maximum liftable weight (rigid mechanism):

\[
W_{\text{max}} = 724\ \text{N} \approx 74\ \text{kg}
\]

---

### (c) Mechanism Description

- Bar length = 150 cm  
- Pivot at A (ground)  
- Weight attached at D, 150 cm from A  
- Actuator attaches at C, 75 cm from A  
- Actuator is vertical from a ground point below C and pushes upward with 1.45 kN  
- Mechanism reaches the required 50 cm lift when the bar is at angle \(\theta \approx 18.4^\circ\)

---

## Step 2 — Beam Analysis (Flexible Bar)

Now the bar is treated as a **beam** instead of rigid.

### Beam Setup

**Supports:**
- Pin at A (x = 0 cm)  
- Vertical reaction at C from actuator (x = 75 cm)  

**Loads:**
- Upward 1450 N at C  
- Downward 724 N at D (x = 150 cm, end of overhang)  

Geometry:
- Supported span A–C: 75 cm = 0.75 m  
- Overhang C–D: 75 cm = 0.75 m  

---

### Support Reactions

Take moments about A:

\[
R_C(75) - 724(150) = 0
\]

\[
R_C = \frac{724 \cdot 150}{75} = 1448\ \text{N}
\]

Vertical equilibrium:

\[
R_A + R_C - 724 = 0 \Rightarrow R_A = 724 - 1448 = -724\ \text{N}
\]

(negative sign indicates the support at A pushes downward on the beam in this static configuration)

---

### Maximum Deflection

Assume the bar is initially a **rectangular 3 cm × 3 cm steel bar**.

**Section properties:**

- Width \(b = 0.03\ \text{m}\)  
- Height \(h = 0.03\ \text{m}\)  

\[
I = \frac{b h^3}{12}
  = \frac{0.03(0.03)^3}{12}
  = 6.75 \times 10^{-7}\ \text{m}^4
\]

Material: steel  
\[
E = 200\ \text{GPa} = 200 \times 10^9\ \text{Pa}
\]

Treat the tip load at D as acting at the end of a 0.75 m overhang from support at C, with supported span \(L = 0.75\ \text{m}\).  
Using the standard formula for deflection at the end of an overhang with tip load \(W\):

\[
v_{\max} = \frac{W a^2 (3L - a)}{6 E I}
\]

Where:
- \(W = 724\ \text{N}\)  
- \(a = 0.75\ \text{m}\) (overhang length)  
- \(L = 0.75\ \text{m}\) (supported span)

Plugging in:

\[
v_{\max} = \frac{724 (0.75)^2 (3 \cdot 0.75 - 0.75)}{6 (200 \times 10^9) (6.75 \times 10^{-7})}
\]

\[
v_{\max} \approx 0.000753\ \text{m} = 0.753\ \text{mm}
\]

---

### Deflection Requirement

Total bar length:

\[
L_{\text{total}} = 1.5\ \text{m}
\]

Allowable deflection is 2% of the bar length:

\[
v_{\text{allow}} = 0.02 L_{\text{total}} = 0.02 \cdot 1.5 = 0.03\ \text{m} = 30\ \text{mm}
\]

Our computed deflection:

\[
v_{\max} = 0.753\ \text{mm} \ll 30\ \text{mm}
\]

#### The bar easily satisfies the deflection constraint.

---

## Redesigned Mass-Efficient Beam (Same Material, Same Area)

The original **area** of the 3 cm × 3 cm bar:

\[
A = 3\ \text{cm} \times 3\ \text{cm} = 9\ \text{cm}^2 = 9 \times 10^{-4}\ \text{m}^2
\]

To make the beam more mass-efficient (same area, larger \(I\)), choose a **taller, thinner rectangle**:

- Height \(h = 6\ \text{cm} = 0.06\ \text{m}\)  
- Width \(b = 1.5\ \text{cm} = 0.015\ \text{m}\)  

Check area:

\[
A_{\text{new}} = 0.015 \cdot 0.06 = 9 \times 10^{-4}\ \text{m}^2
\]

(same as original)

New moment of inertia:

\[
I_{\text{new}} = \frac{b h^3}{12}
= \frac{0.015 (0.06)^3}{12}
= 2.7 \times 10^{-7}\ \text{m}^4
\]

This taller, thinner section uses the same material but places more of it away from the neutral axis, increasing bending stiffness and reducing deflection.

---

# Final Results Summary

- **Rigid mechanism capacity:**  
  \[
  W_{\text{max}} = 724\ \text{N} \approx 74\ \text{kg}
  \]

- **Maximum beam deflection (initial 3 cm × 3 cm bar):**  
  \[
  v_{\max} = 0.753\ \text{mm} < 30\ \text{mm limit}
  \]

- **Mass-efficient redesign:**  
  A 6 cm × 1.5 cm rectangular cross-section (same area, higher stiffness, lower deflection).
