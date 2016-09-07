## Setup

### Cloning Frescolino
    
    git clone git@github.com:FrescolinoGroup/Frescolino --recursive

maybe there's a git issue (2.7) when cloning recursivly and the renaming the folder...
then use:

    git clone git@github.com:FrescolinoGroup/Frescolino
    cd Frescolino
    
    git submodule update --recursive --init
    git submodule foreach --recursive git checkout master

the website repo needs to be called website and reside in the toplevel of Frescolino
because the modules build the doc in here

    git clone git@github.com:FrescolinoGroup/FrescolinoGroup.github.io.git website

The website is in the `.gitignore` file of the main repo.

### New Python Module

    
    ./helpers/create_module.py FancyTestMod ftm python --github
    cd ./modules/FancyTestMod

the remote github repo will be set up automatically

    python setup.py register
    
use your pypi account here
    
    python setup.py sdist upload

go to the pypi page, log in, go to fsc.ftm -> role and do the following
1) add frescolino as owner
2) add yourself as maintainer
3) remove yourself as owner

now this package can be installed via pip:

    pip install fsc.ftm

or reinstall fsc and use the detector to install all fsc.* 
modules for your python version:
    
    pip install fsc --force-reinstall --upgrade

