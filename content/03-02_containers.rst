################
Using Containers
################

Container support on PEARL is provided through `Singularity <https://sylabs.io/singularity/>`_. It is an integral part of the cluster, and Singularity commands can be executed natively on any login or compute node without the need to load any additional modules.

Pearl is connected to the `NVIDIA GPU Cloud <https://www.nvidia.com/en-us/gpu-cloud/>`_ which is also known as NGC. This is a catalogue of pre-optimized deep learning framework containers designed to make full use of the DGX-2’s GPUs in both single and multi-GPU configurations.

Please see the `NVIDIA Docker Containers for Deep Learning Frameworks User Guide <https://docs.nvidia.com/deeplearning/frameworks/user-guide/index.html>`_ for more information on running deep learning containers and `Running NGC Containers Using Singularity <https://docs.nvidia.com/ngc/ngc-user-guide/singularity.html>`_ guide for more information.

NGC provides images in Docker format so to run these on PEARL they must first be converted to the Singularity format.

.. note:: 

   PEARL maintains a collection of the most commonly used images from NGC which have already been converted to Singularity format. These can be found here:

   */mnt/beegfs/images/singularity*

If there is an image you would like to be made available then please request this through the PEARL helpdesk.

You are also able to pull down images from NGC and convert them to Singularity format. You will need to set up an NGC account and create an API key first which can be done by following these steps:

1. Create a personal NGC account at https://ngc.nvidia.com/signup

2. Create an NGC API key for access to the NGC container registry. This can be found by selecting ‘SETUP’ from the left-side menu. **Retain a copy of the key for use in the following step**.

3. Log on to ``ui.pearl.scd.stfc.ac.uk`` using your pearlXXX account and set up the Singularity-Docker environment:

.. code-block:: console

   $ export SINGULARITY_DOCKER_USERNAME='$oauthtoken'
   $ export SINGULARITY_DOCKER_PASSWORD=[your_api_key]

4. Request an interactive session with access to a GPU:

.. code-block:: console

   $ srun --gres=gpu:1 --pty /bin/bash

5. Pull a container from NGC and convert it to Singularity format:

.. code-block:: console

   $ singularity build cuda_10.0-base-centos7.sif docker://nvcr.io/nvidia/cuda:10.0-base-centos7

6. Test your container:

.. code-block:: console

   $ singularity exec --nv cuda_10.0-base-centos7.sif cat /etc/redhat-release && nvidia-smi

   CentOS Linux release 7.7.1908 (Core)
   Thu Dec 19 14:00:26 2019
   +-----------------------------------------------------------------------------+
   | NVIDIA-SMI 418.67       Driver Version: 418.67       CUDA Version: 10.1     |
   |-------------------------------+----------------------+----------------------+
   | GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
   | Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
   |===============================+======================+======================|
   |   0  Tesla V100-SXM3...  On   | 00000000:34:00.0 Off |                    0 |
   | N/A   31C    P0    51W / 350W |      0MiB / 32480MiB |      0%      Default |
   +-------------------------------+----------------------+----------------------+

   +-----------------------------------------------------------------------------+
   | Processes:                                                       GPU Memory |
   |  GPU       PID   Type   Process name                             Usage      |
   |=============================================================================|
   |  No running processes found                                                 |
   +-----------------------------------------------------------------------------+

***************************
Building a custom container
***************************

It is possible to build a custom container from scratch but the ability to do so is enabled on a per-user basis. If you would like to be able to do this then please contact us via the PEARL Service Desk.

Custom containers are built from a definition file which is essentially a set of blueprints defining the OS, what software to install, environment variables, etc. At a very minimum the definition file must contain a header section which defines the base operating system that will be used in the container.

The following very simple example pulls docker layers from the Docker Hub, sets Ubuntu as the OS and defines two sections; test and help:

.. code-block:: console

   Bootstrap: docker
   From: Ubuntu

   %test
       grep -q NAME=\"Ubuntu\" /etc/os-release
       if [ $? -eq 0 ]; then
           echo "Container base is Ubuntu as expected."
       else
           echo "Container base is not Ubuntu."
       fi

   %help
   Hello from inside the container!

You can then build your container:

.. code-block:: console

   $ singularity build --fakeroot hello.simg custom-container.def

Then do the following to test the functionality:

.. code-block:: console

   $ singularity test hello.simg
   Container base is Ubuntu as expected.

.. code-block:: console

   $ singularity run-help hello.simg
   Hello from inside the container!

.. seealso::

   For a more detailed explanation of definition files please see the `official Singularity documentation <https://sylabs.io/guides/3.0/user-guide/definition_files.html>`_.
