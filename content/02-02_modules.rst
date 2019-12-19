#######################
The Lmod Modules System
#######################

PEARL uses the `Lmod <https://lmod.readthedocs.io/en/latest/>`_ environment modules system to make pre-compiled software available to you. 

.. note::

   The following module paths are automatically added to your environment at logon:

   .. code-block:: console

      /apps/modulefiles/core/

      /apps/modulefiles/eb/

   These give you access to optimised, pre-compiled software and also to the system’s default Singularity build which is loaded be default.

To view all the software that is available to you:

.. code-block:: console

   $ module avail

To list the currently loaded modules:

.. code-block:: console

   $ module list

To load software provided by a module:

.. code-block:: console
   
   $ module load [module_name]

To unload a module:

.. code-block:: console

   $ module unload [module_name]

To substitute one module for another:

.. code-block:: console

   $ module swap [module1_name] [module2_name]

To unload all currently loaded modules and revert to the system default state:

.. code-block:: console

   $ module restore

Lmod also has a tool called ``ml`` which provides the same functionality as the full module command but in a shorter, more convenient format. For instance, listing the currently loaded modules becomes simply:

.. code-block:: console

   $ ml

Showing all available modules can be done with:

.. code-block:: console

   $ ml av
 
You can load a module using:

.. code-block:: console

   $ ml [module_name]

You can unload a module with:

.. code-block:: console

   $ ml –[module_name]

.. seealso::

   Please see the `Lmod User Guide <https://lmod.readthedocs.io/en/latest/010_user.html>`_ for further information.
