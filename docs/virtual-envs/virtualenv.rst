********************
Virtual Environments
********************

.. epigraph::
	
	"A Virtual Environment is a tool to keep the dependencies required by different projects in separate places, by creating virtual Python environments for them. It solves the 'Project X depends on version 1.x but, Project Y needs 4.x' dilemma, and keeps your global site-packages directory clean and manageable."

	-- `Hitchiker's Guide to Python, Virtual Environments <http://docs.python-guide.org/en/latest/dev/virtualenvs/>`_

Virtual environments not only help manage package versions, but also ensure the correct version of the Python intepreter is associated with a project.

* `virtualenv <https://virtualenv.pypa.io/en/stable/>`_ is a tool to create these isolated Python environments.
* `virualenvwrapper <https://virtualenvwrapper.readthedocs.io/en/latest/>`_ is a set of extensions to Ian Bicking’s virtualenv tool
  to add the following features:

1. Organize all of your virtual environments in one place.
2. Manage virtual environments (create, delete and list).
3. Allows the use a single command to switch between environments.

* `virtualenvwrapper-win <https://github.com/davidmarble/virtualenvwrapper-win/>`_  is a port of Doug Hellmann's virtualenvwrapper to Windows

Let's install virtualenwrapper-win::

	pip install virtualenvwrapper-win


Virtual Environment Commands
============================

=========================== =====================================================
Command                     Description
=========================== =====================================================
mkvirtualenv <project-name> Create a new virtual environment
lsvirtualenv                List all existing virtual environments
setprojectdir <path>        Associate a project folder with a virtual environment
cdproject                   Change to the project folder
workon <project-name>       Start up a virtual environment 
deactivate                  Shown down the virtual environment
=========================== =====================================================

Virtualenvwrapper-win Environment Variables
===========================================
Default Environment Variables (preset by virtualenvwrapper-win)::

	WORKON_HOME=%USERPROFILE%\Envs
	PROJECT_HOME=%USERPROFILE%\.projects

============ ============================================================
Variable     Description
============ ============================================================
WORKON_HOME  The directory where the virtual environments will be stored.
PROJECT_HOME The project directory associated with a virtualenv.
============ ============================================================

We recommend creating a generic sanbox environment for both Python 2.7 and the latest Python 3 release.  The gives you a environment to play, experiment and learn in, but we suggest creating a separate virtual environment for each Python project that you work with.

Here's how to setup the Python 3.5 sandbox::

	C:\> mkvirtualenv cp35
	C:\> setprojectdir %PROJECT_HOME%\cp35
	C:\> workon cp35

1. This creates new virtual environment we chose to call **cp35** (stands for CPython ver. 3.5)
2. This sets the project directory for the virtual environment.
3. This restarts the virtual environment and moves you into the project directory.

Now let's setup the Python 2.7 sandbox (remember you can use tab completion to avoid typing in the whole name::

	C:\> mkvirtualenv -p c:\python\python27\python.exe
	C:\> setprojectdir %PROJECT_HOME%\cp27
	C:\> workon cp27

.. note::

	Since our default Python Interpreter is 3.5, we need to use the -p option with mkvirtualenv to indicate which interpreter we want to use for the virtual environment.


Summary
=======
When you want to play in CPython 2.7::

	C:\> workon cp25

When you want to switch to CPython 3.5::

	C:\> workon cp35

When you want to exit the virtual environment::

	C:\> deactivate

When you want to create a virtual environment for a new project::

	C:\> mkvirtualenv <name>
	C:\> setprojectdir <path>
	C:\> workon <name>
