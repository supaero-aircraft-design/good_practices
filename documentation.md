# Documentation
## Generating documentation with Sphinx and ReadTheDocs

The file to be copied such-as from FAST-OAD are the following:
- authors.rst
- changelog.rst
- license.rst
- make.bat
- Makefile

They are just relative import of the files from main directory or default configuration / execution files.

The **index.rst** file is the entry point of documentation, but it can include sub-indexes references for example:
`General documentation <documentation/index>`, which can also include sub-indexes...

The **refs.bib** is optional, but it is a good way to cite references within the docstrings.

To obtain the requirements.txt file included in doc, run the following expression in terminal:
`poetry export -f requirements.txt --output requirements.txt --without-hashes`

Be sure that sphinx extensions are added, if necessary add them manually to requirements file:
`sphinx-rtd-theme==0.5.2
sphinx==4.1.2; python_version >= "3.6"
sphinxcontrib-applehelp==1.0.2; python_version >= "3.6"
sphinxcontrib-bibtex==2.3.0; python_version >= "3.6"
sphinxcontrib-devhelp==1.0.2; python_version >= "3.6"
sphinxcontrib-htmlhelp==2.0.0; python_version >= "3.6"
sphinxcontrib-jsmath==1.0.1; python_version >= "3.6"
sphinxcontrib-qthelp==1.0.3; python_version >= "3.6"
sphinxcontrib-serializinghtml==1.1.5; python_version >= "3.6"
`

The **.readthedocs.yml** is the configuration file for the build of the documentation.

The documentation can then be build using following command for a local preview:
- In a terminal, being in `docs` folder, run `make html`
- HTML doc will be available at `./build/sphinx/html/index.html`

To publish it on readthedocs, you shoul import the project to your account (adding the URL of your Github project) and then go to advanced settings:
- Define the requirements file path as: `docs/requirements.txt`
- Define the Python configuration file path as: `docs/conf.py`

Then you should be done.
