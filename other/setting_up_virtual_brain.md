Download the virtual brain zip:

https://www.thevirtualbrain.org/tvb/zwei/brainsimulator-software?_ga=2.108223554.1918290645.1554913451-2133742430.1554913451

Unzip: will have a folder ‘TVB_Distribution’

Setup a github account
Fork the TVB-library repository to your account

Create a python 2.7 environment:
conda create --name tvb python=2.7

Activate this environment:
source activate tvb

You need a specific old version of matplotlib installed:
pip install matplotlib==1.5.1

Set PYTHONHOME to your environements python:
export PYTHONHOME=/Users/yourname/anaconda/envs/tvb

Navigate to the folder TVB_distribution/bin and run:

sh contributor_setup.sh https://github.com/[your_github_account]/tvb-library.git

Go to TVB_distribution/tvb-library

python setup.py develop

Deal with the errors as they arrive according to the instructions generated

Add the needed packages so that ipython/jupyter can access you kernel

conda install nb_conda ipykernel

python -m ipykernel install --user --name tvb