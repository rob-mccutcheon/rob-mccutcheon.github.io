The following is a guide to setting up a python environment on mac OSX

1. Update OSX (About This Mac–>software update)

2. Install xcode command line tools (we need these to install homebrew). To do this open terminal and enter:

xcode-select --install

3. Install homebrew

Homebrew is an easy to use package manager for OSX that helps install packages and keep them working well together

To install homebrew in terminal type:

ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

4. Now we need to tell the computer where to look for packages that homebrew installs. To do this we need to edit the .bash_profile this is a text file is read whenever you open a new terminal window and give terminal instructions about e.g. where to look for files.

Homebrew installs packages in /usr/local/bin

In order to make terminal look here open .bash_profile in a text editor and put the following at the top of the file:

export PATH="/usr/local/bin:$PATH"

This says look in usr/local/bin and then look in the rest of the path.

5. If we now update the current terminal window with the changes we have made to .bash_profile by typing:

source ~/.bash_profile

We can then check that the path has been modfied correctly by typing in terminal:

echo $PATH

6. There is an existing version of python on your Mac that we do not want to interfere with. We want to install our own version of both python 3.7 and python 3.6. To do this we run in terminal:

brew install python
brew install python3

7. We now have two new version of python installed. To keep things neat and tidy and prevent problems developing with different programs needing different version of things it makes sense to work in virtual environments.

pip install virtual env
pip install virtualenvwrapper

We want to amend our .bash_profile again with the following. This tells virtualenvwrapper where to store your virtual environments so you can change the folder location to somewhere else if you wish.

export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/Devel
source /usr/local/bin/virtualenvwrapper.sh

8. We can now make a python3 virtual environment

mkvirtualenv --python=`which python3` nameOfPython3Environment

and install some packages that we may want to use
pip3 install --user numpy scipy matplotlib ipython nibabel jupyter

Now let’s also make a python 2 environment, first exit the python 3 environment:

deactivate
mkvirtualenv --python=`which python` nameOfPython2Environment