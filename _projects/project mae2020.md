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
Design a lifting mechanism inside a 150 cm × 50 cm workspace using a rigid 150 cm bar, three pin supports (two on the ground), and a linear actuator that can deliver up to 1.45 kN.  
The goal is to lift the maximum possible weight to a vertical height of 50 cm.

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

- theta = arctan(50 / 150) ≈ 18.43 degrees.

**Coordinates (cm)**

- A (pivot): (0, 0)  
- C (actuator attach, 75 cm from A along the bar):  
  - x_C = 75 * cos(theta) ≈ 71.3  
  - y_C = 75 * sin(theta) ≈ 23.7  
- D (weight at bar end, 150 cm):  
  - x_D = 150 * cos(theta) ≈ 142.7  
  - y_D = 150 * sin(theta) ≈ 47.4  

The actuator is mounted vertically from the ground directly under C, so its force is vertical:

- F_act = 1.45 kN = 1450 N

**Moment arms about A**

- Actuator moment arm: 71.3 cm  
- Weight moment arm: 142.7 cm  

Moment equilibrium about A:

- 1450 * 71.3 = W * 142.7

Solve for W:

- W = (1450 * 71.3) / 142.7 ≈ 724 N

**Maximum liftable weight (rigid mechanism)**

- W_max ≈ 724 N ≈ 74 kg

---

### (c) Mechanism Description

- Bar: 150 cm long, pinned at A.  
- Weight: attached at D, 150 cm from A.  
- Actuator: base fixed to the ground below C, rod attached to C at 75 cm from A.  
- At the lifted position, the bar makes an angle of about 18.4 degrees and the weight is 50 cm above the ground.  

---

## Step 2 — Beam Analysis (Flexible Bar)

![beam lifting mechanism](/assets/images/IMG_0909.jpeg)


In this step, the same bar is treated as a beam that can bend.

### Beam Model

Supports:

- Pin support at A (x = 0 cm)  
- Vertical reaction at C from the actuator (x = 75 cm)  

Loads:

- Upward 1450 N at C  
- Downward 724 N at D (x = 150 cm)  

Geometry:

- Supported span A–C: L = 0.75 m  
- Overhang C–D: a = 0.75 m  

---

### Support Reactions

Take moments about A (distances in metres):

- R_C * 0.75 − 724 * 1.5 = 0  
  ⇒ R_C = (724 * 1.5) / 0.75 = 1448 N

Vertical equilibrium:

- R_A + R_C − 724 = 0  
  ⇒ R_A = 724 − 1448 = −724 N

(The negative sign indicates the support at A pushes downward on the beam in this configuration.)

---

### Maximum Deflection

Assume the bar is initially a solid rectangular steel bar:

- Width b = 0.03 m (3 cm)  
- Height h = 0.03 m (3 cm)  

Second moment of area:

- I = b * h^3 / 12  
- I = 0.03 * (0.03)^3 / 12  
- I ≈ 6.75 × 10^-7 m^4

Material modulus (steel):

- E = 200 × 10^9 Pa

For a tip load W on an overhang of length a beyond a simple support with span L, the vertical deflection at the tip is

- v_max = W * a^2 * (3L − a) / (6 * E * I)

Use:

- W = 724 N  
- a = 0.75 m  
- L = 0.75 m  

Then

- v_max ≈ 0.000753 m = 0.753 mm

---

### Deflection Requirement

Total bar length:

- L_total = 1.5 m

Allowable deflection (2% of the length):

- v_allow = 0.02 * L_total = 0.02 * 1.5 = 0.03 m = 30 mm

Comparison:

- v_max = 0.753 mm << 30 mm

**Conclusion:** the bar is much stiffer than required; its deflection is well below 2% of the span.

---

## Redesigned Mass-Efficient Beam (Same Material, Same Area)

The original 3 cm × 3 cm bar has area

- A = 3 cm × 3 cm = 9 cm² = 9 × 10^-4 m²

To use the material more efficiently, choose a taller, thinner rectangular section with the same area:

- Height h = 0.06 m (6 cm)  
- Width b = 0.015 m (1.5 cm)  

Area check:

- A_new = b * h = 0.015 * 0.06 = 9 × 10^-4 m² (same as original)

New second moment of area:

- I_new = b * h^3 / 12  
- I_new = 0.015 * (0.06)^3 / 12  
- I_new ≈ 2.7 × 10^-7 m^4

This taller, thinner section uses the same amount of material but moves more of it away from the neutral axis, increasing bending stiffness and further reducing deflection.

---

## Final Results Summary

- Maximum liftable weight (rigid-bar model):  
  W_max ≈ 724 N ≈ 74 kg

- Maximum beam deflection (3 cm × 3 cm bar):  
  v_max ≈ 0.753 mm < 30 mm (2% limit)

- More efficient beam design (same area):  
  Tall, thin rectangle 6 cm × 1.5 cm with  
  I_new ≈ 2.7 × 10^-7 m^4.
