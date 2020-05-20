# Insolar documentation sources

## Install
1. Install the latest Sphinx version: `python3 -m pip install sphinx`
2. Set PATH if you installed it with the `--user` key: `PATH="/Users/<user>/Library/Python/<version>/bin:$PATH"`
3. Install the extensions used in this project: 
   ```
   python3 -m pip install sphinx-tabs
   python3 -m pip install sphinxcontrib.plantuml
   python3 -m pip install sphinx_copybutton 
   python3 -m pip install sphinxcontrib.contentui
   ```
## Build
1. Go to the source files directory: `cd <local-path-to-the-repo>/docs/`
2. Build artifacts: `make html` for HTML artifacts or `make pdf` for PDF artifacts.
