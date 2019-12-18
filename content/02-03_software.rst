##################
Available Software
##################

*********************
Software repositories
*********************

PEARL's applications and libraries are generally provided using the `Easybuild <https://easybuild.readthedocs.io/en/latest/>`_ software build and installation framework. This widely-used tool has been developed specifically to build and manage software on HPC systems. Packages provided this way do not rely on system software as all dependencies are compiled from source as required.

.. note::

   Software which has been installed with Easybuild can be distinguished by this module path:

   .. code-block:: console

      /apps/modulefiles/eb/all

Easybuild uses the concept of toolchains. A toolchain may just consist of a specific version of a compiler but usually adds one or more common HPC libraries such as MPI or numerical routines. This approach provides consistency and avoids many of the problems that can occur when using shared libraries.

Not all software is suitable for distribution using Easybuild and some packages are compiled from source manually. An example of this is the Singularity containers application and this is reflected in the module path:

.. code-block:: console

   /apps/modulefiles/core/singularity/3.4.0-1

Software may also be provided from the Ubuntu repository but this generally provides older versions of packages and so is avoided unless absolutely necessary.

********************
Location of binaries
********************

The location of the actual binaries differs depending on what machine you are logged into. This has been done to ensure that software is optimised for the DGX-2’s more recent processor generation but can also be accessed from the head node. In normal use, this should be completely transparent to you and is only mentioned in this documentation for completeness. You may however see either of the following paths:

.. code-block:: console

   /mnt/beegfs/apps/eb/arch/generic/software/

   /mnt/beegfs/apps/eb/arch/skylake/software/

Software will be added over time but a minimal software stack was made available at service launch. This consists of a recent version of the Singularity containers application, git, Python (plus several common modules) and recent versions of the GCC and Intel compilers. Any requests for specific software to be installed should be made to the PEARL service desk.
