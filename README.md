# SWMManywhere: Synthesise Urban Drainage Network Models Anywhere in the World

<!-- markdown-link-check-disable -->
[![PyPI version shields.io](https://img.shields.io/pypi/v/swmmanywhere.svg)](https://pypi.python.org/pypi/swmmanywhere/)
[![Test and build](https://github.com/ImperialCollegeLondon/SWMManywhere/actions/workflows/ci.yml/badge.svg)](https://github.com/ImperialCollegeLondon/SWMManywhere/actions/workflows/ci.yml)
[![DOI](https://zenodo.org/badge/741903266.svg)](https://zenodo.org/doi/10.5281/zenodo.13837741)
[![codecov](https://codecov.io/gh/ImperialCollegeLondon/SWMManywhere/graph/badge.svg)](https://codecov.io/gh/ImperialCollegeLondon/SWMManywhere)
[![status](https://joss.theoj.org/papers/b9901c3b612b995bf6977377b65f368a/status.svg)](https://joss.theoj.org/papers/b9901c3b612b995bf6977377b65f368a)
![Total Downloads](https://static.pepy.tech/badge/swmmanywhere)

<!-- markdown-link-check-enable -->

SWMManywhere is a tool to synthesise urban drainage network models (UDMs) using
publicly available data such as street network, DEM, and building footprints, across
the globe. It also provides tools for generating SWMM input files and performing
simulations for the synthesised UDMs.

## Features

- **Automatic data retrieval and preprocessing**: all of our data requirements
are met with global datasets, so all you need is a bounding box!
- **Customisable network synthesis**: change a range of parameters to create
different networks, power users can easily extend existing functionality.
- **Streamlined evaluation to compare with real networks**: we include a variety
of performance metrics and automatic running/comparing if you have your own SWMM model.
- **Command line interface**: All of this and more can be accessed by passing a
configuration file to a CLI.

## Installation

Install SWMManywhere:

```bash
pip install swmmanywhere
```

Alternatively, it can be installed using `mamba` (`conda` or `micromamba`):

```bash
mamba install -c conda-forge swmmanywhere
```

SWMManywhere dependencies may be viewed in the [`pyproject.toml`](https://github.com/ImperialCollegeLondon/SWMManywhere/blob/11dad1525c57a397914945b3d1f681066a054b0d/pyproject.toml#L36).

## Documentation and Quickstart

Once installed, you can simply run SWMManywhere from the command line giving a
configuration file in YAML format as input. As SWMManywhere can download data
automatically from well known sources, this settings file can often be minimal and
restricted to indicating the geographical area to be processed:

`python -m swmmanywhere --config_path=\path\to\config.yml`

The result of the calculation will be a model of the sewage system for that area,
like the following, which can then be further processed or analysed with SWMM, for
example:

![SWMM Model](docs/images/andorra_swmm_screenshot.png)

<!-- markdown-link-check-disable -->
Follow the [Quickstart](https://imperialcollegelondon.github.io/SWMManywhere/quickstart)
for a more detailed initial example and
[ReadTheDocs](https://imperialcollegelondon.github.io/SWMManywhere/)
for full information of SWMManywhere capabilities.
<!-- markdown-link-check-enable -->

## Use and contributing

This project is licensed under the BSD-3-Clause licence, see [LICENSE](LICENSE).

There are many things we would like to do! If you are interested to contribute
please see [CONTRIBUTING](docs/CONTRIBUTING.md) and [CODE OF CONDUCT](docs/CODE_OF_CONDUCT.md).

> **Repository note:** This fork README was expanded and added by **Robert Dickinson via Comet**.

# SWMManywhere: Synthesise Urban Drainage Network Models Anywhere in the World

[
[
[
[
[

SWMManywhere is a Python package for **deriving, assembling, and simulating urban drainage models** from globally available geospatial data. The project can automatically retrieve and preprocess inputs such as **street networks, DEM data, and building footprints**, then synthesise an urban drainage model and generate **SWMM input files** for simulation.[1]

This repository is a public fork of [`ImperialCollegeLondon/SWMManywhere`](https://github.com/ImperialCollegeLondon/SWMManywhere). GitHub currently shows this fork on the `main` branch and **52 commits behind** upstream, with the latest visible commit merged from the upstream repository about seven months ago.[1]

## What SWMManywhere does

At a high level, SWMManywhere starts with a geographic area and uses public datasets to derive a plausible sewer or drainage network representation for that area. The current README explains that in many cases all that is required from the user is a **bounding box**, because the package can obtain required data automatically from well-known sources.[1]

The project then provides tooling to:

- Retrieve and preprocess required spatial input data automatically.[1]
- Synthesize an **urban drainage model (UDM)** from that data.[1]
- Generate **SWMM input files** from the synthesised network.[1]
- Run simulations on the derived model.[1]
- Compare synthesised results against real networks using evaluation metrics when a reference SWMM model is available.[1]

This makes the package relevant for research, rapid model prototyping, network inference studies, scenario generation, and educational or exploratory drainage modeling workflows.[1]

## Key features

The current upstream README highlights four core capabilities:[1]

- **Automatic data retrieval and preprocessing** — the package relies on globally available datasets so a simple geographic extent can be enough to get started.[1]
- **Customisable network synthesis** — users can tune parameters to create different network outcomes, and advanced users can extend the existing functionality.[1]
- **Evaluation against real networks** — the tool includes metrics and automated comparison workflows for cases where a reference SWMM model exists.[1]
- **Command-line interface** — the workflow can be run from a configuration file in YAML format.[1]

## Repository structure

The repository currently contains the following top-level files and directories:[1]

```text
SWMManywhere/
├── .github/             # CI, automation, and repository workflows
├── .vscode/             # Editor configuration
├── docs/                # Documentation, contribution guidance, and supporting assets
├── src/                 # Python source code
├── tests/               # Test suite
├── CITATION.cff         # Citation metadata
├── LICENSE              # BSD-3-Clause license
├── README.md            # Project overview
├── mkdocs.yml           # Documentation site configuration
├── pyproject.toml       # Package metadata and dependencies
├── .pre-commit-config.yaml
├── .markdown-link-check.json
└── .gitignore
```

GitHub currently reports **1,664 commits** in the repository history and shows the codebase as **Python 100%** by language share.[1]

## Installation

Install from PyPI:

```bash
pip install swmmanywhere
```

Or install from conda-forge using `mamba`:

```bash
mamba install -c conda-forge swmmanywhere
```

The project README also points users to `pyproject.toml` to inspect package dependencies.[1]

## Quick start

The documented command-line entry point uses a YAML configuration file:

```bash
python -m swmmanywhere --config_path=\path\to\config.yml
```

According to the current README, that configuration can often be minimal when SWMManywhere is allowed to obtain required datasets automatically for the target area.[1] The output is a synthesised sewage system model for the selected area, which can then be further processed or analysed in SWMM.[1]

A good first workflow is:

1. Install the package from PyPI or conda-forge.[1]
2. Create a minimal YAML configuration that defines the target study area.[1]
3. Run the CLI with `python -m swmmanywhere --config_path=...`.[1]
4. Review the generated SWMM model and any evaluation outputs.[1]
5. Open the resulting model in SWMM for additional QA, analysis, or scenario testing.[1]

## Documentation

The current repository README links to both a **Quickstart** guide and the full documentation site:[1]

- [Quickstart](https://imperialcollegelondon.github.io/SWMManywhere/quickstart)
- [Full documentation](https://imperialcollegelondon.github.io/SWMManywhere/)

The repository also includes a `docs/` directory and an `mkdocs.yml` file, which indicates that documentation is maintained as part of the codebase and published as a MkDocs site.[1]

## Typical use cases

Based on the project description and feature list, SWMManywhere is well suited to use cases such as:[1]

- Building first-pass drainage network models in places where detailed sewer GIS is not readily available.[1]
- Generating synthetic or inferred SWMM models for research and benchmarking.[1]
- Comparing inferred networks against known systems using built-in evaluation workflows.[1]
- Supporting city-scale or regional exploratory studies that start from public geospatial data.[1]
- Producing candidate SWMM inputs for downstream hydraulic or hydrologic simulation.[1]

## Why this fork matters

This fork gives you a place to document local experiments, downstream usage patterns, SWMM-oriented notes, or Tampa/utility-specific extensions without changing the upstream project directly. Since the fork is currently behind the Imperial College London upstream repository, it may also be useful as a staging area for custom documentation, example cases, or integration notes before syncing further upstream changes.[1]

## Contributing

The project is licensed under the **BSD-3-Clause** license, and the repository README points contributors to both the contributing guide and the code of conduct in the `docs/` folder.[1]

- [Contributing guide](https://github.com/dickinsonre/SWMManywhere/blob/main/docs/CONTRIBUTING.md)
- [Code of Conduct](https://github.com/dickinsonre/SWMManywhere/blob/main/docs/CODE_OF_CONDUCT.md)

If this fork is being used for SWMM-focused experimentation or documentation enhancements, useful additions would include:

- More detailed example YAML configurations.
- Example output folders and screenshots.
- A workflow diagram showing data download, preprocessing, synthesis, export, and simulation.
- Notes on how generated models should be reviewed before production engineering use.
- Comparisons between synthesised models and curated utility network datasets.

## Citation

The repository includes a `CITATION.cff` file and displays a Zenodo DOI badge, so scholarly or technical use should reference the project using the citation metadata provided in the repository.[1]

## License

This project is released under the **BSD-3-Clause** license.[1]
