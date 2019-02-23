When collecting data for a `psychopy` experiment, it's desirable to be able to just double click on a .py file to run the experiment. Although on a Windows machine, you can pick which python interpreter to use when double clicking .py files, this approach doesn't work with virtual environments. The way around this is to use .bat files.

Let's say you've got a virtualenv created with Anaconda named "psychopy-sound", and an experiment named "experiment.py". To get "experiment.py" to run in the "psychopy-sound" virtualenv, create a .bat file named something like "experiment.bat" with the following text in it.

```bat
:: contents of experiment.bat
:: Activate the root Anaconda python, then activate the psychopy-sound virtualenv, then run the experiment
%userprofile%\Anaconda2\Scripts\activate & activate psychopy-sound & python experiment.py
```

Now you can double click on experiment.bat to run the python experiment with the correct virtual environment.
