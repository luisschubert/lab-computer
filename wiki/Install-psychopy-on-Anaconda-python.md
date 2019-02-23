# Summary

After installing Anaconda, open the command line with Anaconda python on your PATH, and run the following commands to install `psychopy` and its dependencies in an isolated virtual environment named "psychopy".

**Note:** This is a summary of all installation steps in one place. Each step is described in more detail below.

```bash
(root) $ conda create -n psychopy python=2
(root) $ source activate psychopy
(psychopy) $ conda install numpy scipy matplotlib pandas pyopengl wxpython lxml openpyxl xlrd configobj pyyaml gevent pillow greenlet msgpack-python psutil pytables requests seaborn future
(psychopy) $ conda install --channel conda-forge pyglet
(psychopy) $ pip install moviepy pyosf python-bidi psychopy_ext psychopy json_tricks
(psychopy) $ conda install --channel cogsci pygame
```

# Install Anaconda

## Installing Anaconda on Windows

Download Anaconda python via the .exe installer from the Continuum.io website at <https://www.continuum.io/downloads>. Find the links to install Anaconda for Windows, Python 3 version. On this page we are installing 64-bit python, so select the 64-bit installer for Python 3.

After Anaconda is installed, it creates a number of program in the Start menu, one of which is called Anaconda prompt. This opens a terminal session with Anaconda python on the PATH, that is, from this terminal and only this terminal, typing `python` is guaranteed to run the version of python installed by Anaconda. Other terminals you may have access to on your Windows machine may be the PowerShell or Cygwin or Git Bash. These terminals are not guaranteed to be able to find and run your Anaconda python install correctly.

## Installing Anaconda on macOS

On macOS, I recommend installing Anaconda python with Homebrew.

```bash
brew cask install anaconda
```

This will likely install Anaconda system-wide in "/usr/local/anaconda3/". To use it, open up Terminal and activate it with the following command:

```bash
source /usr/local/anaconda3/bin/activate
(root) $
```

# Create a virtualenv named "psychopy"

The next step is to create an isolated virtual environment. We'll name it "psychopy". The python package `psychopy` requires Python 2. Regardless of whether the default Python we installed with Anaconda is Python 2 or Python 3, we can create a virtualenv with Python 2 with the following commands.

```bash
(root) $ conda create -n psychopy python=2  # create the virtualenv with python2
(root) $ source activate psychopy           # activate the new virtualenv
(psychopy) $
```

# Install psychopy dependencies with conda

The command `conda install` is a special way of installing python packages in an Anaconda environment. This is basically an amped-up python installer like `pip` that makes it easy to install python packages for scientific computing. The additional option `--channel` as in `conda install --channel conda-forge pyglet` installs the `pyglet` package from an external source of python packages.

**Note:** The fact that the following lines "just work" is what makes Anaconda so useful.

```bash
(psychopy) $ conda install numpy scipy matplotlib pandas pyopengl pillow \
                           wxpython lxml openpyxl xlrd configobj pyyaml gevent \
                           greenlet msgpack-python psutil pytables requests \
                           seaborn
(psychopy) $ conda install --channel conda-forge pyglet
```

# Install psychopy dependencies with pip

Some packages that are required for `psychopy` are not available to install via the `conda install` command, and must be installed via `pip`. Luckily `pip` and `conda` work well together, and `pip` will install the packages to the right place: the active Anaconda environment named "psychopy" that you created and activated.

```bash
(psychopy) $ pip install moviepy pyosf python-bidi psychopy_ext
```

# Install psychopy

Now that the requirements for a basic `psychopy` experiment have been installed, you can install `psychopy`, which we will install with `pip` because it is one of those packages that isn't available to install via `conda install` or any channels.

**Note:** You can combine the previous `pip install ...` step on the same line. I've separated them only to emphasis that everything up to this point has been to install the various packages required by `psychopy`, and now we actually install `psychopy`.

```bash
(psychopy) $ pip install psychopy
```

# Install an audio library

To play audio, you need either `pygame` or `pyo`. Installing `pygame` is easiest.

```bash
(psychopy) $ conda install --channel cogsci pygame
```

To install `pyo`, see the page [[Installing pyo|Installing-pyo]].

# Test it out

Now you should be able to run a basic `psychopy` experiment. If you've cloned the "lupyanlab/lab-computer" repo, navigate to the "psychopy-tests/" directory and run the following demo.

```bash
cd ~/path/to/lab-computer/psychopy-tests
python test_psychopy.py
```

**Note:** Cloning the repo requires having `git` installed.
