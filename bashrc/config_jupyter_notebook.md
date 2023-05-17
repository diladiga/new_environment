These instructions install Jupyter Notebook with the pip command in a Python virtual environment in your home directory. 
The following instructions are for Python 3.6, but you can also install the application for a different version by loading a different Python module.

Load the Python module.
`[name@server ~]$ module load python/3.7`

Create a new Python virtual environment.
[name@server ~]$ virtualenv $HOME/jupyter_py3

Activate your newly created Python virtual environment.
[name@server ~]$ source $HOME/jupyter_py3/bin/activate

Install Jupyter Notebook in your new virtual environment.
(jupyter_py3)_[name@server ~]$ pip install jupyter

In the virtual environment, create a wrapper script that launches Jupyter Notebook.
(jupyter_py3)_[name@server ~]$ echo -e '#!/bin/bash\nunset XDG_RUNTIME_DIR\njupyter notebook --ip $(hostname -f) --no-browser' > $VIRTUAL_ENV/bin/notebook.sh
 
`this is some code`
 
Finally, make the script executable.
(jupyter_py3)_[name@server ~]$ chmod u+x $VIRTUAL_ENV/bin/notebook.sh

#####################
Installing extensions
Extensions allow you to add functionalities and modify the application’s user interface.

Jupyter Lmod
Jupyter Lmod is an extension that allows you to interact with environment modules before launching kernels. 
The extension uses the Lmod's Python interface to accomplish module-related tasks like loading, unloading, saving a collection, etc.

(jupyter_py3)_[name@server ~]$ pip install jupyterlmod

After the above command I wrote "jupyter nbextension install --py jupyterlmod --sys-prefix" but this appeared: 
ModuleNotFoundError: No module named 'jupyterlmod'

I tried:
module load jupyterlmod

But another error appeared:
Lmod has detected the following error:  The following module(s) are unknown: "jupyterlmod"


(jupyter_py3)_[name@server ~]$ jupyter nbextension install --py jupyterlmod --sys-prefix
(jupyter_py3)_[name@server ~]$ jupyter nbextension enable --py jupyterlmod --sys-prefix
(jupyter_py3)_[name@server ~]$ jupyter serverextension enable --py jupyterlmod --sys-prefix