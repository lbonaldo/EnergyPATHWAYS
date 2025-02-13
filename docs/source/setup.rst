===============
Getting Started
===============

Overview
========

A working EnergyPATHWAYS installation consists of four main parts:

1. EnergyPATHWAYS code
2. csvd python package
3. Excel interface
4. CSV file database

Dependencies
============

EnergyPATHWAYS has been tested with **Python 3.10**. We recommend downloading a specific Anaconda Distribution of python, which can be found here: `<https://repo.anaconda.com/archive/Anaconda3-2023.03-1-Windows-x86_64.exe>`_

.. Note::
   EnergyPATHWAYS has been developed and tested on Microsoft Windows and the interface requires Microsoft Excel for the interface.

Model outputs consist of large csv files that have been designed to work well with `Tableau <https://www.tableau.com/>`_.


Installation
============
EnergyPATHWAYS can be installed using Python's setuptools.

After cloning the EnergyPATHWAYS repository::

    > python setup.py develop

After running the setup script, the excel interface will be able to call the EnergyPATHWAYS model.

.. Note::
   EnergyPATHWAYS requires the csvdb library, which is not currently on PyPI and therefore won't be installed when running the setup script. It can be downloaded here: `<https://github.com/EvolvedEnergyResearch/csvdb>`_

.. topic:: Troubleshooting

    Running setup.py develop will often give permissions errors. To address this, it is recommended that you right click on the command prompt and select the option *Run as administrator*.

    If you encounter an error saying *python: can't open file 'setup.py': [Errno 2] No such file or directory,* check to make sure you are in the correct directory.

Data Setup
==========

In addition to installation of the EnergyPATHWAYS package described above, a model cannot be run until input data are provided. The input data consist of three components:

1. A database describing your energy system
2. A configuration file (e.g. ``config.INI``)
3. A runs_key.csv file that describes the variations of your energy system that you would like to model.

The first two of these are described below, and the third is covered in detail unde

Workspace Organization
===================
You can place EnergyPATHWAYS anywhere you want on your computer. We find that a folder structure similar to what is below makes for a clean workspace for EnergyPATHWAYS.

::

    Some-Date-EP_model
    ├── EnergyPATHWAYS
    │   ├── EnergyPATHWAYS
    │   └── setup.py
    ├── csvdb
    │   ├── numerous folders
    │   └── setup.py
    ├── EP_interface
    │   ├── scenario_builder.py
    │   └── scenario_builder.xlsm
    ├── ep_db
    │   ├── ShapeData
    │   └── numerous csv files
    ├── ep_runs
    │   ├── my_scenario
    │   │   └── config.INI
    │   │   └── runs_key.csv

Running the Model
===================

After installing EnergyPATHWAYS and setting up the necessary input data the model can be run from the command line::

    $ energyPATHWAYS [options]

To get help on the various command line options, use::

    $ energyPATHWAYS --help

In most cases, the user interface, described in :doc:`Interface Section <interface>`, is the best way to interact with the model.