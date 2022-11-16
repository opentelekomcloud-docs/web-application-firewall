:original_name: waf_02_0054.html

.. _waf_02_0054:

Querying Data Masking Rules
===========================

Function Description
--------------------

This API is used to query all data masking rules in a policy.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/privacy?offset={offset}&limit={limit}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                                         |
      +============+===========+========+=====================================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                                           |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | policy_id  | Yes       | String | Specifies the policy ID.                                                                                                            |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | offset     | No        | Long   | Specifies the number of returned pages. Its value ranges from **0** to **65535**. The default value is **0**.                       |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | limit      | No        | Long   | Specifies the maximum number of records displayed on each page. Its value ranges from **0** to **50**. The default value is **10**. |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+---------------------------------------------------+------------------------------------------+
   | Parameter | Type                                              | Description                              |
   +===========+===================================================+==========================================+
   | total     | Integer                                           | Specifies the total number of rules.     |
   +-----------+---------------------------------------------------+------------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0054__table16394183011019>` | Specifies the data masking rule objects. |
   +-----------+---------------------------------------------------+------------------------------------------+

.. _waf_02_0054__table16394183011019:

.. table:: **Table 3** **items**

   +-----------+--------+------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                        |
   +===========+========+====================================================================================+
   | id        | String | Specifies the ID of a data masking rule.                                           |
   +-----------+--------+------------------------------------------------------------------------------------+
   | policy_id | String | Specifies the policy ID.                                                           |
   +-----------+--------+------------------------------------------------------------------------------------+
   | path      | String | Specifies the URL to which the data masking rule applies (exact match by default). |
   +-----------+--------+------------------------------------------------------------------------------------+
   | category  | String | Specifies the masked field. The options are **params** and **header**.             |
   +-----------+--------+------------------------------------------------------------------------------------+
   | index     | String | Specifies the masked subfield.                                                     |
   +-----------+--------+------------------------------------------------------------------------------------+
   | timestamp | Long   | Specifies the time when a data masking rule is added.                              |
   +-----------+--------+------------------------------------------------------------------------------------+

Example
-------

**total** with a value of **2** is used as an example.

Response example

.. code-block::

   {
     "total": 2,
     "items": [{
         "id": "e1c0e55865544d1f8c95cf71df108c6b",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
         "path": "/login",
         "category": "params",
         "index": "password",
         "timestamp": 123243414132
       }, {
         "id": "d947d31c3e794b70a25e5e2057997f8e",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c89",
         "path": "/register",
         "category": "header",
         "index": "x-auth-token",
         "timestamp": 1343243243123
       }
     ]
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0054__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0054__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
