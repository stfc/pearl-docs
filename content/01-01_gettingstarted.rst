#####################
Accessing the cluster
#####################

To log in to PEARL you must have an SSH key and an SSH client. If you are using either Linux or macOS then you should already have a command line SSH client available to you. If you are using Windows then you will need to install a client program. We recommend `PuTTY <https://www.putty.org/>`_.

You will need to have your private key loaded into an SSH agent. Again, Linux and macOS users should have this already installed. For Windows we recommend `Pageant <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>`_.

For instructions on how to generate an SSH key and load it into an agent please see the section on :doc:`/99-01_ssh_key`.

**********
Logging in 
**********

The primary login node is ``ui.pearl.scd.stfc.ac.uk``. From here you can access your home directory, check the status of the cluster and submit and monitor your jobs.

.. note::

   Please do not run computationally-intensive tasks on the login node as this can affect other users.

You are also able to log on to the dedicated data transfer node ``dtn.pearl.scd.stfc.ac.uk``. This machine is solely for enabling the ingress and egress of data to and from the cluster and for this reason you are not able to submit jobs from here.
