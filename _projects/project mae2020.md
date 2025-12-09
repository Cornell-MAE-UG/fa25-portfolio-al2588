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

Problem  
Design a lifting mechanism inside a 150 cm × 50 cm workspace using:

- one rigid 150 cm bar,
- three pin supports (two on the ground), and
- a linear actuator that can deliver up to 1.45 kN.

Goal: lift the maximum possible weight to a vertical height of 50 cm.

Constraints

- Design space: 150 cm horizontal × 50 cm vertical  
- Bar length: 150 cm (rigid in Step 1)  
- Actuator force acts along its own axis  
- Weight is attached at the far end of the bar  
- Actuator attaches to the bar 75 cm from the pivot  

Design degrees of freedom

- Placement of ground pins  
- Location of the bar pivot  
- Location of the actuator base on the ground  
- Location of the actuator attachment on the bar  
- Location of the weight along the bar  

---

### (b) Static Analysis of the Rigid Bar

When the weight has been lifted 50 cm, the 150 cm bar makes an angle

- theta = arctan(50 / 150) ≈ 18.43 degrees.

Coordinates (in cm)

- A (pivot): (0 , 0)  
- C (actuator attachment, 75 cm from A along the bar):

  - x_C = 75 * cos(theta) ≈ 71.3  
  - y_C = 75 * sin(theta) ≈ 23.7  

- D (weight at bar end, 150 cm from A):

  - x_D = 150 * cos(theta) ≈ 142.7  
  - y_D = 150 * sin(theta) ≈ 47.4  

The actuator is mounted vertically from the ground directly under C, so its force is vertical:

- F_act = 1.45 kN = 1450 N.

Moment arms about A

- Actuator moment arm: 71.3 cm (horizontal distance from A to C)  
- Weight moment arm: 142.7 cm (horizontal distance from A to D)

Taking moments about A (counterclockwise positive):

- 1450 N * 71.3 cm − W * 142.7 cm = 0  

Solve for W:

- W = (1450 * 71.3) / 142.7 ≈ 724 N.

Maximum liftable weight in the rigid-bar model

- W_max ≈ 724 N ≈ 74 kg.

---

### (c) Mechanism Description

- A 150 cm bar is pinned to the ground at point A.  
- The weight hangs at point D, 150 cm from A.  
- The actuator base is fixed to the ground directly below point C.  
- The actuator rod attaches to point C, which is 75 cm from A along the bar.  
- When the bar reaches an angle of about 18.4 degrees, the end of the bar is 50 cm above the ground and the mechanism can hold a weight of about 724 N.

---

## Step 2 — Beam Analysis (Flexible Bar)

![Rigid bar lifting mechanism](/assets/IMG_0909.jpeg)


Now the same bar is treated as a beam that can bend.

### Beam Model

Supports

- Pin support at A (x = 0 cm)  
- Vertical reaction at C from the actuator (x = 75 cm)  

Loads

- Upward 1450 N applied at C  
- Downward 724 N (the weight) applied at D, x = 150 cm  

Geometry

- Supported span A–C: L = 0.75 m  
- Overhang C–D: a = 0.75 m  

---

### Support Reactions

Distances are now in metres.

Moment equilibrium about A:

- R_C * 0.75 − 724 * 1.5 = 0  

Solve for R_C:

- R_C = (724 * 1.5) / 0.75 = 1448 N.

Vertical force equilibrium:

- R_A + R_C − 724 = 0  
  → R_A = 724 − 1448 = −724 N.

(The negative sign means the reaction at A acts downward on the beam in this loading configuration.)

---

### Maximum Deflection

Assume the bar is a solid rectangular steel bar.

Section dimensions

- Width b = 0.03 m (3 cm)  
- Height h = 0.03 m (3 cm)

Second moment of area (about the horizontal centroidal axis)

- I = b * h^3 / 12  
- I = 0.03 * (0.03^3) / 12 ≈ 6.75 × 10^(-7) m^4.

Material

- Steel with Young’s modulus E = 200 × 10^9 Pa.

Deflection formula for a point load W at the end of an overhang of length a beyond a simple support with span L:

- v_max = W * a^2 * (3L − a) / (6 * E * I).

Here

- W = 724 N  
- a = 0.75 m  
- L = 0.75 m  

Then

- v_max = 724 * (0.75^2) * (3 * 0.75 − 0.75) / (6 * 200e9 * 6.75e−7)  
- v_max ≈ 0.000753 m ≈ 0.753 mm.

---

### Deflection Requirement

Total bar length:

- L_total = 1.5 m.

Allowable deflection (2 percent of the length):

- v_allow = 0.02 * L_total = 0.02 * 1.5 = 0.03 m = 30 mm.

Comparison:

- v_max ≈ 0.753 mm  
- v_allow = 30 mm  

So

- v_max << v_allow.

Conclusion: the beam is much stiffer than required; its maximum deflection is far less than 2 percent of its length.

---

## Redesigned Mass-Efficient Beam (Same Material, Same Area)

Area of the original 3 cm × 3 cm bar

- A = 3 cm × 3 cm = 9 cm^2 = 9 × 10^(-4) m^2.

To use the material more efficiently, choose a taller, thinner rectangular section with the same area:

- New height h = 0.06 m (6 cm)  
- New width b = 0.015 m (1.5 cm)

Area check:

- A_new = b * h = 0.015 * 0.06 = 9 × 10^(-4) m^2  (same as original).

New second moment of area:

- I_new = b * h^3 / 12  
- I_new = 0.015 * (0.06^3) / 12 ≈ 2.7 × 10^(-7) m^4.

This taller, thinner section keeps the same amount of material but moves more of it away from the neutral axis, which increases bending stiffness and reduces deflection.

---

## Final Results Summary

- Maximum liftable weight in the rigid-bar model:  
  W_max ≈ 724 N (about 74 kg).

- Maximum beam deflection for a 3 cm × 3 cm steel bar:  
  v_max ≈ 0.753 mm, which is much smaller than the 30 mm limit (2 percent of the span).

- More efficient beam with the same area:  
  rectangular cross-section 6 cm × 1.5 cm, with I_new ≈ 2.7 × 10^(-7) m^4.
