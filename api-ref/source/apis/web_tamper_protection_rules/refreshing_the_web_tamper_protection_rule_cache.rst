:original_name: waf_02_0064.html

.. _waf_02_0064:

Refreshing the Web Tamper Protection Rule Cache
===============================================

Function Description
--------------------

This API is used to refresh cache in a web tamper protection rule in the event of changes on the protected webpage.

URI
---

-  URI format

   POST /v1/{project_id}/waf/policy/{policy_id}/antitamper/{antitamper_rule_id}/cache

-  Parameter description

   .. table:: **Table 1** Path parameters

      +--------------------+-----------+--------+---------------------------------------------------+
      | Parameter          | Mandatory | Type   | Description                                       |
      +====================+===========+========+===================================================+
      | project_id         | Yes       | String | Specifies the project ID.                         |
      +--------------------+-----------+--------+---------------------------------------------------+
      | policy_id          | Yes       | String | Specifies the policy ID.                          |
      +--------------------+-----------+--------+---------------------------------------------------+
      | antitamper_rule_id | Yes       | String | Specifies the ID of a web tamper protection rule. |
      +--------------------+-----------+--------+---------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+--------+-----------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                             |
   +===========+========+=========================================================================================+
   | id        | String | Specifies the ID of a web tamper protection rule.                                       |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | policy_id | String | Specifies the policy ID.                                                                |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | hostname  | String | Specifies the domain name.                                                              |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | path      | String | Specifies the URL protected by the web tamper protection rule, excluding a domain name. |
   +-----------+--------+-----------------------------------------------------------------------------------------+
   | timestamp | Long   | Specifies the time when the cache is refreshed.                                         |
   +-----------+--------+-----------------------------------------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
         "id": "3a9b5c0f96784ec8abd8ba61a98064ef",
         "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
         "hostname": "www.aaa.com",
         "path": "/a",
         "timestamp": 1499817600
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0064__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0064__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
