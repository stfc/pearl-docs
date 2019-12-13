###################
Compiling Your Code
###################

Any compilation that you wish to do should only be done on the compute nodes by requesting an interactive job from the SLURM scheduler. This is done using the command:

.. code-block:: console

   $ srun --pty /bin/bash

The system default compiler is gcc 7.4.0 which is available to you without having to load any additional modules. Newer versions of GCC are available and these can be viewed by issuing the following command:

.. code-block:: console

   $ ml av gcc
