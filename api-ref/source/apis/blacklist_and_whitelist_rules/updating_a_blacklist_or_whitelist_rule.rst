:original_name: waf_02_0040.html

.. _waf_02_0040:

Updating a Blacklist or Whitelist Rule
======================================

Function Description
--------------------

This API is used to update a blacklist or whitelist rule.

URI
---

-  URI format

   PUT /v1/{project_id}/waf/policy/{policy_id}/whiteblackip/{whiteblackip_rule_id}

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

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================+
   | addr            | Yes             | String          | Specifies the public IP address or range (IP address and subnet mask). For example, *X.X.*\ **0.125** or *X.X.*\ **6.0/24**. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------+
   | white           | No              | Integer         | Specifies the IP address type.                                                                                               |
   |                 |                 |                 |                                                                                                                              |
   |                 |                 |                 | -  **1**: **Whitelist**                                                                                                      |
   |                 |                 |                 | -  **0**: **Blacklist**                                                                                                      |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

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
   |                       |                       |                                                                                                                              |
   |                       |                       | If you do not configure the **white** parameter, the value is **Blacklist** by default.                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                  | Specifies the time when a blacklist or whitelist rule is added.                                                              |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+

Examples
--------

*X.X.*\ **0.125** is used as an example.

-  Request example

   .. code-block::

      {
       "addr": "X.X.0.125",
       "white": 1
      }

-  Response example

   .. code-block::

      {
        "id": "44d887434169475794b2717438f7fa78",
        "policy_id": "ertr45c0f96784ec8abd8ba61a98064ef",
        "addr": "X.X.0.125",
        "white": 1,
        "timestamp": 1499817600
      }

Status Code
-----------

:ref:`Table 4 <waf_02_0040__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0040__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
