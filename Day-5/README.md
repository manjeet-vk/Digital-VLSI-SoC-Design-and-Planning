# Day 5: Power Planning, Routing, and GDSII Generation
## Overview

The final day of the workshop focused on completing the physical design flow by implementing the Power Distribution Network (PDN), performing routing, validating post-route timing, and generating the final GDSII file for fabrication. This stage represents the transition from design implementation to tape-out readiness.

## Power Distribution Network (PDN) in OpenLANE
## Purpose of PDN

The Power Distribution Network is responsible for delivering stable power and ground connections to all standard cells and macros across the chip. An efficient PDN minimizes IR drop, enhances signal integrity, and ensures reliable circuit operation.

The PDN distributes:

## VDD (power)

## VSS (ground)

across the core area using power rails and metal straps.

## PDN Generation Flow
## Execution of gen_pdn

OpenLANE provides the gen_pdn command to automatically generate the power grid. This step creates horizontal and vertical power rails and connects them to the power pins of all cells in the design.

PDN generation relies on predefined technology and library data to ensure compatibility with placement and routing stages.

## PDN Configuration Dependencies
## Required Variables

Before executing PDN generation, certain configuration variables must be correctly defined to avoid errors:

## LIB_SYNTH_COMPLETE
This variable must be specified in the config.tcl file. It is required by the PDN scripts to reference the complete synthesis libraries.

## LEF_MERGED_UNPADDED
This variable points to the merged LEF file without padding and provides essential layout information needed for power grid construction.

Incorrect or missing definitions of these variables can result in PDN generation failures.

## Routing Stage
## Preparation for Routing

Prior to starting the routing process, routing-related configuration variables were reviewed to ensure the design environment was correctly set up and ready for detailed routing.




