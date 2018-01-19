# A quick introduction to creating python modules

## Set-up the module environments
 
### make package directories
mkdir -p ~/python_modules/demoSphinx
cd ~/python_modules/demoSphinx

### Create minimal files required for a python module
1. setup.py
wget https://www.ebi.ac.uk/~hannah/demoSphinx/setup.py
1. a script
mkdir -p ~/python_modules/demoSphinx/demoSphinx/io
cd ~/python_modules/demoSphinx/demoSphinx/io
wget https://www.ebi.ac.uk/~hannah/demoSphinx/demoSphinx/io/input_raw.py
cd ../..
1. `__init__.py` files

## Create a python environment to setup our package
conda create -n demo python=2.7

### Download module developers tools
conda install -n demo setuptools 

#install these packages for uploading to repositories
#conda install -n demo wheel twine
#pip install twine

### activate the conda environment
source activate demo

### intall our package in developer mode
pip install -e .

## Document package with Sphinx
### install sphinx
conda install sphinx

### Run the quickstart
mkdir -p ~/python_modules/demoSphinx/doc
cd ~/python_modules/demoSphinx/doc
sphinx-quickstart

#if running on the cluster
ln -s ~/demo/demoSphinx ~/public_html/demoSphinx
