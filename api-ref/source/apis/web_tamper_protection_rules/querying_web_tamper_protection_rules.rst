:original_name: waf_02_0060.html

.. _waf_02_0060:

Querying Web Tamper Protection Rules
====================================

Function Description
--------------------

This API is used to query all web tamper protection rules in a policy.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/antitamper?offset={offset}&&limit={limit}

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

   +-----------+---------------------------------------------------+------------------------------------------------------------------------+
   | Parameter | Type                                              | Description                                                            |
   +===========+===================================================+========================================================================+
   | total     | Integer                                           | Specifies the total number of web tamper protection rules in a policy. |
   +-----------+---------------------------------------------------+------------------------------------------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0060__table16394183011019>` | Specifies the web tamper protection rule objects.                      |
   +-----------+---------------------------------------------------+------------------------------------------------------------------------+

.. _waf_02_0060__table16394183011019:

.. table:: **Table 3** **items**

   +-----------+--------+-----------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                             |
   +===========+========+=========================================================================================+
   | id        | String | Specifies the ID of a web tamper protection rule.                                       |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | policy_id | String | Specifies the ID of the policy to which the rule belongs.                               |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | hostname  | String | Specifies the domain name.                                                              |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | path      | String | Specifies the URL protected by the web tamper protection rule, excluding a domain name. |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | timestamp | Long   | Specifies the time when the cache is refreshed.                                         |
   +-----------+--------+-----------------------------------------------------------------------------------------+

Example
-------

**total** with a value of **2** is used as an example.

Response example

.. code-block::

   {
     "total": 2,
     "items": [{
         "id": "3a9b5c0f96784ec8abd8ba61a98064ef",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
         "hostname": "www.aaa.com",
         "path": "/a",
         "timestamp": 1499817600
       }, {
         "id": "44d887434169475794b2717438f7fa78",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
         "hostname": "www.bbb.com",
         "path": "/b",
         "timestamp": 1499817600
       }
     ]
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0060__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0060__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
