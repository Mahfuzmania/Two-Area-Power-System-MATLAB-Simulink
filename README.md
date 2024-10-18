# Two-Area Power System Modeling using MATLAB Simulink

## Project Overview
This project models a two-area power system connected by a tie line using MATLAB Simulink. The simulation analyzes the effects of a sudden load change in one area, including frequency deviations and power flows between the areas. The model uses transfer functions for governors, turbines, and generators, allowing for a comprehensive analysis of system dynamics.

**Key Features:**
- Two-area power system modeling.
- Analysis of load changes and frequency deviations.
- MATLAB Simulink model with transfer functions.
- Tie-line power flow analysis between two areas.

## Problem Statement
The model simulates a two-area power system where a sudden load change of 187.5 MW occurs in Area 1. This change affects the frequency and power flow between the two areas. The goal is to determine the new steady-state frequency and the change in tie line power flow between the areas.

## Objectives
1. Model the dynamics of two interconnected power systems.
2. Analyze the effects of a load change on system frequency and tie-line power flow.
3. Simulate the system using MATLAB Simulink and verify results.

## Methodology
### System Parameters
- **Speed Regulation:**
  - Area 1: \(R_1 = 0.05\)
  - Area 2: \(R_2 = 0.0625\)
- **Frequency-sensitive load coefficient:**
  - Area 1: \(D_1 = 0.6\)
  - Area 2: \(D_2 = 0.9\)
- **Inertia Constant:**
  - Area 1: \(H_1 = 5\)
  - Area 2: \(H_2 = 4\)
- **Governor Time Constants:**
  - Area 1: \(Tg_1 = 0.2s\)
  - Area 2: \(Tg_2 = 0.3s\)
- **Turbine Time Constants:**
  - Area 1: \(Tt_1 = 0.5s\)
  - Area 2: \(Tt_2 = 0.6s\)

### MATLAB Simulink Modeling
The system was modeled using transfer functions for the governors, turbines, generators, and loads in both areas. A tie line connects the two areas, ensuring power flow between them.

The model simulates the effect of a 187.5 MW load increase in Area 1. The transfer functions for the components are:
- **Governor (Area 1):** \( \frac{1}{0.2s + 1} \)
- **Turbine (Area 1):** \( \frac{1}{0.5s + 1} \)
- **Inertia and Load (Area 1):** \( \frac{1}{10s + 0.6} \)
- **Governor (Area 2):** \( \frac{1}{0.3s + 1} \)
- **Turbine (Area 2):** \( \frac{1}{0.6s + 1} \)
- **Inertia and Load (Area 2):** \( \frac{1}{8s + 0.9} \)

### Results
After a 187.5 MW load change in Area 1, the following results were observed:
- **Frequency Deviation in Area 1:** \(\Delta F_1 = -0.3\) Hz
- **Final Frequency in Area 1:** \(F_1 = 59.7\) Hz
- **Frequency Deviation in Area 2:** \(\Delta F_2 = -0.3\) Hz
- **Final Frequency in Area 2:** \(F_2 = 59.7\) Hz
- **Change in Mechanical Power in Area 1:** \( \Delta P_{m1} = 100\) MW
- **Change in Mechanical Power in Area 2:** \( \Delta P_{m2} = 80\) MW
- **Tie Line Power Flow:** \(\Delta P_{12} = -84.5\) MW

**Note:** The system did not fully recover to 60 Hz, indicating a frequency drop that led to a 7.5 MW shortfall in the total load.

### Corrected System
The corrected system design showed:
- **Final Frequency in both areas:** 60 Hz
- **Change in Mechanical Power in Area 1:** 187.5 MW
- **Change in Mechanical Power in Area 2:** 0 MW
- **Tie Line Power Flow:** 0 MW (no power flows from Area 2 to Area 1 in the corrected system).

## Controlling Techniques
To maintain system frequency and avoid power flow discrepancies, a load frequency control (LFC) method was employed, using the area control error (ACE):
\[ ACE_i = \sum \Delta P_{ij} + K_i \times \Delta \omega \]
Where \( K_i \) is the area bias factor, calculated as:
\[ B_i = \frac{1}{R_i + D_i} \]

For the two-area system:
- \( B_1 = 20.6 \)
- \( B_2 = 16.9 \)

## Tools and Technologies
- **Programming Language:** MATLAB Simulink
- **Techniques:** Load Frequency Control, Power System Modeling
- **Data:** Power system parameters based on a 1000 MVA base.

## Conclusion
This project successfully models the dynamic behavior of a two-area power system in response to load changes. The Simulink model allows for analysis of frequency deviations, tie-line power flow, and the implementation of control techniques to restore system balance.

