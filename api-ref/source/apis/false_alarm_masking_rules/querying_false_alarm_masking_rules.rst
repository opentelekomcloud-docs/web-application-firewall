:original_name: waf_02_0066.html

.. _waf_02_0066:

Querying False Alarm Masking Rules
==================================

Function Description
--------------------

This API is used to query all false alarm masking rules in a policy.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/ignore?path={path}&offset={offset}&limit={limit}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                                         |
      +============+===========+========+=====================================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                                           |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | policy_id  | Yes       | String | Specifies the policy ID.                                                                                                            |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | path       | No        | String | Specifies the misreported URL.                                                                                                      |
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

   +-----------+---------------------------------------------------+-------------------------------------------------+
   | Parameter | Type                                              | Description                                     |
   +===========+===================================================+=================================================+
   | total     | Integer                                           | Specifies the total number of policies.         |
   +-----------+---------------------------------------------------+-------------------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0066__table16394183011019>` | Specifies the false alarm masking rule objects. |
   +-----------+---------------------------------------------------+-------------------------------------------------+

.. _waf_02_0066__table16394183011019:

.. table:: **Table 3** **items**

   +------------+--------+--------------------------------------------------------------------------+
   | Parameter  | Type   | Description                                                              |
   +============+========+==========================================================================+
   | id         | String | Specifies the ID of a false alarm masking rule.                          |
   +------------+--------+--------------------------------------------------------------------------+
   | policy_id  | String | Specifies the policy ID.                                                 |
   +------------+--------+--------------------------------------------------------------------------+
   | path       | String | Specifies a misreported URL excluding a domain name.                     |
   +------------+--------+--------------------------------------------------------------------------+
   | event_id   | String | Specifies the event ID.                                                  |
   +------------+--------+--------------------------------------------------------------------------+
   | event_type | String | Specifies the event type.                                                |
   +------------+--------+--------------------------------------------------------------------------+
   | rule       | String | Specifies the rule ID, which consists of six digits and cannot be empty. |
   +------------+--------+--------------------------------------------------------------------------+
   | timestamp  | Long   | Specifies the time when a false alarm masking rule is added.             |
   +------------+--------+--------------------------------------------------------------------------+

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
         "event_id": "02d3ac3cd99f440daf8d38e03cf0e2a6",
         "event_type": "xss",
         "rule": "100001",
         "timestamp": 1499817600,
         "path": "/a"
       }, {
         "id": "44d887434169475794b2717438f7fa78",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
         "event_id": "f8c74b656a9d4d329dbcefe0969cc427",
         "event_type": "sqli",
         "rule": "100002",
         "timestamp": 1499817600,
         "path": "/a"
       }
     ]
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0066__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0066__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
