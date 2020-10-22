# How to Update the [WEC-Sim Website](http://wec-sim.github.io/WEC-Sim)

## Download/Install Required Packages
### Step 1. Download and Install Python 
  - Windows: Download and Install Python3 using [Anaconda](https://www.anaconda.com/distribution/). When installing Anaconda select the option to add Python to your environmental vairables. Follow [these instructions](https://docs.anaconda.com/anaconda/user-guide/tasks/proxy/) for using Anaconda behind a company proxy.
 
### Step 2. Add Python to System Path 
  - Windows: Skip to Step 3 if option selected when installing Anaconda, otherwise modify the PATH in environmental variables to include: C:\PYTHON;C:\PYTHON\Scripts 
  ([more info here](http://stackoverflow.com/questions/3701646/how-to-add-to-the-pythonpath-in-windows-7)).
  - MAC/LINUX: Skip to Step 3, Python is already added to path
  
### Step 3. Download/Install [Sphinx](http://www.sphinx-doc.org/en/stable/index.html) and Sphinx extensions
  - Install Sphinx ``pip install -U Sphinx`` 
    ([more info here](http://www.sphinx-doc.org/en/master/usage/installation.html))
  - Install rtd theme ``pip install -U sphinx_rtd_theme``
  - Install BibTex ``pip install -U sphinxcontrib-bibtex``
  - Install matlabdomain ``pip install -U sphinxcontrib-matlabdomain``
  

## Update the [WEC-Sim Website](http://wec-sim.github.io/WEC-Sim) Content
The WEC-Sim documentation located on the [gh-pages branch](https://github.com/WEC-Sim/WEC-Sim/tree/gh-pages), referred to as ``<GH-PAGES>``. The WEC-Sim Website is developed as restructured text files `*.rst` that are compiled by [Sphinx](http://www.sphinx-doc.org/en/master/) into html files. To edit the WEC-Sim Website, modify the restructured text files `*.rst` files located in the ``<GH-PAGES>/source`` directory. Syntax for restructured text files `*.rst` is described on the [Sphinx Website](http://www.sphinx-doc.org/en/master/). 
Once you are done editing, cd to your local ``$GH-PAGES`` directory from cmd, clean the previous compile with ``clean html``, and compile the updated the documentation with``make html``. This compiles an html version of the website in ``<GH-PAGES>/``. After compiling the updated website, you can view the local copy of the website by opening the ``<GH-PAGES>/index.html`` file from your local directory, and viewing it in a web browser (before pushing it online). 


## Push the [WEC-Sim Website](http://wec-sim.github.io/WEC-Sim) Updates to GH-PAGES
Using GitHub, gh-pages renders the documentation on the ([gh-pages branch](https://github.com/WEC-Sim/WEC-Sim/tree/gh-pages)) as the [WEC-Sim Website](http://wec-sim.github.io/WEC-Sim). The user then pushes changes in the html documentation directly to the [gh-pages branch](https://github.com/WEC-Sim/WEC-Sim/tree/gh-pages). Here are the steps to do this:

  ```Shell
  # Move to the local gh-page directory in cmd
  cd <GH-PAGES>

  # Clean and build the html documentation in cmd
  make clean
  make html

  # Use Git-shell to check status of the gh-pages branch, then commit and push changes. 
  git status
  git add -A
  git commit -m 'update to WEC-Sim documentation'
  git push
  ```
  
  ### Best Practices
  - Run spell check (not built into most text editors)
  - When compiling the website, ``make clean`` and then ``make html``

### Formatting Guidelines
  - `$CASE` to refer to WEC-Sim case directory
  - `$WECSIM` to refer to WEC-Sim directory
  - `$WECSIM/source` to refer to WEC-Sim source directory
  - `*.mat` syntax to refer to file extension
  - use ``insert code`` to reference code
  - Title `####` with overline
  - Heading 1 `======`
  - Heading 2 `------`
  - Heading 3 `^^^^^^`
  - Heading 4 `""""""`
  - Heading 5 `++++++`
  - Use this style guide: https://documentation-style-guide-sphinx.readthedocs.io/en/latest/style-guide.html

### Terminology Guidelines
  - post-processing (not postprocessing)
  - pre-processing (not preprocessing)  
  - nondimensional (not non-dimensional)
  - nonlinear (not non-linear)
  - drivetrain (not drive-train)

