These instructions install Jupyter Notebook with the pip command in a Python virtual environment in your home directory. 
The following instructions are for Python 3.6, but you can also install the application for a different version by loading a different Python module.

Load the Python module.
`[name@server ~]$ module load python/3.7`

Create a new Python virtual environment.
`[name@server ~]$ virtualenv $HOME/jupyter_py3`

Activate your newly created Python virtual environment.
`[name@server ~]$ source $HOME/jupyter_py3/bin/activate`

Install Jupyter Notebook in your new virtual environment.
`(jupyter_py3)_[name@server ~]$ pip install jupyter`

In the virtual environment, create a wrapper script that launches Jupyter Notebook.
`(jupyter_py3)_[name@server ~]$ echo -e '#!/bin/bash\nunset XDG_RUNTIME_DIR\njupyter notebook --ip $(hostname -f) --no-browser' > $VIRTUAL_ENV/bin/notebook.sh`
 
Finally, make the script executable.
`(jupyter_py3)_[name@server ~]$ chmod u+x $VIRTUAL_ENV/bin/notebook.sh`

### Installing extensions
Extensions allow you to add functionalities and modify the application’s user interface.

#### Jupyter Lmod
I tried to install it but got errors
