***************
Python Packages
***************

.. epigraph::

	"Python is known for it’s **'batteries included'** philosophy and has a rich standard library. However, being a popular language, the number of third party packages is much larger than the number of standard library packages. So it eventually becomes necessary to discover how packages are used, found ..."

	-- `Hitchiker's Guide to Packaging <https://the-hitchhikers-guide-to-packaging.readthedocs.io/en/latest/introduction.html>`_

PyPI
====
The `Python Package Index (PyPI) <http://pypi.python.org>`_, formerly known as the `Cheeseshop <https://wiki.python.org/moin/CheeseShop>`_, is a central repository containing tens of thousands of ready to install Python community projects and distributions.  It will become an integral part of your Python ecosystem.

pip
===
`Pip <https://pip.pypa.io/en/stable/>`_ works with PyPI, it's used to install and manage Python packages. Pip replaces `easy_install <http://peak.telecommunity.com/DevCenter/EasyInstall>`_.

================= ========================
Action            Command
================= ========================
install package   pip install <pkg-name>
uninstall package pip uninstall <pkg-name>
upgrade package   pip install -U <pkg-name>
================= ========================

Pip was installed as part of Python, but now we need to upgrade it to make sure we are using the latest version::

	pip install --upgrade pip

======================= =============================================================
Command                 Action                                                       
======================= =============================================================
pip list                List all packages installed in the current environment.                                  
pip search <text>       List all PyPI packages whose name or summary contains <text>. 
pip show <pkg-name> ... Show information about one or more installed packages.                                      
======================= =============================================================

Go head and practice::

	pip list
	pip search web2py
	pip show pip


Wheels
======
A `Wheel <http://pythonwheels.com/>`_ is python distribution standard that doesn’t require building or complation; wheels replace `eggs <https://packaging.python.org/wheel_egg/>`_ . Wheel has an official `PEP <https://www.python.org/dev/peps/pep-0427/>`_; Egg doesn't.

Use Wheel if you try to install a package from PyPI and you see this ...

.. warning:: error: Unable to find vcvarsall.bat


The package is probably a C extension and it can't find a compiler in Windows.  The easiest way to install these types of packages is to download the Wheel file from the `Unofficial Windows Binaries for Python Extension Packages <http://www.lfd.uci.edu/~gohlke/pythonlibs/>`_.

For example, locate the `pandas <http://pandas.pydata.org/pandas-docs/stable/>`_, a data analysis package.  The Wheel files look something like this::

	pandas-0.18.1-cp27-cp27m-win32.whl

The Wheel file format is is defined in `PEP 425 <https://www.python.org/dev/peps/pep-0425/#use>`_ as::

	{distribution}-{version}(-{build tag})?-{python tag}-{abi tag}-{platform tag}.whl

====  ======================
Abbr  Description
====  ======================
cp    CPython (see below)
win32 Use with 32-bit Python
amd64 Use with 64-bit Python
====  ======================

.. epigraph::

	"When people speak of Python they often mean not just the language but also the CPython implementation. Python is actually a specification for a language that can be implemented in many different ways."

	-- `Official Python Guide <http://docs.python-guide.org/en/latest/starting/which-python/>`_

====================================== =============== ============== ==========
File Name                              Package-Version Python-Version 32/64-bit?
====================================== =============== ============== ==========
pandas-0.18.1-cp27-cp27m-win32.whl     0.18.1          Python 2.7     32-bit 
pandas-0.18.1-cp27-cp27m-win_amd64.whl 0.18.1          Python 2.7     64-bit
pandas-0.18.1-cp35-cp35m-win32.whl     0.18.1          Python 3.5     32-bit
pandas-0.18.1-cp35-cp35m-win_amd64.whl 0.18.1          Python 3.5     64-bit
====================================== =============== ============== ==========

Once you download the correct **Wheel** file for your Python version & architecture you can install it with **pip**::

	pip install <wheel-filename>

Make sure to include the path when you specify the Wheel file, for example::

	pip install c:\users\<username>\downloads\pandas-0.18.1-cp27-cp27m-win32.whl

