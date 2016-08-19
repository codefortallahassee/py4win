***********
Quick Start
***********

Step 1: Download & Install Python 2 & 3
=======================================

Python 2.7 (32-bit)
-------------------
1. Click on the following link to download Python 2.7 ...
   https://www.python.org/ftp/python/2.7.12/python-2.7.12.msi
2. Double-click on the downloaded file to install it and use all of the default settings.

Python 3.5 (32-bit)
-------------------
.. attention::

	Mark the **"Install Python 3.5 PATH"** checkbox at the bottom of the first dialog box in the Python 3.5 install wizard. 

1. Click on the following link to download Python 3.5 ...
   https://www.python.org/ftp/python/3.5.2/python-3.5.2.exe
2. Double-click on the downloaded file to install it.  With the exception of the "Install Python 2.5 PATH" checkbox, use all of the default settings.

Step 2: Validate the Default Interpreter
========================================
.. sidebar:: Use Ctrl-z to exit

	Press **[Ctrl]-z** where you see the **^z** symbol to exit out of the Python Interpreter. 

1. Open the command prompt and open the default interpreter::

	C:\> python
	Python 3.5.2 (v3.5.2:4def2a2901a5, Jun 25 2016, 22:01:18) [MSC v.1900 32 bit (Intel)] on win32
	Type "help", "copyright", "credits" or "license" for more information.
	>>> ^z

2. Open the Python 2.7 interpreter::

	C:\> c:\Python27\python.exe
	Python 2.7.12 (v2.7.12:d33e0cf91556, Jun 27 2016, 15:19:22) [MSC v.1500 32 bit (Intel)] on win32
	Type "help", "copyright", "credits" or "license" for more information.
	>>> ^z

Step 3: Install a Virtual Environment Manager
=============================================
1. Install virtualenvwrapper-win ...

.. code:: doscon

	C:\> cd \temp
	C:\> git clone https://github.com/davidmarble/virtualenvwrapper-win.git
	C:\> cd virtualenvwrapper-win	
	C:\> python setup.py install
	C:\> copy scripts\mkproject.bat %USERPROFILE%\AppData\Local\Programs\Python\Python35-32\Scripts
	C:\> notepad %USERPROFILE%\AppData\Local\Programs\Python\Python35-32\Scripts\workon.bat

2. Add the **"doskey workoff=deactivate"** line after "@echo off". 

.. code:: doscon

	@echo off

	doskey workoff=deactivate

	if not defined WORKON_HOME (
	    set "WORKON_HOME=%USERPROFILE%\Envs"
	)

Step 4: Install Interactive Computing Environments
==================================================
Install `IPython <https://ipython.org/>`_ & `Jupyter Notebook <https://jupyter.org/>`_ ...

.. code:: doscon
	
	C:\> pip install jupyter

	C:\> mkvirtualenv -p c:\Python27\python.exe cp27
	C:\> setprojdir c:\%USERNAME%\projects\cp27
	C:\> workon cp27
	C:\> pip install jupyter

	C:\> mkproject cp35

Step 5: Install a Version Control System
========================================
.. note:: Download will start automatically once you click on the link
	
1. Click on the following link to download `Git <https://git-scm.com/>`_ ...
   https://git-scm.com/download/win
2. Double-click on the downloaded file to install it and use all of the default settings.

Step 6: Install Unix Utilities
==============================
1. Click on the following link to download `UnxUtils <http://unxutils.sourceforge.net/>`_ ...
   https://sourceforge.net/projects/unxutils/files/latest/download
2. Click on the downloaded file to open it.
3. Right-click anywhere in the whitespace on right pane of file explorer and select **"Extract All"**.
4. When setting the destination folder browse to **"C:\Program Files (x86)"**.
5. Press **[Win]-s** then type **"env"**
6. Select **"Edit the System Environment Variables: Control Panel"**
7. Click on the **"Environment Variables"** button
8. Click on the **"Path"** variable under **"System Variables"**
9. Click on the **"Edit"** button
10. Click on the **"New"** button
11. Type **"C:\Program Files (x86)\UnxUtils\usr\local\wbin"** and press [Enter]
12. Click the **"Move Up"** button until it is above **"%SystemRoot%\system32"**
13. Verify the **sort** command is the one that comes with *unxutils* by typing the following ...

