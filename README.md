# Fast Python-based Dev Containers with PDM

This is a template repository that can be used to start with a minimal [Python3 Dev Container](https://github.com/devcontainers/images/tree/main/src/python) setup that provides [pipx](https://pypa.github.io/pipx/) and  [PDM](https://pdm.fming.dev/) for setting up Python environments.

This repo contains a sample file ([pyproject.toml](pyproject.toml)) managing AI Python project dependencies, such as DVC and nbdev, with optional support for spdx-tools and huggingface_hub. It also contains a demo Jupyter notebook, and Dev Container configuration files that describe how a containerized development can be built for the repo.
These configuration files work for both local Dev Containers as well as [Codespaces](https://github.com/features/codespaces), a GitHub-hosted cloud environment.

The Docker setup for the Dev Container starts with a Python image that then will install PDM as a pipx tool for managing python packages. PDM will create a virtual environment and install the required packages in the file `pyproject.toml`.

There are some additional configuration options in the comments of the [Docker](.devcontainer/Dockerfile) and [devcontainer.json](.devcontainer/devcontainer.json) that have some examples of other steps you may want to add to your Dev Container, like what VS Code extensions to install when the container is launched.

## Prerequisites for work on your computer

- VS Code with DevContainer extension installed
- Docker

## How to use this template

0. Create a repo of your own by [creating a repo from this template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) to your GitHub account.

1. Start the DevContainer on your computer (requires Docker and VS Code installed)
    - Clone the repo to your computer and open it in VS Code.
    - In VS Code press `Ctrl + Shift + P` to bring up the Command Palette.
    - Enter and find `Dev Containers: Reopen in Container`.
    - VS Code will starts to download the [Python3 Dev Container](https://github.com/microsoft/vscode-dev-containers/tree/main/containers/python-3) image, install PDM that will create a virtual environment and install everything.

2. Start working with the repo in the DevContainer
    - When you open any notebook the kernel will automatically detected. If it doesn't detect it, you can choose the `Recommended python environment`. You can open the demo notebook `demo.ipynb` and execute it to see that everything works.
    - If you open a new terminal inside VS Code, the virtual environment created should be activated. If it is not activated you can activate it with the command `source .venv/bin/activate`.

## Ways to customize the template

- Change the container `name` in [devcontainer.json](.devcontainer/devcontainer.json).
- TODO: Add more customization options.

## Tools Included in the Template

This template includes a variety of tools that support the development of Trusted AI systems. Trusted AI refers to AI systems that are transparent, explainable, fair, and robust. Here's an overview of the major tools included and how they contribute to Trusted AI:

### Quarto

[Quarto](https://quarto.org/) is a powerful tool for creating computational documents using a variety of languages such as Python, R, and Julia. Quarto documents provide a transparent way of sharing your data analysis, which includes code, explanatory text, and visualizations, fostering trust in your AI workflows.

### NBdev

[NBdev](https://nbdev.fast.ai/) is a library that allows you to develop a library in Jupyter Notebooks, putting all your code, tests, and documentation in one place. By making it easy to keep your code and documentation together, NBdev promotes transparency and reproducibility, key aspects of Trusted AI. NBdev is specifically configured to use Quarto in this template.

### DVC

[Data Version Control (DVC)](https://dvc.org/) is a version control system for machine learning projects. By tracking changes in your data and models, DVC makes your experiments reproducible, which is a fundamental part of creating AI systems that can be trusted.

### Hugging Face Hub (Optional)

[Hugging Face Hub](https://huggingface.co/) is a platform for sharing and collaborating on transformers models. A key feature of the Hugging Face Hub is the support for Model and Dataset cards, which are markdown files that accompany datasets and models and provide a description of their content, use-cases, creation/annotation process, biases, limitations and ethical considerations. These cards promote transparency and understanding, making it easier for users to find the right models and datasets for their needs and use them responsibly. Thus, the hub contributes to the development of Trusted AI by enhancing transparency, reproducibility, and responsible use of AI models and data.

### SPDX SBoM (Optional)

[Software Package Data Exchange (SPDX)](https://spdx.dev/) is a standard for communicating the components, licenses, and copyrights associated with a software package. By providing a clear list of components and their licenses, SPDX contributes to transparency and accountability in AI systems. This template includes support for SPDX version 3, which includes new support for AI.

These tools are designed to be used together to build Trusted AI systems. However, you can modify them to suit your needs. Instructions for how to use these tools are included in the respective sections of this README.

