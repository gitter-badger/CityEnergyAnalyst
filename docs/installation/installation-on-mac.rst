:orphan:

Installation guide for Mac
===========================

Follow these instructions to install the CityEnergyAnalyst (CEA) on a Mac system (tested with macOS Mojave 10.14.6) from the source

.. attention:: We advise to follow the above guide precisely:

        *   Be sure to **USE** ``conda env create`` **NOT** ``conda create`` familiar to experienced conda users.
            This command not only creates an environment, but also reads the ``environment.yml`` file, containing a
            list of packages (and versions) to install, as well as a definition of the channels to check.
        *   If you need to create a conda environment for the CEA that has a specific name (the default is ``cea``) then use the
            ``name`` parameter: ``conda env create --name your-env-name-here``


Prerequisites
~~~~~~~~~~~~~

* Download and install `Github Desktop (64-bit) <https://desktop.github.com/>`__.
* Download and install `Miniconda(64-bit) for Python 3.8 <https://conda.io/miniconda.html>`__.
* Download and install `Homebrew <https://brew.sh/>`__.
* Download and install `Xcode <https://developer.apple.com/xcode/>`__.
* Download and install `DAYSIM version >= 4.0 <https://github.com/MITSustainableDesignLab/Daysim#readme>`__.
* For the moment, the user has to manually change `this line <https://github.com/MITSustainableDesignLab/Daysim/blob/76caeb9f682ecb81de08f68db1cff70590b78842/src/daysim/gen_dc.c#L619>` of code in Daysim before compiling it. In this line, change `fclose` to `pclose`.

Installation of the code base
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Excluding the above software, CEA installation requires approximately 13 GB of storage (depending on your existing
Python library) and  1 hour of your time.

#. Open GitHub Desktop from the start menu.
#. Clone the CEA repository:
	#. Press Cmd+Shift+O (clone repository) and select the URL tab.
	#. Paste the CEA GitHub address: https://github.com/architecture-building-systems/CityEnergyAnalyst
	#. Click Clone, this will take ~ 5-10 minutes (Size 1.65 GB).
#. Clone the CEA GUI repository:
	#. Press Cmd+Shift+O (clone repository) and select the URL tab.
	#. Paste the CEA GUI GitHub address: https://github.com/architecture-building-systems/CityEnergyAnalyst-GUI
	#. Click Clone, this will take ~ 5 minutes (Size 600MB).
#. Open a Terminal console.
#. Type ``cd Documents/GitHub/CityEnergyAnalyst`` and press ENTER.
#. Type ``conda env create --name cea --file environment.osx.yml`` and press ENTER.
#. Grab a cup of tea and some toast, this will take ~ 45 minutes.
#. Type ``conda activate cea`` and press ENTER.
#. Type ``pip install --no-deps -e .`` and press ENTER (mind the dot '.' included in this command!).
#. Type ``cd ..`` and press ENTER, then type ``cd CityEnergyAnalyst-GUI`` and press ENTER.
#. Install Yarn by typing ``brew install yarn`` and press ENTER.
#. Type ``yarn`` and press ENTER.
#. Type ``yarn dist:dir`` and press ENTER.
#. Open Finder and go to ``/Users/your_name/Documents/GitHub/CityEnergyAnalyst-GUI/dist/mac``. You will find the CEA application there.

Interfaces
~~~~~~~~~~

There are different ways in which you can interact with the code of CEA.

#. The command line interface: This is the command line to all the commands of CEA from your computer terminal
#. The dashboard: This a web-based interface to CEA, open source and developed by the CEA team.
#. The Pycharm interface: this interface provides access to all the source code of CEA.

While the command line and dashboard interfaces are included during the installation of CEA, the Pycharm interface
requires a few steps to get it up and running.

Pycharm
-------

In order to access and work on the source code of CEA from pycharm do:

#. Download and install `Pycharm Community edition (64-bit) <https://www.jetbrains.com/pycharm/download/#section=windows>`__ OR your own favorite editor.
#. Open PyCharm from the start menu and open project CityEnergyAnalyst (stored where you downloaded CityEnergyAnalyst).
#. Open ``File>Settings>Project:CityEnergyAnalyst>Project Interpreter>Project Interpreter``.
#. Click on the settings button (it looks like a wheel) next to the current interpreter path, and click Add.
#. Click ``Conda Environment`` from the left hand list and select existing environment.
#. Point to the location of your conda environment. It should look something like
   ``Users/your_name/Miniconda2/envs/cea/python.exe`` or
   ``Users/your_name/AppData/Local/conda/conda/envs/cea/python.exe``.
   Where 'your_name' represents your user name in windows.
#. Click apply changes.

