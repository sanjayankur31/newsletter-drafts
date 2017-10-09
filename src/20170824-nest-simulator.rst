NEST simulator
---------------
:author: Ankur Sinha
:status: draft

Overview
=========

NEST_, the Neural Simulation Tool, is a free to use simulator designed to take
advantage of multi-core computers and large clusters. Where simulators such as
NEURON_ and Genesis_ focus on detailed modelling of morphologicaly realistic
individual neurons, NEST_ is optimised for building large scale neural
networks of point neurons. While NEST_ is written in the C++ programming
language, it provides a API that permits users to write their simulations in
the Python programming language. It runs on most Unix-like systems including
MacBooks and BlueGene supercomputers.

Installation
=============

The source code to NEST_ is freely available on the `project's Github
repository <https://github.com/nest/nest-simulator/releases>`__ under the
GPLv2+ license. NEST_ must be compiled from source:

The following tools are required to compile NEST, most of which can be
obtained from various packaging systems or directly from their websites:

- `Cmake <https://cmake.org/>`__
- `Python <https://python.org>`__ (Note that NEST_ supports both versions 2
  and 3 of Python)
- `The GNU C compiler collection <https://gcc.gnu.org/>`__
- `The Boost C++ libraries <http://www.boost.org/>__`
- `An implementation of the MPI protocol <http://mpi-forum.org/>`__ for use on
  clusters/supercomputers - `Open MPI <https://www.open-mpi.org/>`__ and
  `MPICH2 <https://www.mpich.org/>`__ are commonly used.


.. code:: bash

    # In the NEST source code directory
    # Set install path to where NEST will be installed: usually /var/opt/nest/
    $ export INSTALL_PATH=/var/opt/nest
    $ cmake -DCMAKE_INSTALL_PREFIX:PATH=$INSTALL_PATH -Dwith-python:STRING=3 -Dwith-mpi:BOOL=ON
    $ make; sudo make install

After the installation completes, the environment must be updated to point to
the NEST_ installation. The NEST_ developers include a script that does this:

.. code:: bash

    $ source $INSTALL_PATH/bin/nest_vars.sh

On a Linux system using the `bash <https://www.gnu.org/software/bash/>`__
shell, it is often convenient to add the line to the :code:`~/.bashrc` file:

.. code:: bash

    $ echo "source /$INSTALL_PATH/bin/nest_vars.sh" >> ~/.bashrc


The NEST_ installation is then available and can be checked using the Python
interpreter:

.. code:: bash

    $ python3
    Python 3.6.3 (default, Oct  6 2017, 12:22:15)
    [GCC 7.2.1 20170915 (Red Hat 7.2.1-2)] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import nest
    [INFO] [2017.10.9 17:9:15 /home/asinha/Documents/02_Code/00_repos/01_others/nest-simulator/nestkernel/rng_manager.cpp:238 @ Network::create_rngs_] : Creating default RNGs
    [INFO] [2017.10.9 17:9:15 /home/asinha/Documents/02_Code/00_repos/01_others/nest-simulator/nestkernel/rng_manager.cpp:233 @ Network::create_rngs_] : Deleting existing random number generators
    [INFO] [2017.10.9 17:9:15 /home/asinha/Documents/02_Code/00_repos/01_others/nest-simulator/nestkernel/rng_manager.cpp:238 @ Network::create_rngs_] : Creating default RNGs
    [INFO] [2017.10.9 17:9:15 /home/asinha/Documents/02_Code/00_repos/01_others/nest-simulator/nestkernel/rng_manager.cpp:284 @ Network::create_grng_] : Creating new default global RNG

                  -- N E S T --

      Copyright (C) 2004 The NEST Initiative
      Version 2.12.0 Oct  4 2017 17:00:46

    This program is provided AS IS and comes with
    NO WARRANTY. See the file LICENSE for details.

    Problems or suggestions?
      Visit http://www.nest-simulator.org

    Type 'nest.help()' to find out more about NEST.
    >>> nest.version()
    'NEST 2.12.0'
    >>>


Example usage
=============


Troubleshooting and getting help
================================


Show case study
================


A word on the NEST developer community
======================================

NEST_ follows the Open source software development model where most development
occurs on Github_. The development workflow is documented in detail at the
`NEST Developer space <http://nest.github.io/nest-simulator/index>`__ and
includes various topics such as the development workflow, programming
guidelines, and walkthroughs for writing simple extensions. A fortnightly
`Open NEST Developer's video conference
<https://github.com/nest/nest-simulator/wiki/Open-NEST-Developer-Video-Conference>`__
brings developers together to disuss bugs and feature requests. The NEST_
`core development team
<https://github.com/orgs/nest/teams/nest-simulator-developers/members>`__ are
always on the lookout for new contributors to help make NEST_ more useful to
the neuroscience community.


.. _NEST: http://nest-simulator.org/
.. _NEURON: https://www.neuron.yale.edu/neuron/
.. _Genesis: http://www.genesis-sim.org/
.. _Github: https://github.com
