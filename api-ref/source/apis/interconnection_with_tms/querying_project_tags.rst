:original_name: waf_02_0095.html

.. _waf_02_0095:

Querying Project Tags
=====================

Function Description
--------------------

This API is used to query all resource tags of a tenant in a specified project.

URI
---

-  URI format

   GET /v1/{project_id}/waf/tags

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+-------------------------------------------------+-------------------------+
   | Parameter | Type                                            | Description             |
   +===========+=================================================+=========================+
   | tags      | :ref:`Table 3 <waf_02_0095__table433818302503>` | Specifies the tag list. |
   +-----------+-------------------------------------------------+-------------------------+

.. _waf_02_0095__table433818302503:

.. table:: **Table 3** tags

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                           |
   +=======================+=======================+=======================================================================================+
   | key                   | String                | Specifies the key. It contains a maximum of 36 Unicode characters.                    |
   |                       |                       |                                                                                       |
   |                       |                       | The key value must comply with :ref:`Character Set Specifications <waf_02_0086>`.     |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+
   | values                | List<String>          | Specifies the list of values. Each value contains a maximum of 43 Unicode characters. |
   |                       |                       |                                                                                       |
   |                       |                       | The value must comply with :ref:`Character Set Specifications <waf_02_0086>`.         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
         "tags": [
           {
               "key": "key1",
               "values": [
                   "value1",
                   "value2"
                    ]
           },
           {
               "key": "key2",
               "values": [
                   "value1",
                   "value2"
                    ]
           }
       ]
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0095__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0095__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
