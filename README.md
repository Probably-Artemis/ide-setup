# IDE setup for beginners and students

## Terms

Items will be added here as they are mentioned and as definition becomes necessary.
1. IDE - Integrated Development Environment
    1. An IDE is software which provides a relatively comprehensive set of features for software development.
2. Venv - Virtual Environment
    1. A venv is an isolated environment for Python projects, designed to keep dependencies manageable.
3. Terminal
    1. A terminal is a device or software program used for interfacing with a computer over text.
4. CLI - Command Line Interface
    1. A CLI is a program interacted with by typing text commands into a terminal.
5. Git and GitHub
    1. Git & GitHub are not the same thing. Be careful not to confuse them.
    2. Git is a Source Control tool. It tracks the changes to your files.
    3. Git<u>**Hub**</u> is a website that stores Git projects online.
6. Command Palette
    1. The Command Palette is where all Commands are found.<sup>[[VS Code](https://code.visualstudio.com/api/ux-guidelines/command-palette)]</sup>
        1. To open VS Code's Command Palette, use the keyboard shortcut `Ctrl+Shift+P`, or `Cmd+Shift+P` on Mac. Alternatively, one may open the Command Palette from the View section of the top bar of VS Code.
    2. A Command Palette is a bar one may open in certain softwares which can be used to activate certain commands, change some settings, and activate predefined sets of instructions provided by the software.
7. Git terminology
    1. [W3Schools](https://www.w3schools.com/git/) has an in-depth guide on controlling Git from the command line. This guide also serves as a good guide to different terms.
    1. Repository
        1. A repository is a place which stores the complete history of your files and their changes.
        2. A remote repository is any repository not on your device, for example stored in GitHub.
        3. A local repository is the repository you have locally on your device for a given project.
    2. Clone
        1. To clone a repository is to download a repository you do not have locally, so that you may edit it.
    3. Changes, and staging them
        1. In Git, changes are decently self-explanatory, they are differences in files between the most recent commit that touched those files, and the current files.
        2. Staging a change or set of changes marks those changes to be committed on the next commit. You can stage all of your changes at once, or if you wish to be organized, you may stage only some changes at once, so they get different commits.
        3. "Upstream changes" refers to changes which exist on the remote repository but not on your local one.
    4. Commit
        1. To commit is to take all staged changes and associate them with a note of what you changed called a "commit message". You have to type your commit message yourself, and it should be detailed enough that you'll be able to tell what you did when looking back.
        2. Commit message best practices (from [W3Schools](https://www.w3schools.com/git/git_commit.asp?remote=github#:~:text=Commit%20Message%20Best%20Practices))
            1. Keep the first line of commit messages short, 50 characters or less.
            2. Use the imperative mood ("add feature" instead of "added feature")
            3. Leave a blank line after the first line, then explain in more detail on the third line if necessary.
            4. Describe why the change was made, not just what changed.
    5. Push
        1. To push is to "push" commits you have made locally to the remote repository.
    6. Pull
        1. To pull is to "pull" changes present on the remote branch that you do not have locally. You will usually have to pull any upstream changes before being able to push any of your own.
    7. Branch
        1. In Git, a branch is a separate version of your repository, sometimes likened to an alternate universe. Changes made in a branch do not affect the main branch, meaning you can safely test and iterate without risking breaking anything.
        2. Switching your active branch is called "checking out" the chosen branch.
    8. Merging
        1. To merge two branches is to combine their changes back into one branch.
        2. If different branches change the same line of a file, something called a "merge conflict" will occur, and you will have to resolve it by picking one branch's changes, both branches' changes, or attempt to combine them.
    9. Pull Request
        1. A Pull Request (or PR) is a request made by anybody who can view the repository to merge a branch they have provided with your main branch, this is how contributions are made to code on GitHub.
        2. GitHub has a wonderful UI for handling PRs, it makes merging them very easy. If you are worried to merge two branches on your own, make your own pull request and let GitHub help you.

## Intro

This repository is for those who are just getting into Python development and either do not have an IDE set up or do not have one set up well.

## Base requirements (Python, Homebrew, and Git)

### Python

This guide presumes you have Python installed, at least version 3.13. You should keep your installed version of Python up to date unless it breaks installed libraries and packages.

To install Python, visit the [official download page](https://www.python.org/downloads/), which should automatically detect your operating system and offer you the specific file you need to download.

If you are using Linux, you'll need to use your package manager to install Python.

For Windows and Mac, no critical system software requires a specific Python version be installed. Linux, however, comes with Python preinstalled, and will likely break if you replace it instead of installing alongside. 

On Windows, make sure to check the checkbox in the installer which reads "Add python.exe to PATH".

Make certain to look up any requirements or catches for installing Python to your specific system.

### Homebrew (Mac only)

If you're using a Mac, you'll need Homebrew installed for a few steps.

To install, simply run the following command in your terminal, sourced from [brew.sh](https://brew.sh/).
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
On Apple Silicon Macs, the installer script will provide you a couple commands which add `brew` to your PATH. Be certain to run them.

### Git

Installation process varies by operating system.

For Windows, download and run the installer from [git-scm.com](https://git-scm.com/install/windows). You are likely to be given a significant amount of options to choose from. The defaults will suffice, although if prompted I would recommend setting VS Code as Git's default editor.

For Mac, install via Homebrew or MacPorts. The latest instructions can always be found on the [installation page](https://git-scm.com/install/mac).

For Linux, the process of installation will depend on your chosen Linux distribution. The install commands can be found at the Linux section of the [installation page](https://git-scm.com/install/linux).

The first time you use git, you'll need to set your name and email. These variables will be listed in any commits you author, so use a username if you don't want your real name floating around. GitHub offers a private email so your real email stays hidden. You can access it by enabling "Keep my email addresses private" in [GitHub's email settings](https://github.com/settings/emails). Copy the email GitHub gives you, and enter it as your email below. If you don't have a GitHub account yet, see [Linking Git and GitHub](#step-0-a-github-account).
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
Replace `"Your Name"` and `"you@example.com"` with your own name/username and email.

## Installing VS Code

To download VS Code, visit the [downloads](https://code.visualstudio.com/download) page. Select the download button for your specific operating system.

For Windows, you will end up with a `.exe` installation wizard. Run it, and follow the prompts.

For Mac, you will end up with a `.dmg` installer. Open it, drag the contained VS Code item into your Applications folder.

If you are on Linux, there are of course files you may use to install VS Code, but your distribution may provide other, potentially easier, ways to install. For example, below is an installation command for Debian.
```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft.gpg
echo "deb [signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list

sudo apt update
sudo apt install code
```

## Setting up VS Code (manual)

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
4. indent-rainbow
5. Python Indent

If you can take the below less manual route, I strongly advise doing so, as it contains a more complete set of extensions.

## Setting up VS Code (less manual)

Download this repository to the location you'll be doing your work. You may do this either by downloading [the .zip](https://github.com/Probably-Artemis/ide-setup/archive/refs/heads/main.zip) and decompressing it as you would any compressed archive, or by cloning it. To clone:
```bash
git clone https://github.com/Probably-Artemis/ide-setup.git
```
Once you have the files, open the workspace in VS Code. You may do this from a new VS Code window by navigating to *File > Open Folder*, then selecting your newly downloaded files.

When you first open the workspace, VS Code will ask you if you trust the authors. Select "Trust", so settings can take effect. You should then receive a popup offering to install all suggested extensions. Accept the prompt.

If you accidentally close the prompt, you may search `@recommended` in the Extensions search bar to find the list again.

The way this repository is configured, my changes will only apply to this current workspace, not other workspaces you create. To get these features in a new workspace, simply copy the `.vscode` folder and `.gitignore` file to the new location. 

Files and folders beginning with `.` are hidden on Mac and Linux. Use `Cmd+Shift+.` in Finder on Mac to show hidden items, or `Ctrl+H` on most Linux file managers.

This setup comes with AI features disabled by default.

## Venv

### VS Code route

On Debian based Linux distros, you must run the following command before being able to create a venv.
```bash
sudo apt install python3-venv
```

Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac) to open the Command Palette, type in and run `Python: Create Environment`, choose `Venv`, and select your installed Python instance.

New terminals in VS Code should open in the venv, indicated by `(.venv)` being shown in the prompt. Preexisting terminals won't be in the venv, so close and reopen them.

If VS Code doesn't automatically pick up your new venv, run `Python: Select Interpreter` from the Command Palette to select it.

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
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## Linking Git and GitHub

GitHub refuses passwords for authenticating Git in the terminal, and has since 2021, so you must cache your credentials as shown below.

### Step 0: A GitHub account

Create an account at [github.com/signup](https://github.com/signup).

### VS Code

VS Code should prompt you to sign into GitHub the first time Git needs it. To manually initiate the process:
- Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P` on Mac)
- Run `Git: Clone`, then select Clone from GitHub
- VS Code should tell you the extension wants to sign in using GitHub, select allow.
- A sign-in form should open in your browser, sign in.
- The browser should ask to open VS Code, select allow again.
- If it worked, you should see a list of your GitHub repos (if you have any). Press `Esc` if you don't wish to clone anything.

### GitHub CLI

Windows users can usually skip this section, as Git comes with the Git Credential Manager, which should prompt you for a browser sign-in the first time an account is needed without having to install `gh`.

#### Install `gh`

On Windows, install via the following command:
```PowerShell
winget install --id GitHub.cli
```

On Mac, install via the following command:
```bash
brew install gh
```

On Linux, consult the [install page](https://cli.github.com/) for the installation method for your specific distribution. For example on Debian or Ubuntu, the docs provide the following command:
```bash
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

#### Run

Once `gh` is installed, run the following command:
```bash
gh auth login
```
You will be asked a set of questions. The prompts below may not be exact, but pick the closest answer.

- "Where do you use GitHub?" - GitHub.com
- "Preferred protocol for Git operations?" - HTTPS
- "Authenticate Git with your GitHub credentials?" - Y
- "How would you like to authenticate?" - Login with a web browser

You should then be shown a one time code, something like `ABCD-1234`. Copy it, and hit enter to open a browser window. Paste the code into the prompt, sign in, and press Authorize.

To make sure it worked, run:
```bash
gh auth status
```

## Testing / final setup

### Python

Create a file named `hello.py`, make it print hello world, and check if it runs.
```python
print("Hello World!")
```

### Git

If you downloaded this repo by cloning it instead of via .zip download, open your file manager and delete the hidden `.git` folder, or the below steps won't work.

Publish your workspace to github by navigating to the Source Control tab in the left sidebar of VS Code, or by pressing `Ctrl+Shift+G` (`Cmd+Shift+G` on Mac). You should see some text, and two buttons. One button will offer to let you "Initialize Repository". That will not link the repository to GitHub; it will offer you local only source control. The second button should read "Publish to GitHub".

When you press the Publish button, a menu should pop up in the Command Palette. You will be able to name the repository you wish to create, it will default to the name of the folder you are working in. 

Below the name field, there should be two buttons, reading "Publish to GitHub <u>private</u> repository" and "Publish to GitHub <u>public</u> repository" respectively. Public repositories can be viewed by anybody on the internet, and private repositories can only be viewed by you and any collaborators you add.

Once you select which repository type to create, the Command Palette will ask you what files to include in the repository. If you have a `.venv` folder, make sure *not* to include it. When you're ready, press the "OK" button. 

A `.gitignore` file (one is included in this repo) tells git to ignore specific files and folders, like the `.venv` folder.

Once VS Code has created your repo, the Source Control tab will switch to managing changes, commits, and pushes. You should get a notification to open your new repository in GitHub, click it to open the web view. If the notification does not show up, you can find your repository at `https://github.com/[GitHub username]/[repository name]`. For example, if I were to create a repository named `deleteme`, it would be at https://github.com/Probably-Artemis/deleteme.

## Using the Source Control tab

There are three sections of the Source Control tab, `Repositories`, `Changes`, and `Graph`. The exact buttons and their positions may change in future updates, this guide was written in October of 2026.

### Repositories

This section shows, in order from left to right, the repository name, the branch, the Synchronize Changes button, the Create Pull Request button, and the More actions button.

Clicking on the branch (will probably be named `main` by default) will give you options to create a new branch, or switch your current branch to a different local or remote branch.

Clicking the Synchronize Changes button will pull any upstream changes, then push all local commits you've made that haven't yet been pushed.

Clicking Create Pull Request will allow you to, as the name suggests, create a new PR right from VS Code.

### Changes

This section shows a field for writing your commit messages, a commit button, and a display of all changes, staged and unstaged.

You cannot commit without first writing a commit message. Once you are done typing it, you can press `Ctrl+Enter` (or `Cmd+Enter` on Mac) to automatically commit all currently staged changes with your written message.

When you have commits that have not been pushed, or upstream changes that have not been pulled, the commit button will change to read "Sync Changes". Clicking it in this mode will do the same thing as pressing the Synchronize Changes button in the Repositories section.

Below the Commit button is a pair of dropdowns labeled "Staged Changes" and "Changes". The staged section will only show up if you actually have any changes staged. 

From left to right, the buttons on the Staged Changes dropdown allow you to open a comparison view of all changes, unstage all changes, and view a count of how many files have changes staged. Files under the Staged Changes dropdown offer a button to open them, and a button to unstage that specific file.

From left to right, the buttons on the Changes dropdown allow you to open a comparison view of all changes, revert all changes destructively, stage all changes, and view a count of how many files have unstaged changes. Files under the Changes dropdown offer a button to open them, revert all changes to that specific file, and stage the changes made to that file.

### Graph

This section offers a set of buttons related to viewing and changing Git history, and a graph of all commits.

From left to right, the buttons at the top of the Graph section let you change which branch is shown (leave it at auto), a button to go to the current history item, a button to pull from all remotes, a button to pull from the current remote, a button to push, a refresh button, and a button to change if the graph displays as a list or as a tree.

You may hover over a commit in the list of commits to view the full commit message, how many changes were made, the timestamp, the local branch, and the remote branch. Clicking on a commit will list the files which were changed by that commit.

# Contributing

Please see [CONTRIBUTING.md](https://github.com/Probably-Artemis/ide-setup/blob/main/CONTRIBUTING.md) for the full guidelines to contribution.

Any part of my instructions which is unclear, unspecific, or otherwise not beginner friendly warrants the opening of an issue.