---
layout: project
title: Heat exchanger
description: An analysis of the heat exchanger lab
image: /assets/images/IMG_4414.jpeg
---

# Heat exchanger

## Purpose and real-world relevance

In this lab we analyzed a real water-to-water heat exchanger and compared its performance in parallel-flow and counterflow configurations. Our goals were to:

1. Describe how the exchanger works physically  
2. Apply mass, energy, and entropy balances to a real system  
3. Determine how changing an operating/design condition changes performance  

Heat exchangers like this are central to many engineering systems, including car radiators, HVAC units, power-plant condensers and feedwater heaters, chemical reactors with cooling jackets, and refrigeration systems. This lab provided a realistic thermodynamics outcome to share with employers.

---

## Device description (qualitative)

A heat exchanger transfers heat from a hot fluid to a cold fluid **without mixing** the two fluids. The fluids flow through separate channels, and heat moves through the wall from the hotter side to the colder side. As the hot fluid releases heat and cools down, the cold fluid absorbs that heat and warms up.

### Flow arrangements

- **Parallel flow:** both fluids move in the same direction. The temperature difference is largest at the inlet and decreases quickly along the exchanger length, which generally reduces heat transfer.  
- **Counterflow:** fluids move in opposite directions. This maintains a larger temperature difference over more of the exchanger length, generally increasing heat transfer and improving cold-side heating.

Starting the hot fluid at a higher temperature increases the temperature difference, allowing more heat to transfer in both arrangements (counterflow benefits the most).

---

## Photos and schematics


- Figure 1. Initial setup for parallel flow
 <img src="/assets/images/IMG_4411.jpeg" width="260" align="left" style="margin: 0 18px 12px 0; border-radius: 10px;">
- Figure 2. Parallel flow in process  
- Figure 3. Counterflow in process  
- Figure 4. Heat exchanger inside  


---

## Measurements

### Table 1. Temperature and flow measurements

| Run | Configuration | Cold Inlet Tc,in (°C) | Hot Inlet Th,in (°C) | Cold Outlet Tc,out (°C) | Hot Outlet Th,out (°C) | Flow Rate (gal/hr) |
|---:|---|---:|---:|---:|---:|---:|
| 1 | Parallel flow | 6.8 | 40.0 | 15.9 | 24.6 | 210 |
| 2 | Parallel flow | 8.7 | 35.0 | 21.1 | 23.7 | 210 |
| 3 | Counterflow | 9.2 | 35.0 | 22.1 | 18.0 | 210 |
| 4 | Counterflow (hotter start) | 10.0 | 40.0 | 23.9 | 19.6 | 210 |

### Table 2. Heat transfer results (as reported)

| Run | Tc (K) | Qc (kW) | Th (K) | Qh (kW) |
|---:|---:|---:|---:|---:|
| 1 | 9.1 | 8.40 | 15.4 | 14.21 |
| 2 | 12.4 | 11.44 | 11.3 | 10.43 |
| 3 | 12.9 | 11.91 | 17.0 | 15.69 |
| 4 | 13.9 | 12.83 | 20.4 | 18.83 |

**Observation:** Based on the cold-side measurements, the exchanger transferred roughly **8–13 kW** across our runs.

We expect some mismatch between **Qc** and **Qh** because of real-system effects (heat loss from tubing/exchanger to the room, unequal pump flow rates, imperfect reservoir mixing, and thermometer lag/placement). This is typical outside ideal textbook conditions.

### Table 3. Effectiveness (ε)

| Run | Configuration | ε |
|---:|---|---:|
| 1 | Parallel | 0.27 |
| 2 | Parallel | 0.47 |
| 3 | Counterflow | 0.50 |
| 4 | Counterflow (hotter start) | 0.46 |

---

## Comparison (matched inlet conditions)

For the fairest comparison between flow arrangements, we compared **Run 2 (parallel)** and **Run 3 (counterflow)** because they began with nearly the same hot-side inlet temperature (~35 °C) and very similar cold-side inlet temperatures. Under these matched conditions, the **counterflow** setup performed slightly better: it achieved a higher effectiveness and transferred heat to the cold stream at a slightly greater rate than the parallel-flow setup.

---

## Conclusions

- Cold-side heat transfer rates were roughly **8–13 kW**.  
- Under similar inlet conditions, **counterflow** produced higher effectiveness (**0.50**) than **parallel flow** (**0.47**).  
- Increasing hot-reservoir inlet temperature in counterflow increased heat transfer by about **8%**.  
- Energy-rate mismatches between sides were expected due to real losses and uneven flow.

Overall, this experiment provided a concrete example of applying mass, energy, and entropy balances to a real device, and it showed how both a design change (flow arrangement) and an operating change (hot inlet temperature) affect heat-exchanger performance.
