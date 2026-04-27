# Git & GitHub: an introduction



## Requirements (to be done before the first lecture)

* Install [Git](https://git-scm.com/) on your laptop. (Notice that on
  University computers, Git is already available.)
* Create an account on [GitHub](https://github.com/).  **Important:** Log out from GitHub before
  the first lecture.
* **Optional:**  You might want to download a [Graphical interface to Git](https://git-scm.com/tools/guis). (On University computers, gitk is already available.)


### Installation of Git

#### Linux

Type one of the following in a terminal:
```bash
sudo apt install git
sudo dnf install git
```


#### MacOS

First, install [HomeBrew](https://brew.sh/)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then install Git using HomeBrew

```bash
brew install git
```


#### Windows 


1. Download [Git for Windows](https://git-scm.com/download/win)
2. Run the Installer
Most screens you can just click **Next**, but a few matter:

| Screen | Recommended Choice |
|--------|-------------------|
| Default editor | Pick **Notepad** |
| PATH environment | **"Git from the command line and also from 3rd-party software"** ← important |
| Line ending conversions | **"Checkout Windows-style, commit Unix-style"** |
| Everything else | Leave defaults |

3. The Critical Option Explained Simply
> *"When it asks about PATH, pick the middle option - this is what lets VSCode and other programs find Git automatically"*

4. How to Verify It Worked
Open **Command Prompt** or **PowerShell** and type:
```
git --version
```
It should print something like `git version 2.x.x`

