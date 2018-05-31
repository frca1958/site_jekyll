---
title: "Working with Python"
---


## Installation of python3

Python3 is now installed by default on non-minimal installations.
Python2.7 (legacy python) is often installed or needed by system packages.
So essentially, there are 2 python versions on most systems today.
If python is not yet installed (docker images), the approach is

```
sudo apt install python3-minimal
#for v2.7: sudo apt install python-minimal
```

The major tool for python development is pip.
Since development is normally under python3, do this:

```
sudo apt install python3-pip
#only for v2.7 development: sudo apt install python-pip
```

## Working with virtual environments

If you consistently use python3 and pip3, there should not be much reason to use pipenv.
However it ensures that accidentally using pyton or pip does not ruin the work.mc

```
pip3 install pipenv
```
After this, you may need logout/login so that the path to ~/.local/bin is activated.

## Example use
An example of the use of pipenv is here(http://docs.python-guide.org/en/latest/dev/virtualenvs/). Essentially:

```
mkdir test
cd test
pipenv install requests
#create an example program 
pipenv run python3 main.py
#or go to the virtual environment
pipenv shell
```




