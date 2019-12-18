#####################
Accessing the cluster
#####################

Access to the cluster is via ssh. If you are using either Linux or macOS then you will already have a command line client available to you. If you are using Windows then you will need to install a client program, the most commonly used being `PuTTY <https://www.putty.org/>`_.

PEARL only supports ssh keys as for authentication and you will need to have the key loaded into an ssh agent. The PuTTY agent is called Pageant and instructions for loading your key can be found `here <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>`_.

**********
Logging in 
**********

The primary login node is ``ui.pearl.scd.stfc.ac.uk``. From here you can access your home directory, check the status of the cluster and submit and monitor your jobs.

.. note::

   Please do not run computationally-intensive tasks on the head node as it can cause problems for other users.

You are also able to log on to the dedicated data transfer node which is ``dtn.pearl.scd.stfc.ac.uk``. This machine is solely for enabling the ingress and egress of data to and from the cluster and for this reason you are not able to submit jobs from here.
