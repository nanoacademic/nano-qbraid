<img src="images/logos/nanoacademic_horizontal_slogan_cmjn.svg" alt="Nanoacademic Logo" style="max-width: 500px;">

**[Nanoacademic Technologies](https://www.nanoacademic.com/)** provides advanced simulation software that helps researchers and engineers model materials at the nanoscale with **[RESCU](#rescu)** 
and **[NanoDCAL](#nanodcal)**.

Built and continuously improved by our team of experts, our solutions combine high accuracy, strong performance, and an enhanced accessibility for users around the world. Whether you are exploring new materials, optimizing designs, or researching new technologies, Nanoacademic gives you the tools to move faster with confidence.

<img src="images/logos/nanodcal_cmjn.svg" alt="NanoDCAL Logo" width="150"><img src="images/logos/spacer.svg" alt="" width="50" height="1"><img src="images/logos/rescu4_cmjn.svg" alt="RESCU Logo" width="150">

On this cloud platform, you can also take advantage of **[LatticeMind](#latticemind)**, our agentic artifical intelligence DFT simulation assistant, to streamline and pre-validate your simulation workflow and access the CPU/GPU power of qBraid Labs to further speed up your computations.

<img src="images/logos/latticemind_logo_vectorized_smooth_transparent.svg" alt="RESCU Logo" style="max-width: 150px;">

*Soon available on qBraid Labs* → Our next-generation quantum design software for semiconductor spin qubits and superconducting circuits: **[QTCAD®](https://docs.nanoacademic.com/qtcad/)**

<img src="images/logos/qtcad_cmjn.svg" alt="QTCAD Logo" style="max-width: 150px;">

## Accessing the software

The three softwares ([LatticeMind](#latticemind), [RESCU](#rescu), and [NanoDCAL](#nanodcal)), come pre-installed and available in the terminal of in the Nanoacademic qBraid Lab environment. The following steps will show you how to access the lab and setup the licenses required to use our software.

Tutorials, examples and pseudo potentials are available in `$HOME/nanoacademic`. This folder is copied after the lab's creation from `/usr/local/share/nanoacademic`. If you accidentally alter or delete the `$HOME/nanoacademic` folder, you can always get a fresh copy from the source folder.

### 1. Launch the Lab

In [qBraid's dashboard](https://www.qbraid.com/), go to on-demand, then find and launch the Nanoacademic lab.

![qBraid dashboard](images/dashboard.png)


### 2. Bring Your Own License

**NanoDCAL** and **Rescu** require you to have a valid license file imported in the lab. To proceed, you need to :

1. Create an account at [portal.nanoacademic.com](https://portal.nanoacademic.com/).
2. Activate the license for the products you wish to use.
3. You can import your license either through :
    - A. [qBraid's Vault user interface in JupyterLab](#license-setup-in-qbraid-lab)
    - B. Using the `nano-cli` command line tool directly available in your qBraid lab's terminal.

#### License setup in qBraid Lab

1. Launch the Nanoacademic environment from qBraid Lab.
2. Open **Vault** from the profile menu.

![Open Vault](images/to-vault.png)

3. Connect your Nanoacademic account using your credentials.

![Connect Nanoacademic](images/vault1.png)

4. Add or import the required licenses for RESCU and NanoDCAL.

![Import licenses](images/license.png)

## RESCU

Large-Scale Density Functional Theory

<img src="images/logos/rescu4_cmjn.svg" alt="RESCU Logo" width="150">

> A real-space Density Functional Theory (DFT) solver built to reach the length scales where realistic materials physics actually happens, from a single molecule to tens of thousands of atoms.

Welcome to RESCU on qBraid. This page gives you a quick sense of what RESCU can do, walks you through the bundled examples, and gets you to your first calculation in a few clicks. The software and all example notebooks are pre-installed in the qBraid environment, so there is nothing to set up.

### Overview

RESCU (Real-space Electronic Structure CalcUlator) is a Kohn-Sham DFT package developed by Nanoacademic Technologies. It is engineered for one purpose above all: to compute the ground-state electronic structure of very large systems without forcing you to compromise on accuracy. Where conventional DFT codes become impractical at a few hundred atoms, RESCU is designed to stay productive well into the range of thousands to tens of thousands of atoms, which is the regime needed to model defects, interfaces, heterostructures, and nanoscale devices as they are built in the laboratory.

RESCU achieves this by combining three complementary representations of the electronic problem: a real-space grid, a basis of numerical atomic orbitals (NAO), and Chebyshev-filtered subspace iteration for systematic and memory-efficient convergence. This design keeps the most demanding operations local and highly parallel, which is what allows the method to scale.

### Why it matters

For many of the most interesting questions in materials science, size is not a detail, it is the physics. A point defect in a semiconductor, the moire pattern of a van der Waals stack, or the band alignment at a solid-liquid interface cannot be captured faithfully in a small unit cell. RESCU lets you keep the full atomistic detail of these systems while staying within reach of routine computing resources, so you can move from idealized models to structures that resemble real samples.

### Highlights

- **Levels of theory:** LDA, GGA (including PBE), and meta-GGA functionals, together with Hartree-Fock exchange and hybrid functionals. Additional functionals are available through the LibXC library.
- **Magnetism and relativity:** spin-degenerate, collinear, and non-collinear spin calculations, with spin-orbit coupling.
- **Pseudopotentials:** norm-conserving pseudopotentials, including Optimized Norm-Conserving Vanderbilt (ONCV) and Troullier-Martins constructions, with partial core corrections, supplied for LDA and GGA.
- **Basis and solvers:** real-space grid discretization and numerical atomic orbitals, accelerated by Chebyshev-filtered subspace iteration for large systems.
- **High-performance computing:** parallelized with MPI and OpenMP and built on optimized libraries (FFTW, ScaLAPACK). 

### What you can compute

| Category | Properties |
| --- | --- |
| Electronic structure | Total energy, ground-state density, band structure |
| Spectroscopy and analysis | Density of states (DOS), projected DOS (PDOS), local DOS (LDOS, PLDOS), Mulliken charges |
| Forces and geometry | Atomic forces, stress tensors, structural relaxation (steepest descent and conjugate gradient) |
| Vibrational properties | Frozen-phonon spectra, dynamical matrices, interatomic force constants |
| Optical and vibrational response | Dielectric permittivity, Raman spectra |

### Scalability at a glance

RESCU is built around favorable scaling rather than brute force. Using a real-space grid, it scales consistently as roughly O(N^2.3) from a few hundred atoms to more than 5,000 atoms, with comparable or better scaling in a numerical atomic orbital basis up to the 14,000-atom range. Representing wavefunctions as linear combinations of atomic orbitals significantly reduces the memory footprint, which is often the true bottleneck for large calculations.

### Hands-on examples

The qBraid environment ships with the full set of official RESCU tutorials as ready-to-run notebooks. The basic tutorials take you from convergence checks to your first analyses, while the advanced tutorials go further into electronic structure, defects, and doping. Each one is self-contained and annotated.

**Basic tutorials**

1. **Numerical convergence.** Check how the total energy and key quantities converge with the real-space grid, k-point sampling, and basis settings. *Key takeaway:* establishing converged, trustworthy parameters before any production run.
2. **Equation of state and geometry optimization.** Relax the structure, fit the equation of state to obtain the equilibrium lattice constant and bulk modulus, and compute band offsets across an interface. *Key takeaway:* obtaining the ground-state geometry, the mechanical response, and interface band alignment.
3. **Adsorption energy.** Compute the binding energy of an adsorbate on a surface. *Key takeaway:* quantifying surface-adsorbate interactions for catalysis and surface science.
4. **STM simulations (Tersoff-Hamann).** Generate scanning tunneling microscopy images using the Tersoff-Hamann approximation. *Key takeaway:* connecting the calculated electronic structure directly to STM experiments.

**Advanced tutorials**

Going further, the advanced set covers bulk silicon basics, graphene PDOS, the equation of states and chemical potential, the valence band maximum, the dielectric constant, the diamond vacancy defect, and phosphorus doping in silicon, including impurity-state analysis of the P-in-Si donor.

### Getting started on qBraid

1. **Launch the environment.** Open the pre-configured environment on the qBraid platform: [Launch on qBraid](https://account.qbraid.com/?gitHubUrl=https://github.com/nanoacademic/nano-qbraid.git). No installation is required.
2. **Open a notebook.** Start with the numerical convergence tutorial to confirm your setup and learn the input format.
3. **Run and visualize.** Execute the cells to compute the band structure and DOS, then use the built-in DOS, PDOS, LDOS, and band-structure tools to inspect the results.
4. **Make it yours.** Copy a notebook as a template, replace the structure, and adjust the functional, basis, and convergence settings to match your own system.

### Tips and troubleshooting

- **Convergence:** if the self-consistent loop struggles to converge, refine the real-space grid spacing and revisit the smearing and mixing parameters before changing anything else.
- **Memory on large systems:** prefer the numerical atomic orbital basis for the largest structures, since it reduces the memory footprint substantially.
- **Performance:** enable GPU acceleration where available, and scale the number of MPI processes to the size of the system.

### Documentation and resources

- Official RESCU documentation: https://docs.nanoacademic.com/rescu/
- Tutorial catalog: https://docs.nanoacademic.com/rescu/tutorials/basic_tutorials/basic_tutorials/
- Nanoacademic Technologies: https://nanoacademic.com/


## NanoDCAL

Quantum Transport from First Principles

<img src="images/logos/nanodcal_cmjn.svg" alt="NanoDCAL Logo" width="150">

> A quantum transport simulator that predicts how electrons flow through a device, from a single molecule between two electrodes to a sub-nanometer transistor, directly from first principles.

Welcome to NanoDCAL on qBraid. This page introduces what NanoDCAL computes, walks you through the bundled device examples, and gets you to your first transport calculation in a few clicks. The software and all example notebooks are pre-installed in the qBraid environment, so there is nothing to set up.

### Overview

NanoDCAL (Nanoacademic Device Calculator) is a quantum transport package developed by Nanoacademic Technologies. It is an atomic-orbital implementation of the NEGF-DFT method, which couples Density Functional Theory (DFT) with the Keldysh non-equilibrium Green's function (NEGF) formalism. This combination is what makes NanoDCAL a genuine device simulator rather than a bulk-structure tool: it computes current, conductance, and transmission for open systems under a finite bias, accounting for the non-equilibrium quantum statistics that govern a working device.

The workflow is conceptually simple. DFT determines the Hamiltonian of the nanostructure with full atomic detail, while NEGF supplies the non-equilibrium statistical occupation through the Keldysh formalism. The two are solved self-consistently, so the charge density, the electrostatic potential, and the transport properties are mutually consistent at every applied voltage.

### Why it matters

Predicting the electronic structure of a material is only half the story for nanoelectronics. The question that ultimately matters is how a device behaves when it is connected to electrodes and a voltage is applied. NanoDCAL answers that question directly, providing current-voltage characteristics and transmission spectra that can be compared against experiment and used to evaluate device concepts before they are fabricated. For molecular electronics, spintronics, and ultra-scaled transistors, this is the difference between a structural model and a performance prediction.

The same reach extends to superconducting quantum computing, where qubit performance is shaped by materials as much as by design. The Josephson junction at the core of a qubit is, structurally, a metal-insulator-metal device, the two-probe geometry NanoDCAL is built around. NanoDCAL brings first-principles, atomic-scale modeling to that junction, so you can study how the tunnel barrier and its interfaces, from oxidation and stoichiometry to disorder, shape the junction's transport, and weigh material choices before a single device is fabricated.

### Device types

NanoDCAL is organized around the geometry of the problem, from closed systems to multi-terminal devices:

| Configuration | Use case |
| --- | --- |
| 0-probe | Isolated molecules and periodic crystals via supercells |
| 1-probe | Surfaces with semi-infinite geometry |
| 2-probe | Open device structures with leads (the primary use case) |
| Multi-probe | Structures with several electrodes |

Leads can be one-, two-, or three-dimensional, and the package handles device structures of up to roughly 1,000 atoms.

### What you can compute

- **Transport:** transmission coefficients, conductance and resistance, and nonlinear, non-equilibrium current-voltage (I-V) characteristics.
- **Electronic structure:** total and local density of states, band structure, current density, and scattering states.
- **Spin:** spin-polarized transport, with collinear and non-collinear treatments and spin-orbit coupling.
- **Forces and vibrations:** atomic forces, structural optimization, and vibrational properties including electron-phonon coupling.
- **Beyond DC:** photocurrent, thermal and thermoelectric transport, gate fields included self-consistently for leads with finite cross-section, and external AC voltages applied on top of a DC bias (experimental).

### Hands-on examples

The qBraid environment ships with the full set of official NanoDCAL tutorials as ready-to-run notebooks, organized by topic. Each one is self-contained and annotated.

1. **Electronic structure.** Compute the fat-band structure of a PtSe2 monolayer. *Key takeaway:* extracting orbital-resolved band structure from a first-principles calculation.
2. **Molecular electronics.** Build simple molecular devices and explore their dynamic (AC) conductance. *Key takeaway:* the core two-probe workflow, from self-consistency to transmission and the current-voltage curve.
3. **Spin devices.** Study spin-resolved transport in a zigzag graphene nanoribbon, a nickel-graphene interface, and with DFT+U. *Key takeaway:* resolving transport by spin channel for spintronics applications.
4. **Semiconductor devices.** Account for spin-orbit interaction, carrier effective mass, and complex energy band structure. *Key takeaway:* the ingredients needed for realistic semiconductor device modeling.
5. **2D materials.** Set up a WSe2 monolayer device. *Key takeaway:* applying the NEGF-DFT workflow to two-dimensional channels.
6. **Photodetectors.** Compute the photocurrent in a WSe2 monolayer under illumination. *Key takeaway:* predicting optoelectronic response from first principles.
7. **Phonons and thermoelectric properties.** Run a frozen phonon calculation (7.1), then evaluate the thermoelectric properties of materials (7.2) and thermoelectric transport (7.3). *Key takeaway:* assessing energy-conversion performance end to end, from lattice vibrations to transport.

### Getting started on qBraid

1. **Launch the environment.** Open the pre-configured environment on the qBraid platform: [Launch on qBraid](https://account.qbraid.com/?gitHubUrl=https://github.com/nanoacademic/nano-qbraid.git). No installation is required.
2. **Start small.** Open a basic tutorial, such as a simple molecular device or the PtSe2 electronic-structure example, to become familiar with the two-probe setup and the input format.
3. **Run the transport calculation.** Compute the self-consistent NEGF-DFT solution, then evaluate the transmission spectrum and the current-voltage characteristics.
4. **Make it yours.** Use an example as a template, substitute your structure and electrodes, and extend the analysis to spin, gating, or thermoelectric properties as needed.

### Tips and troubleshooting

- **Lead setup:** make sure the lead (electrode) cell is a well-converged, periodic bulk calculation before assembling the two-probe device, since the leads define the boundary conditions.
- **Bias and integration:** for non-equilibrium runs, check the convergence of the current with respect to the energy and bias-window integration grids.
- **Self-consistency:** if a biased calculation is slow to converge, start from the converged zero-bias solution and ramp the voltage gradually.

### Documentation and resources

- Official NanoDCAL documentation: https://docs.nanoacademic.com/nanodcal/
- Full tutorial catalog: https://docs.nanoacademic.com/nanodcal/tutorials/
- Nanoacademic Technologies: https://nanoacademic.com/

## LatticeMind (TODO)

<img src="images/logos/latticemind_logo_vectorized_smooth_transparent.svg" alt="RESCU Logo" style="max-width: 150px;">

- [ ] Add Materials from Nate
- Add logo
- Open AI

LatticeMind brings an AI-assisted workflow to RESCU development. It is designed to help with code exploration, iteration, and task automation inside the lab environment.

![LatticeMind](images/latticemind.png)

For LatticeMind, add an OpenAI API key in Vault and set `OPENAI_API_KEY`.

![OpenAI API keys](images/api-keys.png)

![OpenAI token](images/openai-token.png)

## Documentation

- [qBraid Docs](https://docs.qbraid.com/)
- [Nanoacademic Docs](https://docs.nanoacademic.com/)
- [RESCU Docs](https://docs.nanoacademic.com/rescu/)
- [NanoDCAL Docs](https://docs.nanoacademic.com/nanodcal/)

## About Nanoacademic

Learn more about us on our website at [https://www.nanoacademic.com/](https://www.nanoacademic.com/)
