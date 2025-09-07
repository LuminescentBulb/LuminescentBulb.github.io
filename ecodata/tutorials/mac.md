---
layout: spec
---

MacOS Tutorial for EcoData
=====================================
## Terminal Setup
macOS comes with a Terminal and can run UNIX command-line tools directly.

The macOS terminal command prompt ends with a `$`. To follow the steps below, type commands that appear after the `$` and hit enter.

### Open terminal
Open the Terminal application which comes with macOS.

<img src="/images/macos001.png" width="480px" /> | <img src="/images/macos010.png" width="480px" />

### Homebrew package manager
Install the [Homebrew package manager](https://brew.sh/).
```console
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Then run the following to add Homebrew to your path:

```console
$ echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
```

Close your terminal and reopen your terminal.

Check your install.  Your version might be different.
```console
$ brew --version
Homebrew 4.6.7
```

### Install CLI tools
Use the Homebrew package manager to install common command line programs that we use in EcoData:

```console
$ brew install wget git tree python node
```

### Home Directory
Run `cd ~`. This will take you to your home directory (Different from / which is ROOT directory). Running `pwd` afterward confirms the location. (Your username will be different.)

```console
$ cd ~
$ pwd
/Users/jjuett
```

Create an EcoData folder by running `mkdir ~/ecodata`. Running `ls` afterward confirms the folder has been created.

```console
$ mkdir ~/ecodata
$ ls
Desktop		Downloads	Movies		Pictures	ecodata
Documents	Library		Music		Public
```

<div class="primer-spec-callout warning" markdown="1">
**Pitfall:** Avoid paths that contain spaces. Spaces cause problems with some command line tools.

| Bad Example     | Good Example   |
|-----------------|----------------|
| `Solar Panel/` | `solar_panel/` |
| `Project 1 Stats/` | `p1-stats/` |

</div>

### CLI Tutorial
If you have time and want to learn more about the command line, check out EECS 280's [CLI Tutorial](https://eecs280staff.github.io/tutorials/cli.html).
We will only need relatively simple commands like `ls`, `cd`, `mkdir` in general, and more specific commands will be taught within projects. 

## VSCode Setup
Personally, I recommend VSCode since almost everyone in EECS uses it and it runs on both macOS, Windows, and Linux. psst: Do NOT confuse with Visual Studio. 

### Install

Use the homebrew package manager to install VS Code.  You can run this command from any directory.
```console
$ brew install --cask visual-studio-code
```

Open VS Code. You can find it in your applications (look for "Visual Studio Code") or, alternatively, you can run it using the command line.
```console
$ code
```

And that's it! You don't need to do anything more with VSCode until you get into your project groups, where we will give further instructions on how to use git to work with other people,
as well as any project specific extensions you might need. 


## Acknowledgments
This tutorial is adapted from [Andrew DeOrio's original document](https://eecs280staff.github.io/tutorials/setup_macos.html), licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Modifications have been made for EcoData.  