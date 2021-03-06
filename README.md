prosumpy - Energy prosumer analysis toolkit for python
=================================================================
 ![Python version](https://img.shields.io/badge/python-2.7,%203.6-blue.svg) [![License](https://img.shields.io/badge/License-EUPL--1.1-blue.svg)](https://opensource.org/licenses/EUPL-1.1)  [![Build status](https://travis-ci.org/energy-modelling-toolkit/prosumpy.svg?branch=master)](https://travis-ci.org/energy-modelling-toolkit/prosumpy)



### Model Description
A toolkit for the simulation and economic evaluation of self-consumption and solar home battery systems.
The code is written in Python.

A photovoltaic and storage (battery) system is consider as a means to cover the needs of an end user. The model contains the logic to dispatch the energy based on given conditions and rules for the following energy flow chart:

![Energy flows](https://github.com/energy-modelling-toolkit/prosumpy/blob/master/docs/_static/pv_flows.png)

The energy flows names correspond to the variable names estimated by the model. The grey circles correspond to the meters found in such installations. These meters are used to implement different pricing policies:
1. Feed in Tarriff or Power Purchase Agreement meter
2. (a+b) Bidirectional standard meter

### Dispatch strategies

Currently two dispatch strategies are implemented:
1. `dispatch_max_sc()`: Maximize self consumption
2. `dispatch_max_sc_grid_pf()`: Maximize self consumption in a grid-friendly way by deferring the storage to peak hours. A perfect forecast is assumed.

The dispatch algorithms are tested for their consistency with a unit testing framework ensuring the node balance consistency.

## Quick start
An [example notebook](https://github.com/energy-modelling-toolkit/prosumpy/blob/master/notebooks/Basic%20example.ipynb) has been added to demonstrate the usage of this library.

The easiest way to install all prerequisites of this package is to have the anaconda distribution  [anaconda distribution](https://www.continuum.io/downloads)
installed. If you want to use and edit this package then it is recommended to create a separate environment:

```bash
git clone https://github.com/energy-modelling-toolkit/prosumpy.git
cd prosumpy
conda env create  # Automatically creates environment based on environment.yml
source activate prosumpy # for windows: activate prosumpy
pip install -e . # Install editable local version
pytest # Run the tests and ensure that there are no errors
```


## References
This toolkit has been used in the following paper:

Quoilin, S., Kavvadias, K., Mercier, A., Pappone, I., Zucker, A., 'Quantifying self-consumption linked to solar home battery systems: Statistical analysis and economic assessment', Applied Energy, Elsevier, 2016, 182, pp. 58-67

