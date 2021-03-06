.. Copyright 2016 FUJITSU LIMITED

.. _machineImage-publish:

machineImage_publish
--------------------

.. function:: POST /users/{uid}/appliances/{aid}/pimages

.. sidebar:: Summary

	* Method: ``POST``
	* Response Code: ``201``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 2.0``

Request to publish (register) a generated machine image to a target cloud environment. 

The response body is a ``publish image ticket`` that provides the meta-data of the published machine image. The actual publication is done asynchronously.  To poll the status of this publication, use :ref:`machineImagePublishedStatus-getAll`. 

This request is similar to :ref:`applianceImage-publish`

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``image_publish``

URI Parameters
~~~~~~~~~~~~~~

* ``uid`` (required): the user name (login name) of the :ref:`user-object`
* ``aid`` (required): the id of the :ref:`appliance-object`

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A :ref:`publishImage-object` object

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/users/{uid}/appliances/{aid}/pimages" -X POST \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml" --data-binary "@representation.xml"

Example of representation.xml content (the request body):

.. code-block:: xml

	<ns0:publishImage>
		<xsi:type></xsi:type>
		<applianceUri>users/root/appliances/4</applianceUri>
		<credAccount>
			<xsi:type></xsi:type>
			<targetPlatform>
				<name>openstack</name>
			</targetPlatform>
			<glanceUrl>http://ip:9292</glanceUrl>
			<keystoneUrl>http://ip:5000</keystoneUrl>
			<login>username</login>
			<password>password</password>
			<keystoneVersion>v3</keystoneVersion>
		</credAccount>
		<imageUri>users/root/appliances/4/images/7</imageUri>
		<keystoneDomain>Keystone Domain Example</keystoneDomain>
		<keystoneProject>Keystone Project Example</keystoneProject>
		<displayName>Machine Image Name Example</displayName>
		<publicImage>true</publicImage>
	</ns0:publishImage>


.. seealso::

	 * :ref:`appliance-object`
	 * :ref:`publishimage-object`
	 * :ref:`machineImage-deleteAll`
	 * :ref:`machineImage-delete`
	 * :ref:`machineImage-download`
	 * :ref:`machineImage-downloadFile`
	 * :ref:`machineImage-generate`
	 * :ref:`machineImage-publish`
	 * :ref:`machineImage-get`
	 * :ref:`machineImage-getAll`
	 * :ref:`machineImage-regenerate`
	 * :ref:`machineImageGeneration-cancel`
	 * :ref:`machineImageStatus-getAll`
	 * :ref:`machineImageStatus-get`
	 * :ref:`machineImagePublish-cancel`
	 * :ref:`machineImagePublished-get`
	 * :ref:`machineImagePublished-getAll`
	 * :ref:`machineImagePublished-delete`
	 * :ref:`machineImagePublished-deleteAll`
	 * :ref:`machineImagePublished-download`
	 * :ref:`machineImagePublishedStatus-get`
	 * :ref:`machineImagePublishedStatus-getAll`
	 * :ref:`machineImage-publish`
