# Qudi-plugin for QuOCS

This repo contains the neccessary files to run QuOCS in [Qudi](https://github.com/Ulm-IQO/qudi).

# Installation

1) Install the [QuOCS-pyside2interface](https://github.com/Quantum-OCS/QuOCS-pyside2interface) according to the README in the respective repository. 
Make sure you execute all the commands in the "qudi" conda environment!

2) Copy the folder ```optimalcontrol``` in the directories ```gui_files``` and ```logic_files``` into the ```gui```
and ```logic``` folders of your Qudi installation, respectively.

3) Run Qudi.

4) Select "Load configuration" from the Menu or the icon in the top left corner of the Qudi UI. 
Load the ```qudi_configuration.cfg``` configuration file provided in this repo.
(You can also include the neccessary parts in your custom Qudi configuration 
so that the modules show up in the interface and can be loaded.)

5) Load the "optimalcontrol" GUI in Qudi. 

6) Follow the ```Example_Notebook_Qudi_and_QuOCS.ipynb``` to learn how to use QuOCS and run optimizaitons in Qudi.

---

# Additional Help

## Install the Qudi kernel for Jupyter notebooks

1) Open a terminal in the ```qudi/core``` folder of your Qudi installation.

2) Activate your qudi conda environment
~~~bash
conda activate qudi
~~~

3) Run the installation script via
~~~bash
python qudikernel.py install
~~~

4) The used Qudi configuration file should contain the following entries:

In the global section:
~~~bash
Remote_server:
    address: 'localhost'
    port: 12345
~~~

In the logic section:
~~~bash
kernellogic:
    module.Class: 'jupyterkernel.kernellogic.QudiKernelLogic'
    remoteaccess: True
~~~

Now you can open a Jupyter notebook and select the "Qudi" kernel.