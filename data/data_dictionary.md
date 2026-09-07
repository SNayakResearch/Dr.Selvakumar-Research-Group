# MOFDB25 Data Dictionary

This file is a template for the formal data dictionary accompanying MOFDB25.

| Feature | Description | Category | Data Type | Unit | Missing Convention |
|---|---|---|---|---|---|
| Catalyst_ID | Unique catalyst identifier | Metadata | ID | — | — |
| Paper_ID | Source publication identifier | Metadata | ID | — | — |
| Current_Density | HER current density | Electrochemical | Numerical | mA cm^-2 | NR |
| Overpotential | HER overpotential | Electrochemical | Numerical | mV | NR |
| Tafel_Slope | Tafel slope | Electrochemical | Numerical | mV dec^-1 | NR |
| Kinetics_Mechanism | HER kinetic/mechanistic class | Electrochemical | Categorical | — | NR |
| Exchange_Current_Density | Exchange current density | Electrochemical | Numerical | source-reported | NR |
| Onset_Potential | HER onset potential | Electrochemical | Numerical | source-reported | NR |
| Electrochemical_Medium | Electrolyte/medium | Electrochemical | Categorical | — | NR |
| Acidic_Alkaline | Medium classification | Electrochemical | Categorical | — | NR |
| Encoded_Medium | Encoded electrochemical medium | Electrochemical | Numerical/Categorical | — | NR |
| Rct | Charge-transfer resistance | Electrochemical | Numerical | ohm | NR |
| Rs | Solution resistance | Electrochemical | Numerical | ohm | NR |
| Cdl | Double-layer capacitance | Electrochemical | Numerical | source-reported | NR |
| ECSA | Electrochemically active surface area | Electrochemical | Numerical | source-reported | NR |
| Additives | Electrolyte/additives | Electrochemical | Categorical/Text | — | NR |
| Nafion | Nafion used | Electrochemical | Binary | — | NR |
| Mass_Loading | Catalyst mass loading | Electrochemical | Numerical | source-reported | NR |
| BET_Surface_Area | BET surface area | Morphological | Numerical | m2 g^-1 | NR |
| Pore_Size | Pore size | Morphological | Numerical | source-reported | NR |
| Pore_Volume | Pore volume | Morphological | Numerical | source-reported | NR |
| Graphitization_Index | Raman ID/IG | Morphological | Numerical | — | NR |
| Synthesis_Method | Synthesis route | Synthetic | Categorical | — | NR |
| Precursor_Reagents | Precursor reagents | Synthetic | Text/Categorical | — | NR |
| Precursor_Solvents | Precursor solvents | Synthetic | Text/Categorical | — | NR |
| MOF_Used | Parent MOF | Synthetic | Categorical | — | NR |
| MOF_Metal | MOF metal | Synthetic | Categorical | — | NR |
| TM_O_S_N_C_P_Chl | Transition-metal/heteroatom descriptor | Synthetic | Categorical/Text | — | NR |

**Important:** The final data dictionary should preserve the exact column names, definitions, units, encodings, and conventions used in the released MOFDB25 dataset.
