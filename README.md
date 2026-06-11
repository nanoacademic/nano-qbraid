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

<img src="images/logos/rescu4_cmjn.svg" alt="RESCU Logo" width="150">

- Include aldi's materials
- Include tutorials
- The pseuso potentials are at

RESCU is available for large-scale density functional theory simulations, with examples and licensing prepared in the qBraid Lab environment.

## NanoDCAL

<img src="images/logos/nanodcal_cmjn.svg" alt="NanoDCAL Logo" width="150">

- Include aldi's materials
- Include tutorials
- The pseuso potentials are at

NanoDCAL is available in the same workspace for nanoelectronics and transport simulations, with the runtime and licensing flow already prepared for qBraid Lab.

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
