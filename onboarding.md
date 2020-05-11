# Mojaloop Onboarding

## <a name='Contents'></a>Contents 

<!-- vscode-markdown-toc -->
1. [Installing CLI Tools](#InstallingCLITools)
2. [Non-CLI Tools](#Non-CLITools)
3. [Development Workflow](#DevelopmentWorkflow)
4. [Contributing to a Specific Sub Project](#ContributingtoaSpecificSubProject)
5. [Other Useful Links](#OtherUsefulLinks)
6. [Common Errors & FAQs](#CommonErrorsFAQs)

<!-- vscode-markdown-toc-config
	numbering=false
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->


## <a name='InstallingCLITools'></a>Installing CLI Tools

Building and Running Mojaloop from source requires the following tools:

1. [`brew`](#1-brew-macos) (MacOS) [todo: windows package manager]
2. [`docker`](#2-docker)
3. [`docker-compose`](#3-docker-compose)
4. [`npm` and `nvm`](#4-npm-and-nvm)(optional)


### <a name='brewMacOS'></a>1. `brew` (MacOS)

#### macOS
Brew is a package manager for macOS. The simplest installation method is:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Linux
[todo: make sure tools are available on apt and yum]

Most of the tools we install with `brew` are available on existing linux package managers, such as `apt` and `yum`. That doesn't stop you from using brew on Linux if you'd like. You can follow the [Official Linux Installation Guide](https://docs.brew.sh/Homebrew-on-Linux) to do so.

#### Windows
[todo: find alternative]


### <a name='docker'></a>2. `docker`

We use docker to build reliable images of the Mojaloop components, as well as install and run other developer tools such as MySQL and Kafka without requiring the overhead of installing a bunch of stuff.

#### macOS
Follow the Docker for Mac installation guide [here](https://docs.docker.com/docker-for-mac/)


#### Linux
Install Docker for Ubuntu [here](https://docs.docker.com/install/linux/docker-ce/ubuntu/), or Docker for CentOS [here](https://docs.docker.com/install/linux/docker-ce/centos/).  
You can also install from docker binaries if your flavor of Linux is not supported [here](https://docs.docker.com/install/linux/docker-ce/binaries/).

#### Windows
Follow the Docker Desktop for Windows installation guide [here](https://docs.docker.com/docker-for-windows/install/).


### <a name='docker-compose'></a>3. `docker-compose`
Docker Compose is a tool for easily running multiple docker containers at once. It can be used to replace cumbersome `docker run` commands with a `docker-compose.yml` file.

##### macOS
If you installed Docker using Docker for Mac, then `docker-compose` is already installed. Run:
```bash
docker-compose --version
```

To verify its installation.

##### Linux
Follow [this guide](https://docs.docker.com/compose/install/) to install `docker-compose` on your linux machine.


##### Windows
If you installed Docker using  Docker Desktop for Windows, then `docker-compose` is already installed. Run:
```bash
docker-compose --version [todo: confirm]
```

To verify its installation.


### <a name='npmandnvm'></a>4. `npm` and `nvm`

The preferred approach (especially if you use node on multiple projects) is to use `nvm` ([Node Version Manager](https://github.com/nvm-sh/nvm)) to manage your global nodejs versions. There are other tools available to manage your node versions, but `nvm` is the lightest weight, and tends to need the least amount of configuration.


#### <a name='nvm'></a>nvm

`nvm` is a version manager for node. It's not strictly required, but it will make it easier to switch from one node version to another.


##### Linux

Ensure that you have `curl` or `wget` installed, and run:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash 
```
or with wget:
```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Then follow the rest of the MacOS installation steps.

##### macOS

Use a `brew` package manager

```bash
brew install nvm
```
and follow instructions shown in terminal to properly setup your shell environment for `nvm`.

Or download and install the nvm installer with curl:

```bash
curl https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

If the install was successful, run `nvm --version` which should return the version of nvm installed.

Install and use the latest LTS version of NodeJS: _(at the time of writing this is `10.15.3`)_
```bash
nvm install --lts
nvm use --lts
```

##### Windows
[todo]

##### Set Up NVM In `~/.bash_profile`, `.zshrc`, or `.profile`:

For NVM to work the next time you open your shell, you need to make sure that following exists in your `.bash_profile`, `.zshrc`, or `.profile`:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

If you don't have a `~/.bash_profile`, you can create one with:
```bash
touch ~/.bash_profile
```
And using a your text editor of choice, add the following:
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

You will need to run `source ~/.bash_profile`, or restart your shell for these changes to take effect.


#### <a name='NPM'></a>NPM

NPM is the node package manager. It allows us to install and manage the dependencies for each of the sub-projects.
We also use npm as the entry point for many different commands, such as running tests [finish]

If you installed `nvm` above, you can skip this step, as `npm` will already be installed.


##### macOS

Use homebrew to install `node` and `npm` together.

```bash
brew install node
```

If you have already installed `nvm` (see above) you can skip this step. Elsewhere you can have multiple Node.js instances and it could bring some problems in future.

##### Linux

```bash
#Add the LTS Repo
sudo apt-get install curl python-software-properties
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -

sudo apt-get install nodejs

```

For other flavours of Linx, follow the installation guide [here](https://nodejs.org/en/download/package-manager/)


##### Windows

[todo]



## <a name='Non-CLITools'></a>Non-CLI Tools

1. [Github](#1-github)
2. [Postman](#2-postman)
3. [Zenhub](#3-zenhub)
4. [Javascript IDE](#4-javascript-ide) (optional)
5. [MySQLWorkbench](#5-mysqlworkbench) (optional)


### <a name='Github'></a>1. Github

All of the Mojaloop repos are available on Github. While you don't need a GitHub account to download and play around with the code, you must have your own GitHub account set up in order to contribute to Mojaloop.

In order to contribute to a given repo, you should first make a fork of the repo in your own account, and submit a pull request from that fork. For more information about contributing, refer to the [Creating new Features](http://mojaloop.io/documentation/contributors-guide/standards/creating-new-features.html) guide in the Mojaloop Documentation.

### <a name='Postman'></a>2. Postman

Postman is a tool for exploring and testing APIs.

To install Postman, follow these instructions: [Get Postman](https://www.getpostman.com/postman)

Alternatively on **Ubuntu** you may run:
```
wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
sudo tar -xzf postman.tar.gz -C /opt
rm postman.tar.gz
sudo ln -s /opt/Postman/Postman /usr/bin/postman
```

#### <a name='PostmanSetup'></a>Postman Setup

There are already a number of ready-made Mojaloop Postman collections in the [Postman Repo](https://github.com/mojaloop/postman).

```bash
git clone git@github.com:mojaloop/postman.git
```

You can then import these collections into your Postman:
* open *Postman*
* click **Import** and then **Import File**
* navigate to the `postman` directory and select `Mojaloop.postman_collection.json`

Each of the collections depend on an *environment* to be imported as well.
* open *Postman*
* click **Import** and then **Import File**
* navigate to the `postman/environments` directory and select the most appropriate environment for your mojaloop setup. For example, when running mojaloop Locally, import and use the `MojaloopLocal.postman_environment.json` environment.


### <a name='Zenhub'></a>3. Zenhub

Zenhub is a Project Management Plugin for GitHub. It adds some helpful features such as Kanban, easier project management workflows, etc.

* First, navigate to https://www.zenhub.com/ and sign in with your GitHub Account
* Next, add the Zenhub plugin for your browser
  - [Chrome Installer](https://chrome.google.com/webstore/detail/zenhub-for-github/ogcgkffhplmphkaahpmffcafajaocjbd)
  - [Firefox Installer](https://www.zenhub.com/extension)

[todo]


### <a name='JavascriptIDEOptional'></a>4. Javascript IDE (Optional)

When developing for Mojaloop, you may wish to use a Javascript IDE or a simple text editor. There are plenty available out there, including:
- [VSCode](https://code.visualstudio.com/)
- [Atom](https://atom.io/)
- `vim` (not for the faint of heart)
- [Webstorm](http://www.jetbrains.com/webstorm/) (free 30 day trial)



### <a name='MySQLWorkbenchOptional'></a>5. MySQLWorkbench (Optional)

[MySQL Workbench](https://www.mysql.com/products/workbench/) is a GUI Based database management tool.

We will only cover the installation of MySQLWorkbench in this guide. For using MySQLWorkbench with a given sub-project, refer to the specific on-boarding guide in the respective project.

#### macOS

use `brew` package manager
```bash
brew cask install mysqlworkbench
```

Or: 
* Go to this page [here](https://dev.mysql.com/downloads/workbench/)
* Scroll down the page > select **macOS** for the operating system > *Download*

>_Note: this version of MySQLWorkbench is compatible with Mojave (10.14) and High Sierra (10.13)_ 

#### Linux

For debian based linux, you can install using `apt`:

```bash
sudo apt install mysql-workbench
```

For other linux flavours follow the instructions [here](https://dev.mysql.com/downloads/workbench/)

#### Windows

* Go to this page [here](https://dev.mysql.com/downloads/workbench/)
* Scroll down the page > select **Windows** for the operating system > *Download*
* Run the installer and open MySQL Workbench


## <a name='DevelopmentWorkflow'></a>Development Workflow

While the workflow will change for each Mojaloop sub-project, these steps will generally applicable to any part of the codebase that you end up working on. For more information, take a look at the [Creating new Features](https://github.com/mojaloop/documentation/blob/master/contributors-guide/standards/creating-new-features.md) guide, but in summary:

**For each sub-project:**
```bash

git clone https://github.com/<your_username>/<forked_repo>.git && cd <forked_repo>
git remote add mojaloop https://github.com/mojaloop/<original_repo>.git
```

**For each new feature:**
```bash
git checkout -b <branchType>/<issue#><issueDescription>
```

More information about formatting branches here: [Creating new Features](https://github.com/mojaloop/documentation/blob/master/contributors-guide/standards/creating-new-features.md#creating-a-branch)


**Commiting code changes**
```bash
npm install  # installs the dependencies
npm run test # runs the local unit tests
git commit -am "<Commit message>"
git push
```

If you need help writing good commit messages, take some inspiration from [this post](https://chris.beams.io/posts/git-commit/).

**Merge into Mojaloop**
Once a feature is complete, you can create a PR from your Feature Branch into the `master` branch of the Mojaloop repository.


## <a name='ContributingtoaSpecificSubProject'></a>Contributing to a Specific Sub Project

Now that you have completed this onboarding guide, you are now ready to follow the installation and setup steps for each individual mojaloop sub-project.

Follow the Onboarding guides for each sub project here:
- [ml-api-adapter](https://github.com/mojaloop/ml-api-adapter/blob/master/Onboarding.md)
- [central-ledger](https://github.com/mojaloop/central-ledger/blob/master/Onboarding.md)
- [mock-pathfinder](https://github.com/mojaloop/mock-pathfinder/blob/master/Onboarding.md)



## <a name='OtherUsefulLinks'></a>Other Useful Links
- [Mojaloop Specification Documents](https://github.com/mojaloop/mojaloop-specification)
- [Mojaloop Project Repo](https://github.com/mojaloop/project) - for tracking issues across all sub-projects




## <a name='CommonErrorsFAQs'></a>Common Errors & FAQs

- None yet. If you run into a problem or have a question, ask away and we can add to this list for future reference.



