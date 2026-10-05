# IDE setup for beginners and students

## Terms

Items will be added here as they are mentioned and as definition becomes necessary.
1. IDE - Integrated Development Environment
    1. An IDE is software which provides a relatively comprehensive set of features for software development.

## Intro

This repository is for those who are just getting into python development and either do not have an IDE set up or do not have one set up well.

## Base requirements (Python)

This guide presumes you have Python installed, at least version 3.13. You should keep your installed version of Python up to date unless it breaks installed libraries and packages. As of time of writing, the most recent version of Python is version 3.14, although 3.15 should be releasing in only a few weeks.

To install python, visit the [official download page](https://www.python.org/downloads/), which should automatically detect your operating system and offer you the specific file you need to download.

For Windows and Mac, no critical system software requires a specific Python version be installed. Linux, however, comes with Python preinstalled, and will likely break if you install a different version without being careful. 

Make certain to look up any requirements or catches for installing Python to your specific system.

## Installing VS Code

To download VS Code, visit the [downloads](https://code.visualstudio.com/download) page. Select the download button for your specific operating system.

For Windows, you will end up with a `.exe` installation wizard. Run it, and follow the prompts.

For Mac, you will end up with a `.dmg` installer.

If you are on Linux, there are of course files you may use to install VS Code, but your distribution may provide other, potentially more easy, ways to install. For example, below is an installation command for Debian.
```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft.gpg
echo "deb [signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list

sudo apt update
sudo apt install code
```

## Setting up VS Code (manual)

Files to handle this setup automatically are in the works, but they are not yet ready.

To start, you will want to make sure you have at the bare minimum the following extensions installed and enabled.

1. Python
2. Python Debugger
3. Python Environments
4. Pylance
5. Error Lens

I personally recommend the following additional extensions.

1. Ruff
2. Ruff Rule Explainer
3. GitHub Repositories
4. [Git & GitHub Extension Pack](https://marketplace.visualstudio.com/items?itemName=vinirossa.vscode-gitandgithub-pack)
5. indent-rainbow
6. Python Indent

## Setting up VS Code (less manual)

COMING SOON

# Contributing

Please see [CONTRIBUTING.md](https://github.com/Probably-Artemis/ide-setup/blob/main/CONTRIBUTING.md) for the full guidelines to contribution.

Any parts of my instructions which were unclear, unspecific, or otherwise not beginner friendly warrants the opening of an issue.