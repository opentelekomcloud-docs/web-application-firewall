:original_name: waf_02_0093.html

.. _waf_02_0093:

Adding or Deleting Resource Tags in Batches
===========================================

Function Description
--------------------

This API is used to add or delete tags for a specified resource in batches.

URI
---

-  URI format

   POST /v1/{project_id}/waf/{resource_id}/tags/action

-  Parameter description

   .. table:: **Table 1** Path parameters

      =========== ========= ====== ==========================
      Parameter   Mandatory Type   Description
      =========== ========= ====== ==========================
      project_id  Yes       String Specifies the project ID.
      resource_id Yes       String Specifies the resource ID.
      =========== ========= ====== ==========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------+-----------+---------------------------------------------------+-------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type                                              | Description                                                                                     |
   +===========+===========+===================================================+=================================================================================================+
   | tags      | Yes       | :ref:`Table 3 <waf_02_0093__table77071626145320>` | Specifies the tag list.                                                                         |
   +-----------+-----------+---------------------------------------------------+-------------------------------------------------------------------------------------------------+
   | action    | Yes       | String                                            | Specifies the operation to be performed. The value can be set to **create** or **delete** only. |
   +-----------+-----------+---------------------------------------------------+-------------------------------------------------------------------------------------------------+

.. _waf_02_0093__table77071626145320:

.. table:: **Table 3** tags

   +-----------------+---------------------------------------------------------------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory                                                                       | Type            | Description                                                                                                                                                                                                                                                                                                                                                          |
   +=================+=================================================================================+=================+======================================================================================================================================================================================================================================================================================================================================================================+
   | key             | Yes                                                                             | String          | Specifies the key.                                                                                                                                                                                                                                                                                                                                                   |
   |                 |                                                                                 |                 |                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                                                                                 |                 | It contains a maximum of 36 Unicode characters.                                                                                                                                                                                                                                                                                                                      |
   |                 |                                                                                 |                 |                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                                                                                 |                 | The key value must comply with :ref:`Character Set Specifications <waf_02_0086>`.                                                                                                                                                                                                                                                                                    |
   +-----------------+---------------------------------------------------------------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value           | Mandatory if **action** is **create** and optional if **action** is **delete**. | String          | Specifies the value.                                                                                                                                                                                                                                                                                                                                                 |
   |                 |                                                                                 |                 |                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                                                                                 |                 | Each value contains a maximum of 43 Unicode characters. When tags are being deleted and some tags do not exist, the operation is considered successful by default, and the character set of the tags will not be checked upon deletion. When tags are deleted, the tag structure body cannot be missing, and the key cannot be left blank or set to an empty string. |
   |                 |                                                                                 |                 |                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                                                                                 |                 | The value must comply with :ref:`Character Set Specifications <waf_02_0086>`.                                                                                                                                                                                                                                                                                        |
   +-----------------+---------------------------------------------------------------------------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

None

Example
-------

The following examples describe how to create or delete a tag.

Request example

.. code-block::

   {
       "action": "create",
       "tags": [
           {
               "key": "key1",
               "value": "value1"
           },
           {
               "key": "key",
               "value": "value3"
           }
   ]
   }

or

.. code-block::

   {
       "action": "delete",
       "tags": [
           {
               "key": "key1"
            },
           {
               "key": "key2",
               "value": "value3"
           }
   ]}

Status Code
-----------

:ref:`Table 4 <waf_02_0093__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0093__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   +-------------+-------------+---------------------------------------------------------------------------------+
   | Status Code | Description | Meaning                                                                         |
   +=============+=============+=================================================================================+
   | 204         | No Content  | The server successfully processed the request and is not returning any content. |
   +-------------+-------------+---------------------------------------------------------------------------------+

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
