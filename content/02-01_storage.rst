###################
PEARL Storage Areas
###################

PEARL’s primary storage areas are hosted on two Talyn storage appliances. These provide your *home* directory and and the *work* area. Given the nature of the expected workloads quotas are not enforced but users are expected to manage their data in a responsible way. Please give due consideration to other users.

The storage areas are available from all nodes that you can log directly into and they are also accessible from the DGX2 nodes.

The *work* area contains group-specific directories that you have access to depending on your organisational affiliation. There is also a generally-accessible directory where cluster-wide resources such as container images are stored for your use.

.. warning:: Note that for operational reasons **only the home directories are backed up** and this area will be regularly assessed to ensure that user’s data is within reasonable limits. Large data sets should be stored in the *work* area while only data that cannot be easily replaced, such as results, should be stored in *home*. No data will be deleted without prior consultation with the data owner however.
