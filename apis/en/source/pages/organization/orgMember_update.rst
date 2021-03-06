.. Copyright 2016 FUJITSU LIMITED

.. _orgMember-update:

orgMember_update
----------------

.. function:: PUT /orgs/{oid}/members/{uid}

.. sidebar:: Summary

	* Method: ``PUT``
	* Response Code: ``200``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 3.3``

Adds or updates (the privileges of) an user to an organization.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``org_members_administrate``

URI Parameters
~~~~~~~~~~~~~~

* ``uid`` (required): the user name (login name) of the :ref:`user-object` to add or update
* ``oid`` (required): the id of the :ref:`org-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A :ref:`user-object` object

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/orgs/{oid}/members/{uid}" -X PUT \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml" --data-binary "@representation.xml"

Example of representation.xml content (the request body):

.. code-block:: xml

	<ns0:user>
		<loginName>example</loginName>
		<active>false</active>
	</ns0:user>


.. seealso::

	 * :ref:`org-object`
	 * :ref:`distribprofile-object`
	 * :ref:`user-object`
	 * :ref:`license-object`
	 * :ref:`org-create`
	 * :ref:`org-get`
	 * :ref:`org-getAll`
	 * :ref:`orgOS-add`
	 * :ref:`orgOS-getAll`
	 * :ref:`orgOS-update`
	 * :ref:`orgOSWindows-add`
	 * :ref:`orgOSWindows-getAll`
	 * :ref:`orgMember-remove`
	 * :ref:`orgMember-getAll`
	 * :ref:`orgMember-remove`
	 * :ref:`orgMember-update`
	 * :ref:`orgMember-getAll`
	 * :ref:`orgCompany-getAll`
