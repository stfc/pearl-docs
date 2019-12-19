###################
PEARL Storage Areas
###################

PEARL’s primary storage areas are hosted on two Talyn storage appliances. These provide your *home* directory and and the shared *work* area. Given the nature of the expected workloads quotas are not enforced, but you are expected to manage your data in a responsible way so please give due consideration to other users.

The storage areas are available from all nodes that you can log into directly and they are also accessible from the DGX2 nodes.

The *work* area contains group-specific directories that you have access to depending on your organisational affiliation. You are able to create additional directories here to suit your requirements.

There is also a universally-accessible directory where cluster-wide resources such as container images are stored for your use.

When you log in some environment variables are set to enable you to access the storage areas easily and without having to remember the paths.

.. warning:: Note that for operational reasons **only the home directories are backed up** and this area will be regularly assessed to ensure that user’s data is within reasonable limits. Large data sets should be stored in the *work* area while only data that cannot be easily replaced, such as results, should be stored in *home*. Data will never be deleted without prior consultation with the data owner.

Below is a table summarising the PEARL storage areas: 

+---------------------------------+----------+-------------------------+-----------+
| Path                            | Variable | Description             | Backups   |
+=================================+==========+=========================+===========+
| /mnt/beegfs/home/<username>     | $HOME    | Your home directory     | Nightly   |
+---------------------------------+----------+-------------------------+-----------+
| /mnt/beegfs/work/ati            | $WORK    | ATI shared work area    | No        |
+---------------------------------+----------+-------------------------+-----------+
| /mnt/beegfs/work/stfc           | $WORK    | STFC shared work area   | No        |
+---------------------------------+----------+-------------------------+-----------+
| /mnt/beegfs/images              | $IMAGES  | Shared image repository | No        |
+---------------------------------+----------+-------------------------+-----------+
