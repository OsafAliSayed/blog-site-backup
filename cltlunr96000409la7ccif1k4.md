---
title: "Getting over different Python versions using pyenv"
datePublished: Sun Mar 10 2024 18:30:20 GMT+0000 (Coordinated Universal Time)
cuid: cltlunr96000409la7ccif1k4
slug: getting-over-different-python-versions-using-pyenv
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707196195178/3d569609-e5a2-4022-9a60-9180b464c241.png
tags: python, opensource, version-control, environment, pyenv, environment-variables

---

If you are an open-source contributor working with technologies such as Django, Flask, Python, etc then you know how tedious it gets to manage different Python versions. Every time you need to replicate some issue you will need to set up the environment again. This process is very tedious and takes a lot of time.

However, we do have a solution for this, Enter "pyenv"! This command line script allows us to create and manage multiple Python versions and environments. This tutorial will teach you how to set up "pyenv" and some basic commands to get you started.

### Installation

To install Pyenv simply follow this [article](https://k0nze.dev/posts/install-pyenv-venv-vscode/).

### Basic Commands

I am covering all the basic Pyenv commands here for reference. This will be useful until we memorize these basic commands

```powershell
# show all python versions that are available
pyenv install -l

# install a specific python version
# replace <version> with the required version
pyenv install <version> 

# check installed python versions
pyenv versions

# activate python version for a shell session
pyenv shell <version>

# set global python version
pyenv global <version>

# set local python version
# creates a python-version file for local folder to maintain the local version
pyenv local <version>

# We can also create a virtual environment and use it with local version as follows
# make sure our local python version is set before creating environment
# create virtual environment named venv
python -m venv venv

# activate virtual environment for windows
venv/Script/activate

# activate virtual environment for linux
venv/bin/activate

# check local pip location
get-command pip
```

### Conclusion

Pyenv is a lifesaver if you are an open-source contributor and are using multiple Python versions.

Leave a like if this helped you and subscribe to my newsletter for these short 4-5 min-content on the tech world.