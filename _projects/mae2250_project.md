---
layout: project
title: MAE 2250 – Grape Soup
description: Client Pitch and Functional Prototype
---

<div id="top"></div>

## Table of Contents
- [Client Pitch](#client-pitch)
- [Functional Prototype](#functional-prototype)

---

<h2 id="client-pitch">Client Pitch</h2>

**Project:** Preventing SLF Contamination in Grape Harvests  
**Team:** Grape Soup  
**Client(s):** Cornell CALS Extension / E&J Gallo Winery / National Grape  

### Problem Statement
Spotted lanternflies (SLFs) contaminate mechanically harvested grapes in infested vineyard regions. When insects on the vines are harvested along with the fruit, they can enter bins and downstream processing. This creates contamination issues for grape growers and processors and can reduce harvest quality and efficiency.

### Why It Matters
If this problem is solved, wineries can receive cleaner harvested fruit, reduce contamination during juice or wine processing, and spend less time on manual sorting and cleanup.

### Proposed Solution Direction
We propose a density-based separation system for use at the vineyard receiving area. Harvested material would first pass through an initial stage that removes excess liquid. The remaining solids, including grapes and SLFs, would then enter a flotation tank. Since grapes are heavier, they sink, while SLFs float and can be skimmed from the surface. Clean grapes would then exit through the bottom and continue to processing.

Our long-term goal is a standalone station integrated into winery receiving workflows. For the lab prototype, we built a small-scale proof of concept to test whether surface skimming could remove floating contaminants while keeping grape loss low.

### Key Risks / Unknowns
- Whether the density difference is large enough under realistic harvest conditions
- How damaged fruit, stems, and debris affect separation performance
- Whether water exposure could affect fruit quality or sanitation
- How easily the system could integrate into existing winery workflows

### Questions for the Client
1. What are the main workflow constraints in post-harvest processing? This helps determine where our system could fit into existing operations.
2. What percentage of harvested material is non-grape debris such as stems and leaves? This helps us design around real contamination conditions.

[View Client Pitch PDF](/assets/pdf/O3_GrapeSoup.pdf)

---

<h2 id="functional-prototype">Functional Prototype</h2>

**Prototype Goal:** Build and test a first functional mechanism that removes floating SLF-like material from the surface of a tank while allowing heavier grape analogs to remain below.

### Design Overview
Our prototype uses a storage container as the tank and a rotating paddle wheel mounted across the top. A hand crank turns the shaft, which rotates the paddles across the surface to skim floating material. This functional prototype was used to test motion, interference, fastening, and repeat use.

### Major Parts

#### Container
- Plastic storage container for food and beverage
- McMaster Code: 8993T46
- Quantity: 1
- Total Cost: $45.23

#### 3D-Printed Parts
- **Paddle (1):** PLA plastic, shaft about 12.5 in long and 1 in diameter, paddles about 10 in
- **Mounting Bracket (2):** PLA plastic, semicircular top to hold the shaft in place
- **Crank (1):** PLA plastic, about 1 in diameter where it mounts to the shaft, about 2.5 in handle, about 4 in length

#### Lab Makeshift Prototype Parts
- **Paddle (1):** cardboard shaft with wood panels
- **Crank (1):** cardboard and wood
- **Mounting Bracket (2):** wood

### Assembly Summary
1. Position the paddle assembly across the top of the storage container.
2. Place the mounting brackets on both sides to support the shaft.
3. Secure the brackets to the container.
4. Attach the crank to the shaft so manual rotation drives the paddle wheel.
5. Rotate the crank to move the paddle and skim floating material from the surface.

### Prototype Note
The printed CAD parts were still being processed at the time of the lab check-off, so a substitute prototype made from wood and cardboard was used to validate the same mechanical concept and dimensions before final printed parts were available.

### Design Tests

#### 1. Motion Test
**Goal:** Verify that the paddle rotates smoothly and continuously.  
**Method:** Rotate the crank for 10 full revolutions at about 20 rpm while observing the paddle wheel.  
**Measured Outcomes:**  
- Paddle completed 10/10 revolutions
- No visible slip between crankshaft and paddle hub
- No stoppage or sticking during rotation

**Result:** The paddle rotated 1:1 with the crank for all 10 revolutions with no binding.  
**Next Step:** Replace the hand crank with a motor in the next prototype.

#### 2. Interference Test
**Goal:** Ensure the paddles do not collide with the tank or bracket during motion.  
**Method:** Rotate the assembly for 10 full revolutions while checking clearance between paddles, walls, shaft, and brackets.  
**Measured Outcomes:**  
- No contacts with non-intended surfaces
- Target minimum clearance of at least 5 mm between paddles and tank walls

**Result:** No contact was observed, but the temporary wooden bracket setup required careful operation.  
**Next Step:** Use rigid 3D-printed brackets to improve reliability.

#### 3. Fastening and Stability Test
**Goal:** Confirm that the crank, shaft, and box stay secure during rotation.  
**Method:** Rotate the crank and paddle for 10 full rotations and observe translational movement of the box and bracket assembly.  
**Pass Criteria:**  
- Box does not visibly flex or shift
- Shaft remains seated and does not walk out

**Result:** Partial translation occurred in both directions along the bracket.  
**Next Step:** Replace tape mounting with through-bolts, washers, or clamps to reduce bracket translation and shaft wobble.

#### 4. Repeat Use / Cycling Test
**Goal:** Check whether the prototype loosens or degrades with repeated use.  
**Method:** Rotate the mechanism at about 60 rpm for 1 minute.  
**Pass Criteria:**  
- No cracks in paddles, hub, or bracket
- No tape peeling or bracket loosening
- No increase in wobble by more than 2 mm compared to pre-test

**Result:** The prototype functioned as expected with no visible damage or deviation.  
**Next Step:** Repeat the test using 3D-printed parts and the operating water level to verify stiffness, alignment, and clearance under more realistic conditions.

### Success Criteria
Our project aims to separate SLFs from harvested grape mixtures by using density-based sorting and surface skimming. A successful final system must remove floating SLFs while preserving grapes and operating reliably.

1. **Stable Mounting:** Brackets must remain securely mounted to the box so the system can operate for 3 consecutive trials without stalling or needing manual correction.  
2. **Effective SLF Removal:** The paddles should remove at least 80% of SLF analogs while limiting grape loss to 2%.  
3. **Surface-Only Engagement:** At the target speed, the paddle wheel should engage only the top surface layer and transfer 0 grapes to the discard compartment during a 60-second control test.

### Outcome
The prototype successfully demonstrated the core skimming motion and confirmed that the paddle mechanism can rotate consistently without interference. The biggest issue found was fastening and bracket stability, which will be improved in the next iteration using more rigid parts and better mounting hardware.

[View Functional Prototype PDF](/assets/pdf/Functional_Prototype.pdf)

[Back to top](#top)