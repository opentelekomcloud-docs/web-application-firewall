:original_name: waf_02_0039.html

.. _waf_02_0039:

Querying a Blacklist or Whitelist Rule
======================================

Function Description
--------------------

This API is used to query a blacklist or whitelist rule.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/whiteblackip/{whiteblackip_rule_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +----------------------+-----------+--------+----------------------------------------------------+
      | Parameter            | Mandatory | Type   | Description                                        |
      +======================+===========+========+====================================================+
      | project_id           | Yes       | String | Specifies the project ID.                          |
      +----------------------+-----------+--------+----------------------------------------------------+
      | policy_id            | Yes       | String | Specifies the policy ID.                           |
      +----------------------+-----------+--------+----------------------------------------------------+
      | whiteblackip_rule_id | Yes       | String | Specifies the ID of a blacklist or whitelist rule. |
      +----------------------+-----------+--------+----------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                  |
   +=======================+=======================+==============================================================================================================================+
   | id                    | String                | Specifies the ID of a blacklist or whitelist rule.                                                                           |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | policy_id             | String                | Specifies the policy ID.                                                                                                     |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | addr                  | String                | Specifies the public IP address or range (IP address and subnet mask). For example, *X.X.*\ **0.125** or *X.X.*\ **6.0/24**. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | white                 | Integer               | Specifies the IP address type.                                                                                               |
   |                       |                       |                                                                                                                              |
   |                       |                       | -  **1**: **Whitelist**                                                                                                      |
   |                       |                       | -  **0**: **Blacklist**                                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                  | Specifies the time when a blacklist or whitelist rule is added.                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+

Example
-------

*X.X.*\ **0.125** is used as an example.

Response example

.. code-block::

   {
     "id": "44d887434169475794b2717438f7fa78",
     "policy_id": "ertr45c0f96784ec8abd8ba61a98064ef",
     "addr": "X.X.0.125",
     "white": 0,
     "timestamp": 1499817600
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0039__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0039__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
