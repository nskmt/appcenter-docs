.. Copyright 2016 FUJITSU LIMITED

.. _migration-process-whitebox:

Whitebox Migration Process
--------------------------

The goal of white box migration is to change the contents found during the scan of the live system prior to migration.  To carry out a white box migration, the user must import the scan report as an appliance template. The import process basically transforms the meta-data of the scan report to an appliance template.

.. warning:: White box migration is not supported for Windows.  

As part of this transformation process, the scan information is mapped to one or more of the appliance template layers as follows:

	* Native packages that have been analyzed by the scan process and correctly found in one of UForge AppCenter package repositories are added to the ``OS Profile``.
	* Native packages that have been analyzed by the scan process and NOT found in any of UForge AppCenter's package repositories are added to a ``My Software`` component.
	* All other files (including configuration files) that are not part of a native package are added to a ``My Software`` component.
	* Partitioning table information is added to the ``Install Profile``
	* Root and user passwords are added to the ``Install Profile`` (encrypted)
	* Timezone is added to the ``Install Profile``
	* Keyboard is added to the ``Install Profile``
	* Kernel parameters are added to the ``Install Profile``
	* Users and groups are added to the ``Install Profile``

.. warning:: All other information found in the scan is not used (reset) and the Install Profile default information is used.  This includes:

	* Networking information (IP address).  Furthermore, appliance templates do not support multiple NICs, therefore only the first NIC is taken into consideration.
	* SELinux settings not taken into account – this information is lost
	* SSH keys.  You will need to manually add the ssh keys to the install profile.  

.. warning:: Currently, UForge is not able to migrate the Yum repository GPG keys. This means that the user will have to accept the repository GPG key when the user installs or updates a package. The user will have to do this only once per repository.

.. image:: /images/migration-whitebox-mapping.jpg

Once the scan report has been imported as an appliance template, you can update the content prior to generating a machine image.

The generation process is slightly different between black box and white box migration. UForge is not generating a machine image from a scan report, rather from an appliance template. You can add and remove packages at will from the OS Profile layer.  Consequently package dependencies are calculated using the list of packages in the OS Profile. Any missing packages form the OS Profile are added prior to generating the machine image.  



