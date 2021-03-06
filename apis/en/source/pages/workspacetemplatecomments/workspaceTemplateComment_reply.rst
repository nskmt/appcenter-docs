.. Copyright 2016 FUJITSU LIMITED

.. _workspaceTemplateComment-reply:

workspaceTemplateComment_reply
------------------------------

.. function:: POST /orgs/{oid}/workspaces/{wid}/templates/{tid}/comments/{cid}/replies

.. sidebar:: Summary

	* Method: ``POST``
	* Response Code: ``201``
	* Response Formats: ``application/xml`` ``application/json``
	* Since: ``UForge 3.3.2``

Create a reply to a comment. 

Please refer to :ref:`comment-object` for a complete list of all the ``comment`` attributes.

Security Summary
~~~~~~~~~~~~~~~~

* Requires Authentication: ``true``
* Entitlements Required: ``appliance_create``

URI Parameters
~~~~~~~~~~~~~~

* ``wid`` (required): the id of the :ref:`workspace-object`
* ``oid`` (required): the id of the :ref:`org-object`
* ``tid`` (required): the id of the :ref:`gallerytemplate-object`
* ``cid`` (required): the id of the :ref:`comment-object` to reply to

HTTP Request Body Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A :ref:`comment-object` object

Example Request
~~~~~~~~~~~~~~~

.. code-block:: bash

	curl "https://uforge.example.com/api/orgs/{oid}/workspaces/{wid}/templates/{tid}/comments/{cid}/replies" -X POST \
	-u USER_LOGIN:PASSWORD -H "Accept: application/xml" --data-binary "@representation.xml"

Example of representation.xml content (the request body):

.. code-block:: xml

	<ns0:comment>
		<message>Example Reply</message>
		<type>REPLY</type>
	</ns0:comment>


.. seealso::

	 * :ref:`workspace-api-resources`
	 * :ref:`workspacetemplate-api-resources`
	 * :ref:`workspacecomments-api-resources`
	 * :ref:`comment-object`
	 * :ref:`workspaceTemplateComment-create`
	 * :ref:`workspaceTemplateComment-reply`
	 * :ref:`workspaceTemplateComment-getAll`
	 * :ref:`workspaceTemplateComment-get`
	 * :ref:`workspaceTemplateComment-update`
	 * :ref:`workspaceTemplateComment-deleteAll`
	 * :ref:`workspaceTemplateComment-delete`
	 * :ref:`workspaceTemplateComment-reportAbuse`
	 * :ref:`workspaceTemplateComment-like`
	 * :ref:`workspaceTemplateComment-dislike`
