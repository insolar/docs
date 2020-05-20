# Insolar documentation sources

##I nstall
1. Install latest version of Sphinx: `python3 -m pip install --user sphinx`
2. Set PATH if needed: `PATH="/Users/<user>/Library/Python/<version>/bin:$PATH"`
3. Install the extensions used in this project: 
   ```
   python3 -m pip install sphinx-tabs
   python3 -m pip install sphinxcontrib.plantuml
   python3 -m pip install sphinx_copybutton 
   python3 -m pip install sphinxcontrib.contentui
   ```
## Build
1. Go to the repo directory: `cd <local-path-to-the-repo>/docs/`
2. Build artifacts: `make html` for HTML artifacts or `make pdf` for PDF artifacts.
