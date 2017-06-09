# sciplat-examples
A place to put example scripts, notebooks and movies for the Science Platform.  Not that the demos may not exactly match the experience on the current JupyterLab deployment as development on this product is extremely rapid.

## Movie links
### [Simple Demo of the Stack on JupyterLab](http://lsst-web.ncsa.illinois.edu/~krughoff/data/Simple%20Stack%20Demo.mov)
To follow along with the movie above, you can use [this notebook](https://gist.githubusercontent.com/SimonKrughoff/2548896169b75946b1c5875611b7e751/raw/dfc26c625831ca84df434af660245c0e5f20e1a7/test.ipynb)
### [User extensions to the python environment](http://lsst-web.ncsa.illinois.edu/~krughoff/data/User%20Packages%20Demo.mov)
This movie requires no extra information to follow along.  Note that to install packages in the shell you will need to use the `--user` switch in the appropriate installer (e.g. `pip` or `setup.py`).  I do not believe `conda` has the notion of a user installed package.
### [Example of interactive visualization from JupyterLab](http://lsst-web.ncsa.illinois.edu/~krughoff/data/Viz%20Demo%202.mov)
This is the most complicated demonstration.  You will need several pieces to execute this demo fully.
#### Notebook
The notebook itself is [here](https://gist.githubusercontent.com/SimonKrughoff/470facb524414e5cd250f9400272dae1/raw/fc625127540d6035b5edc47b358d2a1759a19638/Deblender.ipynb)
You'll also need to get the [analysis](https://github.com/lsst/analysis) package.
#### Remote display
First you'll need a copy of ds9 you can point the remote machine to.  For me, I had to run this on a linux box and forward X to my mac.  You may find this easier than I did.
Next setup ssh on your remote instance.
* In a shell, make a `.ssh` directory in your home directory if you don't have one.  It will need to be created with `700` permissions.
* Go into that directory and put an ssh config file in there.  [Here](https://gist.githubusercontent.com/SimonKrughoff/285d55dd2b14d64c3a49910cc919057f/raw/cfbaa114ae71e946ff695934a4d21ebdcf836185/ssh_config) is an example.  It needs to be called `config` and needs to have `600` permissions.  You will need to change at least the username and remote machine.
#### Setup user packages
First build the analysis package<br>
`$> cd analysis`<br>
`$> source /opt/lsst/software/stack/loadLSST.bash`<br>
`$> scons`<br>
Then setup the launcher configuration.  [Here](https://gist.githubusercontent.com/SimonKrughoff/49b328a785f980f0f96883af7cb1833c/raw/a6eddd057dcbe6b01dc82341b9698bc3763aa41e/.user_setups) is the `.user_setups` I used in the demo.  It needs to be called `.user_setups` and needs to be in your home directory.
