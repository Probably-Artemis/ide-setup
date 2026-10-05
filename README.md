# IDE setup for beginners and students

## Terms

Items will be added here as they are mentioned and as definition becomes necessary.
1. IDE - Integrated Development Environment
    1. An IDE is software which provides a relatively comprehensive set of features for software development.
2. Venv - Virtual Environment
    1. A venv is an isolated environment for Python projects, designed to keep dependencies manageable.

## Intro

This repository is for those who are just getting into python development and either do not have an IDE set up or do not have one set up well.

## Base requirements (Python and Git)

### Python

This guide presumes you have Python installed, at least version 3.13. You should keep your installed version of Python up to date unless it breaks installed libraries and packages. As of time of writing, the most recent version of Python is version 3.14, although 3.15 should be releasing in only a few days.

To install python, visit the [official download page](https://www.python.org/downloads/), which should automatically detect your operating system and offer you the specific file you need to download.

For Windows and Mac, no critical system software requires a specific Python version be installed. Linux, however, comes with Python preinstalled, and will likely break if you install a different version without being careful. 

Make certain to look up any requirements or catches for installing Python to your specific system.

### Git

Installation process varies by operating system.

For Windows, download and run the installer from [git-scm.com](https://git-scm.com/install/windows).

For Mac, install via homebrew or MacPorts. The latest instructions can always be found on the [installation page](https://git-scm.com/install/mac).

For Linux, the process of installation will depend on your chosen Linux distribution. The install commands can be found at the Linux section of the [installation page](https://git-scm.com/install/linux).

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

Download this repository to the location you'll be doing your work. You may do this either by downloading [the .zip](https://github.com/Probably-Artemis/ide-setup/archive/refs/heads/main.zip) and decompressing it as you would any compressed archive, or by cloning it. To clone:
```bash
git clone https://github.com/Probably-Artemis/ide-setup.git
```
Once you have the files, open the workspace in VS Code. You may do this from a new VS Code window by navigating to *File > Open Folder*, then selecting your newly downloaded files.

When you first open the workspace, VS Code will ask you if you trust the authors. Select yes, so settings and extensions can be downloaded. You should then receive a popup offering to install all suggested extensions. Accept the prompt.

The way this repository is configured, my changes will only apply to this current workspace, not other workspaces you create. To get these features in a new workspace, simply repeat the download step above.

## Venv

### VS Code route

Install VSCode and its Python extension. Open your project's folder in VSCode. **Not just a single .py file, the entire folder.**

Press `Ctrl+Shift+P` to open the Command Palette, type in and run `Python: Create Environment`, choose `Venv`, and select your installed Python instance.

New terminals in VSCode should open in the venv, indicated by `(.venv)` being shown in the prompt. Preexisting terminals won't be in the venv, so close and reopen them.

### Manual (terminal) route

Open your project folder in a terminal. Consult the table below for the commands to run for your given operating system.

| | Windows | Mac / Linux |
|---|---|---|
|Create|`py -m venv .venv`|`python3 -m venv .venv`|
|Activate|`.venv\Scripts\activate`|`source .venv/bin/activate`|

To create your venv, use the Create command for your specific operating system.

Each time you open a terminal to run your code, you must activate your venv, using the Activate command for your specific operating system.

#### A note for Windows users:

Sometimes, activating your venv may fail, as PowerShell will tell you "running scripts is disabled on this system". To fix this, run the following command to enable running scripts.
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

# Contributing

Please see [CONTRIBUTING.md](https://github.com/Probably-Artemis/ide-setup/blob/main/CONTRIBUTING.md) for the full guidelines to contribution.

Any parts of my instructions which were unclear, unspecific, or otherwise not beginner friendly warrants the opening of an issue.