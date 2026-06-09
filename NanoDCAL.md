# NanoDCAL: Quantum Transport from First Principles

> A quantum transport simulator that predicts how electrons flow through a device, from a single molecule between two electrodes to a sub-nanometer transistor, directly from first principles.

Welcome to NanoDCAL on qBraid. This page introduces what NanoDCAL computes, walks you through the bundled device examples, and gets you to your first transport calculation in a few clicks. The software and all example notebooks are pre-installed in the qBraid environment, so there is nothing to set up.

## Overview

NanoDCAL (Nanoacademic Device Calculator) is a quantum transport package developed by Nanoacademic Technologies. It is an atomic-orbital implementation of the NEGF-DFT method, which couples Density Functional Theory (DFT) with the Keldysh non-equilibrium Green's function (NEGF) formalism. This combination is what makes NanoDCAL a genuine device simulator rather than a bulk-structure tool: it computes current, conductance, and transmission for open systems under a finite bias, accounting for the non-equilibrium quantum statistics that govern a working device.

The workflow is conceptually simple. DFT determines the Hamiltonian of the nanostructure with full atomic detail, while NEGF supplies the non-equilibrium statistical occupation through the Keldysh formalism. The two are solved self-consistently, so the charge density, the electrostatic potential, and the transport properties are mutually consistent at every applied voltage.

## Why it matters

Predicting the electronic structure of a material is only half the story for nanoelectronics. The question that ultimately matters is how a device behaves when it is connected to electrodes and a voltage is applied. NanoDCAL answers that question directly, providing current-voltage characteristics and transmission spectra that can be compared against experiment and used to evaluate device concepts before they are fabricated. For molecular electronics, spintronics, and ultra-scaled transistors, this is the difference between a structural model and a performance prediction.

## Device types

NanoDCAL is organized around the geometry of the problem, from closed systems to multi-terminal devices:

| Configuration | Use case |
| --- | --- |
| 0-probe | Isolated molecules and periodic crystals via supercells |
| 1-probe | Surfaces with semi-infinite geometry |
| 2-probe | Open device structures with leads (the primary use case) |
| Multi-probe | Structures with several electrodes |

Leads can be one-, two-, or three-dimensional, and the package handles device structures of up to roughly 1,000 atoms.

## What you can compute

- **Transport:** transmission coefficients, conductance and resistance, and nonlinear, non-equilibrium current-voltage (I-V) characteristics.
- **Electronic structure:** total and local density of states, band structure, current density, and scattering states.
- **Spin:** spin-polarized transport, with collinear and non-collinear treatments and spin-orbit coupling.
- **Forces and vibrations:** atomic forces, structural optimization, and vibrational properties including electron-phonon coupling.
- **Beyond DC:** photocurrent, thermal and thermoelectric transport, gate fields included self-consistently for leads with finite cross-section, and external AC voltages applied on top of a DC bias (experimental).

## Hands-on examples

The qBraid environment ships with the full set of official NanoDCAL tutorials as ready-to-run notebooks, organized by topic. Each one is self-contained and annotated.

1. **Electronic structure.** Compute the fat-band structure of a PtSe2 monolayer. *Key takeaway:* extracting orbital-resolved band structure from a first-principles calculation.
2. **Molecular electronics.** Build simple molecular devices and explore their dynamic (AC) conductance. *Key takeaway:* the core two-probe workflow, from self-consistency to transmission and the current-voltage curve.
3. **Spin devices.** Study spin-resolved transport in a zigzag graphene nanoribbon, a nickel-graphene interface, and with DFT+U. *Key takeaway:* resolving transport by spin channel for spintronics applications.
4. **Semiconductor devices.** Account for spin-orbit interaction, carrier effective mass, and complex energy band structure. *Key takeaway:* the ingredients needed for realistic semiconductor device modeling.
5. **2D materials.** Set up a WSe2 monolayer device. *Key takeaway:* applying the NEGF-DFT workflow to two-dimensional channels.
6. **Photodetectors.** Compute the photocurrent in a WSe2 monolayer under illumination. *Key takeaway:* predicting optoelectronic response from first principles.
7. **Phonons and thermoelectric properties.** Run a frozen phonon calculation (7.1), then evaluate the thermoelectric properties of materials (7.2) and thermoelectric transport (7.3). *Key takeaway:* assessing energy-conversion performance end to end, from lattice vibrations to transport.

## Getting started on qBraid

1. **Launch the environment.** Open the pre-configured environment on the qBraid platform: [Launch on qBraid](https://account.qbraid.com/?gitHubUrl=https://github.com/nanoacademic/nano-qbraid.git). No installation is required.
2. **Start small.** Open a basic tutorial, such as a simple molecular device or the PtSe2 electronic-structure example, to become familiar with the two-probe setup and the input format.
3. **Run the transport calculation.** Compute the self-consistent NEGF-DFT solution, then evaluate the transmission spectrum and the current-voltage characteristics.
4. **Make it yours.** Use an example as a template, substitute your structure and electrodes, and extend the analysis to spin, gating, or thermoelectric properties as needed.

## Tips and troubleshooting

- **Lead setup:** make sure the lead (electrode) cell is a well-converged, periodic bulk calculation before assembling the two-probe device, since the leads define the boundary conditions.
- **Bias and integration:** for non-equilibrium runs, check the convergence of the current with respect to the energy and bias-window integration grids.
- **Self-consistency:** if a biased calculation is slow to converge, start from the converged zero-bias solution and ramp the voltage gradually.

## Documentation and resources

- Official NanoDCAL documentation: https://docs.nanoacademic.com/nanodcal/
- Full tutorial catalog: https://docs.nanoacademic.com/nanodcal/tutorials/
- Nanoacademic Technologies: https://nanoacademic.com/
