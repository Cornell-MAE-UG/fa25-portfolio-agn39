---
layout: project
title: Final Homework Part II - Wrench Design
description: Final design project that integrates multiple softwares and technologies to create a working design of a wrench.
technologies: [Autodesk Fusion, Solid Works, Ansys Workbench, Python, Granta]
image: /assets/images/Screenshot 2025-12-09 231553.png
---

As our final wrench design, my partner (Navya Penati ngp42) and I iterated our design through testing different material choices and dimensions to create a working wrench design that fits all of the specified design requirements. This includes the factors of safety for strength, crack, and fatigue as well as the required electrical output of our chosen strain gauge. Details on our dimensions, material choice, and analysis using Ansys are described below:

[Final Homework Part II]({{ "/MAE 3270 Final Project Part 2.pdf" | relative_url }}) in PDF format.

**Navya Penati (ngp42) and Amanda Nicholson (agn39) Final Project Part II**

**5.2.1 Results**
**Images of CAD model. Must show all key dimensions**	

From the baseline design, our wrench has smaller handle dimensions as well as an additional fillet at the base of the drive. These dimensions are shown in Figure 1.

Figure 1: Wrench Design Dimensions

![image here](assets/images/cadmodel.png)


**Describe material used and its relevant mechanical properties**

Our final design uses High Alloy Steel, AerMet 100 (solution treated and aged). This material was chosen because it is both strong and durable and allows the handle dimensions to be reduced for higher strain sensitivity while obtaining all required safety factors. Its mechanical properties are: Young’s modulus = 28 x 10^6 psi, Poisson’s ratio = 0.30, yield/tensile strength = 235 ksi, fracture toughness = 91,000 psi√(in), and fatigue strength at 10^6 cycles = 135 ksi. These properties ensure that the design meets and exceeds the requirements for yield, fracture, and fatigue safety margins. 

**Diagram communicating how loads and boundary conditions were applied to your FEM model**.

In Ansys mechanical, the boundary conditions and loads can be applied in the static structural tab. Figure 2 shows the streamline process of adding the clamped boundary condition by hiding the fillet body, selecting the faces of the drive, and adding a displacement boundary of 0 at each face for each axial direction. Figure 3 shows the process of adding the load given 600 lb-in torque at the end of the handle. Note that the applied load is 600 lb-in/8 in = 75 lbf since the length of our handle from the center of the drive is 8in

Figure 2: Adding Clamped Boundary
















Figure 2: Adding Load to End of Handle



**Normal Strain contours (in the strain gauge direction) for FEM**

The contour plot for normal strain shown in Figure 4 was obtained after using a mesh size of 0.25 in for the handle and 0.06 in for both of the drive components. Note that the direction of the strain gauge is along the x-axis (not the z-axis originally provided by the baseline design)

Figure 4: Normal Elastic Strain (X Axis) PRE Mesh Refinement



After refining the original mesh size to 0.1in and 0.02 in for the handle and drive components respectively, the contour plot for normal elastic strain was obtained and is shown in Figure 5.
Figure 5: Normal Elastic Strain (X Axis) POST Mesh Refinement




**Contour plot of maximum principal stress for FEM**

The following are contour plots of the max principal stress, which is seen to be concentrated around the fillet of the drive as well as near the strain gauge location

Figure 6: Maximum Principal Stress
Pre Mesh Refinement 

Post Mesh Refinement




**Summarize results from FEM calculation showing maximum normal stress (anywhere), load point deflection, strains at the strain gauge locations**


Figure 7: Normal Stress
Pre Mesh Refinement

Post Mesh Refinement




Figure 8: Load Point Deflection (Directional)
Pre Mesh Refinement

Post Mesh Refinement




Figure 9: Maximum Strain Values Over Time 
Pre Mesh Refinement
Post Mesh Refinement 




The FEM analysis produced three important results for testing and evaluating the performance of the final torque wrench design. As seen in Figure 7, the maximum normal stress for the model was significantly high for both versions of mesh in comparison to the hand calculations (79,402 ksi and 1.06e5 ksi pre and post mesh refinement respectively). These stresses were concentrated around the drive/fillet of the drive. After probing around the handle near the gauge location, we observed a normal stress of  approximately 32 ksi which was the max stress predicted by our hand calculations. The load-point deflection under the 600 in-lbf torque was 0.0973 in (Figure 8), which is slightly more than the 0.0694 in predicted by our calculations. This shows that the handle was stiff but still allowed bending strain. Probing for the strain at the center of the strain gauge yields the results shown in Figure 9. Given that our gauge length is oriented in the x-axis, the strain at the gauge location was observed as 1,057 microstrain, which is better than expected when it comes to achieving the required electrical output.

**Torque wrench sensitivity in mV/V using strains from FEM analysis**

Further probing of strain at the point of the center of the strain gauge on the handle allows us to see the exact strain at the location of the gauge. The details for maximum values of strain at the probed location are shown in Figure 5 for both before and after mesh refinement. Note that the strain gauge is oriented along the x-axis given the wrench geometry in Ansys.

Given the values of the Normal -X Axis max strain over time, we can calculate the sensitivity of our wrench using the output of a half-bridge strain gauge:

Pre mesh refinement:
Gauge output  =2k/4 =103 mV/V=1.057mV/V
	
Post mesh refinement:
Gauge output  =2k/4=103 mV/V=1.0563 mV/V

Both versions of the mesh produce an output/sensitivity that meets the design requirements (> 1mV/V).
	
**Strain gauge selected (give type and dimensions). Note that design must physically have enough space to bond the gauges**
	
We decided to use two SGD-6/120-LY11 strain gauges in a half bridge configuration with one gauge on the side of the handle in tension and the other gauge on the side of the handle in compression. This gauge is 0.449 inches in total length, 0.201 inches in total width, and has an active gauge area of 0.0312 in2. We chose this strain gauge because it is flat and fits the dimensions of our handle thickness. Figure 10 shows the layout of the gauge.

Figure 10: SGD-6/120-LY11 Strain Gauge Selection

Note: Image and dimensions were obtained from the vendor site: https://www.dwyeromega.com/en-us/linear-strain-gages/p/SGD-LINEAR1-AXIS# 






Additional: Raw Manual Calculations Output

~~~~~~ MATERIAL CHOICE:  High alloy steel, AerMet 100, solution treated & aged ~~~~~~

Material properties:
Young's modulus (psi):  28000000
Poisson's ratio:  0.3
tensile strength (or yield strength) (psi):  235000
fracture toughness (psi sqrt(in)):  91000
fatigue strength for 10^6 cycles (psi):  135000
price per unit volume (USD/in^3):  4.8032407407407405
density (lb/in^3):  0.286

Dimensions:
length: L =  8 in
width: h =  0.71 in
thickness: b =  0.22 in
volume: V =  1.3199125 in^3

price:  6.339857494212962 USD
mass:  0.37749497499999995 lb

~~~~~~ OUTPUTS FOR  High alloy steel, AerMet 100, solution treated & aged ~~~~~~

Stress and deflection analysis:
load point deflection:  0.06966833915432871 in
max normal stress:  32.46109177472003 ksi

factor of safety results:
factor of safety for strength:  7.23943611111111
requirement satisfied.

factor of safety for crack growth:  7.060822843142121
requirement satisfied.

factor of safety for fatigue:  4.158824999999999
requirement satisfied.

strain gauge results:
strain at gauge:  1014.4091179600009 microstrain
output (600 in-lbf using half-bridge):  1.014409117960001 mV/V
requirement satisfied.


