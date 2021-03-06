.. Copyright 2016 FUJITSU LIMITED

.. _scanInstance-create:

scanInstance_create
-------------------

.. function:: POST /users/{uid}/scannedinstances

.. sidebar:: Summary

	* Method: ``POST``
	* Response Code: ``201``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 3.4``

Creates a scanned instance. 

A ``scanned instance`` is an object representing a live running instance (physical machine, VM, container). Each time the system is scanned, the scan report is stored under the ``scanned instance`` object. 

Please refer to :ref:`scannedinstance-object` for a complete list of all the ``scanned instance`` attributes.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``migration_access``

URI Parameters
~~~~~~~~~~~~~~

* ``uid`` (required): the user name (login name) of the :ref:`user-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A :ref:`scannedInstance-object` object

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/users/{uid}/scannedinstances" -X POST \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml" --data-binary "@representation.xml"

Example of representation.xml content (the request body):

.. code-block:: xml

	<ns0:scannedInstance>
		<name>Example Scan</name>
		<distribution>
			<name>CentOS</name>
			<version>6.7</version>
			<arch>x86_64</arch>
		</distribution>
	</ns0:scannedInstance>


.. seealso::

	 * :ref:`scannedinstance-object`
	 * :ref:`scan-object`
	 * :ref:`machinescan-api-resources`
	 * :ref:`scannedInstanceScan-getAll`
	 * :ref:`scanInstance-getAll`
	 * :ref:`scanInstance-get`
	 * :ref:`scanInstance-deleteAll`
	 * :ref:`scanInstance-delete`
