## Day 5: Power Planning, Routing, and GDSII Generation

## Overview
The final day of the workshop focused on completing the physical design flow by generating the Power Distribution Network (PDN), performing routing, validating timing after routing, and producing the final GDSII file for fabrication. This stage marks the transition from design implementation to tape-out readiness.

---

## Power Distribution Network in OpenLANE

## Role of PDN
A Power Distribution Network ensures reliable delivery of power and ground to every standard cell and macro within the chip. A well-designed PDN minimizes voltage drop, improves signal integrity, and enhances overall chip stability.

The PDN primarily distributes:
- VDD (power)
- VSS (ground)

across the core using rails and straps.

---

## PDN Generation Flow

## gen_pdn Execution
OpenLANE provides the `gen_pdn` procedure to automatically generate the power grid. This step constructs horizontal and vertical power rails and connects them to all power pins in the design.

The PDN stage relies on predefined technology and library information to maintain compatibility with the routing and placement stages.

---

## PDN Configuration Dependencies

## Required Variables
Before executing PDN generation, certain configuration variables must be correctly defined.

## LIB_SYNTH_COMPLETE
This variable must be present in the `config.tcl` file.
It is internally referenced by the PDN scripts to access complete synthesis libraries.

## LEF_MERGED_UNPADDED
This variable points to the merged LEF file without padding.
It provides structural information required for power grid creation.

Improper configuration of these variables may cause PDN generation to fail.

---

## Routing Stage

## Preparing for Routing
Before initiating routing, key routing-related variables were inspected to confirm the current design state.








