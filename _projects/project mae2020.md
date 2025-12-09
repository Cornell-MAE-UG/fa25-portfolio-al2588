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

**Problem**  
Design a lifting mechanism inside a 150 cm × 50 cm workspace using a rigid 150 cm bar, three pin supports (two on the ground), and a linear actuator that can deliver up to **1.45 kN**.  
The goal is to lift the maximum possible weight to a vertical height of **50 cm**.

**Constraints**

- Design space: 150 cm horizontal × 50 cm vertical  
- Bar length: 150 cm (treated as rigid in Step 1)  
- Actuator force acts along its axis only  
- Weight is attached at the far end of the bar  
- Actuator attaches to the bar 75 cm from the pivot  

**Design Degrees of Freedom**

- Placement of ground pins  
- Location of the bar pivot  
- Location of actuator base on the ground  
- Location of actuator attachment on the bar  
- Location of the weight along the bar  

---

### (b) Static Analysis of the Rigid Bar

The bar lifts the weight when the end of the bar reaches 50 cm height.  
With bar length 150 cm, the bar angle is

$ \theta = \tan^{-1}\left(\dfrac{50}{150}\right) \approx 18.43^\circ. $

**Coordinates (cm)**

- A (pivot): $(0,\ 0)$  
- C (actuator attach, 75 cm from A along the bar):  
  - $x_C = 75\cos\theta = 71.3$  
  - $y_C = 75\sin\theta = 23.7$  
- D (weight at bar end, 150 cm):  
  - $x_D = 150\cos\theta = 142.7$  
  - $y_D = 150\sin\theta = 47.4$

The actuator is mounted vertically from the ground directly under C, so its force is vertical:

$ F_{\text{act}} = 1.45\ \text{kN} = 1450\ \text{N}. $

**Moment arms about A**

- Actuator moment arm: $71.3$ cm  
- Weight moment arm: $142.7$ cm  

Moment equilibrium about A:

$$
1450 \cdot 71.3 = W \cdot 142.7
$$

Solving for the weight:

$$
W = \dfrac{1450 \cdot 71.3}{142.7} \approx 724\ \text{N}
$$

**Maximum liftable weight (rigid mechanism)**

$ W_{\text{max}} \approx 724\ \text{N} \approx 74\ \text{kg}. $

---

### (c) Mechanism Description

- Bar: 150 cm long, pinned at A.  
- Weight: attached at D, 150 cm from A.  
- Actuator: base fixed to the ground below C, rod attached to C at 75 cm from A.  
- At the lifted position, the bar makes an angle $\theta \approx 18.4^\circ$ and the weight is 50 cm above the ground.  

---

## Step 2 — Beam Analysis (Flexible Bar)

In this step, the same bar is treated as a **beam** that can bend.

### Beam Model

Supports:

- Pin support at A (x = 0 cm)  
- Vertical reaction at C from the actuator (x = 75 cm)  

Loads:

- Upward load $1450\ \text{N}$ at C  
- Downward load $724\ \text{N}$ at D (x = 150 cm)  

Geometry:

- Supported span A–C: $L = 0.75\ \text{m}$  
- Overhang C–D: $a = 0.75\ \text{m}$  

---

### Support Reactions

Take moments about A (with distances in metres):

$$
R_C \cdot 0.75 - 724 \cdot 1.5 = 0
$$

$$
R_C = \dfrac{724 \cdot 1.5}{0.75} = 1448\ \text{N}
$$

Vertical equilibrium:

$$
R_A + R_C - 724 = 0 \quad\Rightarrow\quad R_A = 724 - 1448 = -724\ \text{N}
$$

(The negative sign indicates the support at A pushes downward on the beam in this configuration.)

---

### Maximum Deflection

Assume the bar is initially a **solid rectangular steel bar**:

- Width $b = 0.03\ \text{m}$ (3 cm)  
- Height $h = 0.03\ \text{m}$ (3 cm)  

Second moment of area:

$$
I = \dfrac{b h^3}{12}
  = \dfrac{0.03 \cdot (0.03)^3}{12}
  = 6.75 \times 10^{-7}\ \text{m}^4
$$

Material modulus (steel):

$ E = 200 \times 10^9\ \text{Pa}. $

Treat the downward weight at D as a tip load on a 0.75 m overhang beyond support C, with supported span $L = 0.75\ \text{m}$.  
Using the standard formula for vertical deflection at the end of an overhang with tip load $W$:

$$
v_{\max}
= \dfrac{W a^2 (3L - a)}{6 E I}
$$

Substitute $W = 724\ \text{N}$, $a = 0.75\ \text{m}$, $L = 0.75\ \text{m}$:

$$
v_{\max}
= \dfrac{724 \cdot (0.75)^2 \cdot (3 \cdot 0.75 - 0.75)}{6 \cdot (200 \times 10^9) \cdot (6.75 \times 10^{-7})}
\approx 0.000753\ \text{m}
$$

So

$ v_{\max} \approx 0.753\ \text{mm}. $

---

### Deflection Requirement

Total bar length:

$ L_{\text{total}} = 1.5\ \text{m}. $

Allowable deflection (2% of the length):

$$
v_{\text{allow}} = 0.02 L_{\text{total}} = 0.02 \cdot 1.5 = 0.03\ \text{m} = 30\ \text{mm}
$$

Comparison:

$ v_{\max} = 0.753\ \text{mm} \ll 30\ \text{mm}. $

**Conclusion:** the bar is far stiffer than required; its deflection is well below 2% of the span.

---

## Redesigned Mass-Efficient Beam (Same Material, Same Area)

The original 3 cm × 3 cm bar has:

$$
A = 3\ \text{cm} \times 3\ \text{cm} = 9\ \text{cm}^2 = 9 \times 10^{-4}\ \text{m}^2
$$

To use the material more efficiently, choose a **taller, thinner rectangular section** with the same area:

- Height $h = 0.06\ \text{m}$ (6 cm)  
- Width $b = 0.015\ \text{m}$ (1.5 cm)  

Area check:

$$
A_{\text{new}} = b h = 0.015 \cdot 0.06 = 9 \times 10^{-4}\ \text{m}^2
$$

New second moment of area:

$$
I_{\text{new}} = \dfrac{b h^3}{12}
= \dfrac{0.015 \cdot (0.06)^3}{12}
= 2.7 \times 10^{-7}\ \text{m}^4
$$

This taller, thinner section uses the same amount of material but moves more of it away from the neutral axis, increasing bending stiffness and further reducing deflection.

---

## Final Results Summary

- **Maximum liftable weight (rigid-bar model):**  
  $ W_{\text{max}} \approx 724\ \text{N} \approx 74\ \text{kg} $

- **Maximum beam deflection (3 cm × 3 cm bar):**  
  $ v_{\max} \approx 0.753\ \text{mm} < 30\ \text{mm}$ (2% limit)

- **More efficient beam design (same area):**  
  Tall, thin rectangle 6 cm × 1.5 cm with  
  $ I_{\text{new}} = 2.7 \times 10^{-7}\ \text{m}^4 $.
