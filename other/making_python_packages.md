Creat a folder for your package and put these 3 files in it:

module_name.py – this is a list of functions that you have written

README.txt – can be blank

setup.py – as below
from setuptools import setup

setup(
name='module_name',
version = '1.0',
description = 'this module does this',
author='Rob McCutcheon'
author_email = 'rob.mccutcheon1@gmail.com'
url = 'blah.com',
py_modules=['module_name'],
install_requires=[‘A==1.0’, ‘B>=1,<2’], )

'py_modules' is the list of .py files to include in our case just one (and this file can contain multiple functions)
'install_requires' allows us to specify dependencies in setup file:

Go to the folder where these files are and run:

python setup.py sdist

then enter the dis folder that has just been distributed

sudo -m pip install module_name-1.0.tar.gz

We can now import it like any other module

If we change the module_name.py file we have to change the version number in the setup.py file and reinstall the package

To upload to PyPi:
https://marthall.github.io/blog/how-to-package-a-python-app/

http://python-packaging.readthedocs.io/en/latest/minimal.html

When initially designing function and ironing out kinks it is easier to just work with the module_name.py file in your working directory and it can then be easily reloaded after editing by just calling it with import module_name