.. code:: doscon

	C:\>whereis sort
	C:\Program Files (x86)\UnxUtils\usr\local\wbin\sort.exe


Step 7: Install a Regular Expression Debugger
=============================================
1. Click on the following link to download `Kodos <http://kodos.sourceforge.net/>`_ ...
   https://sourceforge.net/projects/kodos/files/latest/download?source=files
2. Double-click on the downloaded file to install it and use all of the default settings.

Step 8: Install a Tool for Getting & Sending Files using URL Syntax
===================================================================
1. Click on the following link to download `cURL <https://curl.haxx.se/>`_ ...
   http://www.confusedbycode.com/curl/#downloads
2. Check the **"I am not a robot"** checkbox.
3. Click on the **curl-7.46.0-win32.exe** button on the **"Administrator Privileges (free)** row.
4. Double-click on the downloaded file to install it and use all of the default settings.

Step 9: Install a Code & Markup Editor
======================================
1. Click on the following link to download Python 2.7 ...
   https://download.sublimetext.com/Sublime%20Text%20Build%203114%20Setup.exe
2. Double-click on the downloaded file to install it.
3. Set the destination directory to ...

.. code:: doscon

	c:\Program Files (x86)\Sublime Text 3

3. Press and release the **[Win]** key and righ-click on the on the **"Sublime Text 3"** icon and select **"More"** then **"Pin to Taskbar"**.  Click on the new icon on your taskbar (brown square with an orange "S" in the middle).
4. From  the menu at the top select "View" --> "Show Console".
5. Click in the console at the bottom of the screen and paste in the following code and press [Enter]

.. code:: python

	import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

6. From  the menu select **"Preferences"** --> **"Package Control"**
7. Press **"i"** [Enter] to **"Install Package"**
8. Type **"flake8"** and select **"Python Flake8 Lint"**
9. From  the menu select **"Preferences"** --> **"Package Control"**
10. Press **"i"** [Enter] to **"Install Package"**
11. Type **"rest"** and select **"RestructuredText Improved"**
12. From  the menu select **"Preferences"** --> **"Package Control"**
13. Press **"i"** [Enter] to **"Install Package"**
14. Type **"sidebar"** and select **"SideBarEnhancements"**
15. From the menu select **"File"** --> **"New File"**
16. Press **[Ctrl]-s** to **"Save As"**
17. Type **"temp.py"**
18. From the menu select **"Preferences"** --> **"Settings - More"** --> **"Syntax Specific - User"**
19. Copy & Paste the text below into the main editor window

.. code:: json 

    {
        "rulers": [72, 79],
        "translate_tabs_to_spaces": true,
        "draw_white_space_all": "all",
        "tab_size": 4
    }

17. Press **[Ctrl]-f** then **s** to save the changes.
18. Press **[Ctrl]-w** to close the window.
19. If you have administrator right to your machine ...
    Right-click **[Windows Start]** and select **"Command Prompt - Admin"**
    Click the **"Yes"** button on the **"Do you want to allow this application to make changes to your PC?"**
    Copy and paste the following into the command prompt ...

.. attention::

	If you installed Sublime Text 3 somewhere other than "C:\Program Files (x86)\Sublime Text 3" then modify the SET statement below accordingly.

.. code:: batch

	@echo off
	SET st3Path=C:\Program Files (x86)\Sublime Text 3\sublime_text.exe
	 
	rem add it for all file types
	@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3"         /t REG_SZ /v "" /d "Edit with Sublime Text 3"   /f
	@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3"         /t REG_EXPAND_SZ /v "Icon" /d "%st3Path%,0" /f
	@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3\command" /t REG_SZ /v "" /d "%st3Path% \"%1\"" /f
	 
	rem add it for folders
	@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3"         /t REG_SZ /v "" /d "Edit with Sublime Text 3"   /f
	@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3"         /t REG_EXPAND_SZ /v "Icon" /d "%st3Path%,0" /f
	@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3\command" /t REG_SZ /v "" /d "%st3Path% \"%1\"" /f

 20. Close the Command window.

Congratulations!
================
You're Windows 10 Python ecosystem is ready to rumble.
