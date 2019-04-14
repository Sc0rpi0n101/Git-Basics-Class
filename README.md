# ALiAS School

## Basics of Git and Github Class

Welcome to the basics of Git and Github class.
In this class you will be learning about the basic git commands and how to use github to host your projects and contribute to other's projets.
First, youneed to know what Git and Github are adn what are they used for:

Git is a free and open source distributed version control system. It is designed for coordinating work among programmers and can be used to track changes in your project.

GitHub is a web-based hosting service for version control using Git. It is mostly used to store source code for projects which include contributions from multiple people across various locations.

This class will consisit of several assignments which will help you work on basic git commands and handling Github repositories. You will have to submit those assignments in form of pull requests and your teachers will be reviewing them to assess if you've learned and implemented what was required of you in the assignments.

The assignments for this class are:
1. Introduction to Git and your first pull request.
2. Creating your own repository and Branching.
3. Merging, rebasing and squashing commits.

### Installing Git

#### Installing Git on Windows

* Download the latest [Git for Windows installer](https://gitforwindows.org/).

* When you've successfully started the installer, you should see the Git Setup wizard screen. Follow the Next and Finish prompts to complete the installation. The default options are pretty sensible for most users.

* Open a Command Prompt (or Git Bash if during installation you elected not to use Git from the Windows Command Prompt).

#### Installing Git on Linux

If you want to install the basic Git tools on Linux via a binary installer, you can generally do so through the package management tool that comes with your distribution.

##### Debian and Ubuntu:

```bash
sudo apt update
sudo apt install git-all
```

##### CentOS:

```bash
sudo yum install git
```

##### Fedora:

```bash
sudo yum install git
```

or

```bash
sudo dnf install git -all
```

##### Arch Linux:

```bash
sudo pacman -Sy git
```

##### Gentoo:

```bash
sudo emerge --ask --verbose dev-vcs/git
```

##### Build Git from source on Linux

###### Debian / Ubuntu

Git requires the several dependencies to build on Linux. These are available via apt:

* From your shell, install the necessary dependencies using apt-get:

```bash
$ sudo apt-get update
$ sudo apt-get install libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev asciidoc xmlto docbook2x
```

* Clone the Git source (or if you don't yet have a version of Git installed, download and extract it):

```bash
$ git clone https://git.kernel.org/pub/scm/git/git.git
```

* To build Git and install it under /usr, run make:

```bash
$ make all doc info prefix=/usr
$ sudo make install install-doc install-html install-info install-man prefix=/usr
```

###### Fedora

Git requires the several dependencies to build on Linux. These are available via both yum and dnf:

* From your shell, install the necessary build dependencies using dnf (or yum, on older versions of Fedora):

```bash
$ sudo dnf install curl-devel expat-devel gettext-devel openssl-devel perl-devel zlib-devel asciidoc xmlto docbook2X
```

* or using yum. For yum, you may need to install the Extra Packages for Enterprise Linux (EPEL) repository first:

```bash
$ sudo yum install epel-release
$ sudo yum install curl-devel expat-devel gettext-devel openssl-devel perl-devel zlib-devel asciidoc xmlto docbook2X
```

* Symlink docbook2X to the filename that the Git build expects:

```bash
$ sudo ln -s /usr/bin/db2x_docbook2texi /usr/bin/docbook2x-texi
```

* Clone the Git source (or if you don't yet have a version of Git installed, download and extract it):

```bash
$ git clone https://git.kernel.org/pub/scm/git/git.git
```

* To build Git and install it under /usr, run make:

```bash
$ make all doc prefix=/usr
$ sudo make install install-doc install-html install-man prefix=/usr
```

#### Installing Git on Mac

##### Git for Mac Installer

The easiest way to install Git on a Mac is via the stand-alone installer:

**Download the latest [Git for Mac installer](https://sourceforge.net/projects/git-osx-installer/files/).**

* Follow the prompts to install Git.

* Open a terminal and verify the installation was successful by typing `git --version`

##### Install Git with Homebrew

* Open your terminal and install Git using Homebrew:

```bash
$ brew install git
```

##### Install Git with MacPorts

If you have installed MacPorts to manage packages on OS X, you can follow these instructions to install Git:

* Open your terminal and update MacPorts:

```bash
$ sudo port selfupdate
```

* Search for the latest available Git ports and variants:

```bash
$ port search git
$ port variants git
```

* Install Git with bash completion, the OS X keychain helper, and the docs:

```bash
$ sudo port install git +bash_completion+credential_osxkeychain+doc
```

##### Build Git from source on OS X

Building Git can be a little tricky on Mac due to certain libraries moving around between OS X releases. On El Capitan (OS X 10.11), follow these instructions to build Git:

* From your terminal install XCode's Command Line Tools (if you haven't already):

```bash
$ xcode-select --install
```

* Install [Homebrew](https://brew.sh/) using:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* Using Homebrew, install openssl:

```bash
$ brew install openssl
```

* Clone the Git source (or if you don't yet have a version of Git installed, download and extract it):

```bash
$ git clone https://github.com/git/git.git
```

* To build Git run make with the following flags:

```bash
$ NO_GETTEXT=1 make CFLAGS="-I/usr/local/opt/openssl/include" LDFLAGS="-L/usr/local/opt/openssl/lib"
```

### First Time Git Configuration

You need to configure your git config before you start using git.
The first thing you should do when you install Git is to set your user name and email address. This is important because every Git commit uses this information:

```bash
$ git config --global user.name "your name"
$ git config --global user.email your-email@domain.com
```

you can also configure the default editor to edit you commits using

```bash
$ git config --global core.editor <path to your editor>
```

If you want to check your configuration settings, you can use the `git config --list` command
