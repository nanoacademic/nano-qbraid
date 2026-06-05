# Nanoacademic Atomistic Software in the Cloud

Run Nanoacademic workflows inside qBraid Lab with a preconfigured environment for atomistic simulation, licensing, and AI-assisted development.

## What’s Included

- **RESCU**: atomistic simulation tools for scientific computing
- **NanoDCAL**: electronic transport and nano-scale device simulation
- **LatticeMind**: an AI coding agent for RESCU workflows

## Access the Lab

The software is preinstalled in the qBraid on-demand labs dashboard.

![qBraid dashboard](images/dashboard.png)

### Bring Your Own License

Before logging into Vault inside qBraid Lab, complete your Nanoacademic account setup:

1. Create an account at [portal.nanoacademic.com](https://portal.nanoacademic.com/).
2. Activate the license for the products you need.

You can import your license either through the Vault user interface in JupyterLab or from the JupyterLab terminal with `nano-cli`.

### License setup in qBraid Lab

1. Launch the Nanoacademic environment from qBraid Lab.
2. Open **Vault** from the profile menu.

![Open Vault](images/to-vault.png)

3. Connect your Nanoacademic account.

![Connect Nanoacademic](images/vault1.png)

4. Add or import the required licenses for RESCU and NanoDCAL.

![Import licenses](images/license.png)

## LatticeMind

LatticeMind brings an AI-assisted workflow to RESCU development. It is designed to help with code exploration, iteration, and task automation inside the lab environment.

![LatticeMind](images/latticemind.png)

For LatticeMind, add an OpenAI API key in Vault and set `OPENAI_API_KEY`.

![OpenAI API keys](images/api-keys.png)

![OpenAI token](images/openai-token.png)

## NanoDCAL

NanoDCAL is available in the same workspace for nanoelectronics and transport simulations, with the runtime and licensing flow already prepared for qBraid Lab.

## Documentation

- [qBraid Docs](https://docs.qbraid.com/)
- [Nanoacademic Docs](https://docs.nanoacademic.com/)
- [RESCU Docs](https://docs.nanoacademic.com/rescu/)
- [NanoDCAL Docs](https://docs.nanoacademic.com/nanodcal/)

## About Nanoacademic

- [Nanoacademic](https://www.nanoacademic.com/)
