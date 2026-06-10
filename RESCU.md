# RESCU: Large-Scale Density Functional Theory

> A real-space Density Functional Theory (DFT) solver built to reach the length scales where realistic materials physics actually happens, from a single molecule to tens of thousands of atoms.

Welcome to RESCU on qBraid. This page gives you a quick sense of what RESCU can do, walks you through the bundled examples, and gets you to your first calculation in a few clicks. The software and all example notebooks are pre-installed in the qBraid environment, so there is nothing to set up.

## Overview

RESCU (Real-space Electronic Structure CalcUlator) is a Kohn-Sham DFT package developed by Nanoacademic Technologies. It is engineered for one purpose above all: to compute the ground-state electronic structure of very large systems without forcing you to compromise on accuracy. Where conventional DFT codes become impractical at a few hundred atoms, RESCU is designed to stay productive well into the range of thousands to tens of thousands of atoms, which is the regime needed to model defects, interfaces, heterostructures, and nanoscale devices as they are built in the laboratory.

RESCU achieves this by combining three complementary representations of the electronic problem: a real-space grid, a basis of numerical atomic orbitals (NAO), and Chebyshev-filtered subspace iteration for systematic and memory-efficient convergence. This design keeps the most demanding operations local and highly parallel, which is what allows the method to scale.

## Why it matters

For many of the most interesting questions in materials science, size is not a detail, it is the physics. A point defect in a semiconductor, the moire pattern of a van der Waals stack, or the band alignment at a solid-liquid interface cannot be captured faithfully in a small unit cell. RESCU lets you keep the full atomistic detail of these systems while staying within reach of routine computing resources, so you can move from idealized models to structures that resemble real samples.

## Highlights

- **Levels of theory:** LDA, GGA (including PBE), and meta-GGA functionals, together with Hartree-Fock exchange and hybrid functionals. Additional functionals are available through the LibXC library.
- **Magnetism and relativity:** spin-degenerate, collinear, and non-collinear spin calculations, with spin-orbit coupling.
- **Pseudopotentials:** norm-conserving pseudopotentials, including Optimized Norm-Conserving Vanderbilt (ONCV) and Troullier-Martins constructions, with partial core corrections, supplied for LDA and GGA.
- **Basis and solvers:** real-space grid discretization and numerical atomic orbitals, accelerated by Chebyshev-filtered subspace iteration for large systems.
- **High-performance computing:** parallelized with MPI and OpenMP and built on optimized libraries (FFTW, ScaLAPACK). The most demanding linear-algebra steps of the self-consistent solver can be offloaded to NVIDIA GPUs via CUDA (CUBLAS and cuSPARSE), which is especially effective for large real-space calculations.

## What you can compute

| Category | Properties |
| --- | --- |
| Electronic structure | Total energy, ground-state density, band structure |
| Spectroscopy and analysis | Density of states (DOS), projected DOS (PDOS), local DOS (LDOS, PLDOS), Mulliken charges |
| Forces and geometry | Atomic forces, stress tensors, structural relaxation (steepest descent and conjugate gradient) |
| Vibrational properties | Frozen-phonon spectra, dynamical matrices, interatomic force constants |
| Optical and vibrational response | Dielectric permittivity, Raman spectra |

## Scalability at a glance

RESCU is built around favorable scaling rather than brute force. Using a real-space grid, it scales consistently as roughly O(N^2.3) from a few hundred atoms to more than 5,000 atoms, with comparable or better scaling in a numerical atomic orbital basis up to the 14,000-atom range. Representing wavefunctions as linear combinations of atomic orbitals significantly reduces the memory footprint, which is often the true bottleneck for large calculations.

## Hands-on examples

The qBraid environment ships with the full set of official RESCU tutorials as ready-to-run notebooks. The basic tutorials take you from convergence checks to your first analyses, while the advanced tutorials go further into electronic structure, defects, and doping. Each one is self-contained and annotated.

**Basic tutorials**

1. **Numerical convergence.** Check how the total energy and key quantities converge with the real-space grid, k-point sampling, and basis settings. *Key takeaway:* establishing converged, trustworthy parameters before any production run.
2. **Equation of state and geometry optimization.** Relax the structure, fit the equation of state to obtain the equilibrium lattice constant and bulk modulus, and compute band offsets across an interface. *Key takeaway:* obtaining the ground-state geometry, the mechanical response, and interface band alignment.
3. **Adsorption energy.** Compute the binding energy of an adsorbate on a surface. *Key takeaway:* quantifying surface-adsorbate interactions for catalysis and surface science.
4. **STM simulations (Tersoff-Hamann).** Generate scanning tunneling microscopy images using the Tersoff-Hamann approximation. *Key takeaway:* connecting the calculated electronic structure directly to STM experiments.

**Advanced tutorials**

Going further, the advanced set covers bulk silicon basics, graphene PDOS, the equation of states and chemical potential, the valence band maximum, the dielectric constant, the diamond vacancy defect, and phosphorus doping in silicon, including impurity-state analysis of the P-in-Si donor.

## Getting started on qBraid

1. **Launch the environment.** Open the pre-configured environment on the qBraid platform: [Launch on qBraid](https://account.qbraid.com/?gitHubUrl=https://github.com/nanoacademic/nano-qbraid.git). No installation is required.
2. **Open a notebook.** Start with the numerical convergence tutorial to confirm your setup and learn the input format.
3. **Run and visualize.** Execute the cells to compute the band structure and DOS, then use the built-in DOS, PDOS, LDOS, and band-structure tools to inspect the results.
4. **Make it yours.** Copy a notebook as a template, replace the structure, and adjust the functional, basis, and convergence settings to match your own system.

## Tips and troubleshooting

- **Convergence:** if the self-consistent loop struggles to converge, refine the real-space grid spacing and revisit the smearing and mixing parameters before changing anything else.
- **Memory on large systems:** prefer the numerical atomic orbital basis for the largest structures, since it reduces the memory footprint substantially.
- **Performance:** enable GPU acceleration where available, and scale the number of MPI processes to the size of the system.

## Documentation and resources

- Official RESCU documentation: https://docs.nanoacademic.com/rescu/
- Tutorial catalog: https://docs.nanoacademic.com/rescu/tutorials/basic_tutorials/basic_tutorials/
- Nanoacademic Technologies: https://nanoacademic.com/
