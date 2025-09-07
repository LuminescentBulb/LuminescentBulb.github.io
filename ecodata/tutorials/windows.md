---
layout: spec
---

Windows Tutorial for EcoData
=====================================

## Install WSL
Open Windows Powershell in Administrator mode to run the commands below.
If you don't have WSL already (check by running `wsl -l -v`). then you will need to install it.

Run the following command if you don't have it:
```console
wsl --install -d Ubuntu-24.04
```

Restart your computer and then check Ubuntu is installed.
```console
C:\WINDOWS\system32> wsl -l -v
  NAME                   STATE           VERSION
* Ubuntu-24.04           Running         2
```

## Setup Ubuntu
From the previous section, you have installed WSL and an Ubuntu Linux distribution. You'll need it for running package managers like npm or yarn for web dev or python environments.

Start an Ubuntu Bash shell. Bash is a command-line interface for Linux. Search for "Ubuntu" (or "Ubuntu 24.04 LTS") or "bash" in the start menu.

<img src="/images/wsl020.png" width="240px" /> | <img src="/images/wsl030.png" width="480px" />

The bash command prompt ends with a `$`. To follow the steps below, type commands that appear after the `$` and hit enter.

### First time: create account
The first time you open Ubuntu, you will be prompted to create a Linux username and password. Follow the prompts to create one.
- Choose a username that is all lowercase characters (could be your uniqname).
- While typing your password, the characters are not shown. This is fine.
- You can press <kbd>Enter</kbd> to skip fields other than username and password (e.g. "room number").

<img src="/images/wsl035.png" width=768px>

Double check that your user has been created. (Your username will be different.)
```console
$ whoami
awdeorio  # this should NOT say root
```
### Install CLI tools

From an Ubuntu bash terminal, use the `apt` package manager to install essential command line programs for development, including tools for C++, Python, Git, and web development.

```console
$ sudo apt update
$ sudo apt install g++ make rsync wget git ssh gdb python3 python3-pip tree npm
```

- `npm` is included for managing JavaScript packages (needed for Next.js or React projects).
- `python3-pip` is included for installing Python packages (useful for machine learning).
- You may also want to install additional tools for ML or web development as needed:

```console
$ sudo apt install build-essential libssl-dev
```

### Home Directory
You'll generally want to store your coding projects in the Linux filesystem, which is separate from your Windows filesystem.

From an Ubuntu bash terminal, run `cd ~`. This will take you to your Ubuntu home directory (~ is home directory, not to be confused with / which is ROOT directory). Running `pwd` afterward confirms the location. (Your username will be different.)

```console
$ cd ~
$ pwd
/home/jjuett
```

Create an EcoData folder by running `mkdir ~/ecodata`. Running `ls` afterward confirms the folder has been created.

```console
$ mkdir ~/ecodata
$ ls
ecodata
```

### CLI Tutorial
If you have time and want to learn more about the command line, check out EECS 280's [CLI Tutorial](https://eecs280staff.github.io/tutorials/cli.html).
We will only need relatively simple commands like `ls`, `cd`, `mkdir` in general, and more specific commands will be taught within projects. 

## VSCode Setup
Personally, I recommend VSCode since almost everyone in EECS uses it and it runs on both macOS, Windows, and Linux. psst: Do NOT confuse with Visual Studio. 

### Install

Ensure the prerequisites above are satisfied, then install VS Code from the web [https://code.visualstudio.com/](https://code.visualstudio.com/).

Select each of the options below during installation.

<img src="/images/vscode_wsl_005.png" width="480px" />

Open VS Code. You can skip the welcome screen.

<img src="/images/vscode_wsl_007.png" width="768px" />

### WSL Extension

Install the WSL Extension, which allows the VS Code backend to run in WSL where the C++ compiler lives.

1. Open the extensions panel from the left sidebar.
2. Search for WSL.
3. Click "Install".

VS Code might attempt to install this one automatically - if so, you may see "Installing" followed by a "Reload Window" option. Click that instead of "Install".

<img src="/images/vscode_wsl_008.png" width="768px" />

Next, connect to WSL:
1. Click the button in the bottom left corner.
2. Select "Connect to WSL using Distro..." from the menu.
3. Choose "Ubuntu 24.04" from the list.

<img src="/images/vscode_wsl_012.png" width="768px" />

Now, the button in the bottom left should say "WSL: Ubuntu-24.04". For any C++ development, make sure VS code is always connected to WSL. Depending on your version of VS Code and Windows, your button might be blue instead of green, and you might not have the purple bar at the bottom of your window - that's fine.

<img src="/images/vscode_wsl_013.png" width="768px" />

And that's it! You don't need to do anything more with VSCode until you get into your project groups, where we will give further instructions on how to use git to work with other people,
as well as any project specific extensions you might need. 

## Acknowledgments
This tutorial is adapted from [Andrew DeOrio's original document](https://eecs280staff.github.io/tutorials/setup_wsl.html), licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Modifications have been made for EcoData.  
