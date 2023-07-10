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
