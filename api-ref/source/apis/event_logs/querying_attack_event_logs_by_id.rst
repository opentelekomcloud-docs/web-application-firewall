:original_name: waf_02_0071.html

.. _waf_02_0071:

Querying Attack Event Logs by ID
================================

Function Description
--------------------

This API is used to query attack event logs by ID.

URI
---

-  URI format

   GET /v1/{project_id}/waf/event/{event_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      event_id   Yes       String Specifies the event ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                                                                                |
   +=======================+=======================+============================================================================================================================================================================================================================================================+
   | id                    | String                | Specifies the event ID.                                                                                                                                                                                                                                    |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | time                  | Integer               | Specifies the attack time since Unix Epoch in milliseconds.                                                                                                                                                                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | policy_id             | String                | Specifies the policy ID.                                                                                                                                                                                                                                   |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sip                   | String                | Specifies an attack source IP address.                                                                                                                                                                                                                     |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | host                  | String                | Specifies an attacked domain name.                                                                                                                                                                                                                         |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | host_id               | String                | Specifies a domain name ID.                                                                                                                                                                                                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | url                   | String                | Specifies the attacked URL, excluding a domain name.                                                                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | attack                | String                | Specifies the attack type.                                                                                                                                                                                                                                 |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | rule                  | String                | Specifies the ID of the matched rule.                                                                                                                                                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | payload               | String                | Specifies the hit load.                                                                                                                                                                                                                                    |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action                | String                | Specifies the protective action.                                                                                                                                                                                                                           |
   |                       |                       |                                                                                                                                                                                                                                                            |
   |                       |                       | -  **Block**: WAF blocks and logs detected attacks.                                                                                                                                                                                                        |
   |                       |                       | -  **Log only**: WAF logs detected attacks only.                                                                                                                                                                                                           |
   |                       |                       | -  **Allow**: WAF allows the requests that meet the specified conditions.                                                                                                                                                                                  |
   |                       |                       | -  **Verification code**: A verification code is displayed when the number of requests reaches the maximum limit in a CC attack protection rule. Upon completing the verification, you are no longer restricted by the maximum number of requests allowed. |
   |                       |                       | -  **Filter**: WAF implements data masking.                                                                                                                                                                                                                |
   |                       |                       | -  **Mismatch**: The cached web page in the WAF engine does not match the original web page.                                                                                                                                                               |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | payload_location      | String                | Specifies the location in the request packet where the attack occurs. The options are as follows: **body**, **url**, **params**, and **header**.                                                                                                           |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | request_line          | String                | Specifies the attack request method.                                                                                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | headers               | Object                | Specifies the attack request header.                                                                                                                                                                                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cookie                | String                | Specifies the cookie.                                                                                                                                                                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | body                  | String                | Specifies the body of an attack request.                                                                                                                                                                                                                   |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

Event ID **0000-0000-0000-13-56ef71f5745764348192f844658dd144** is used as an example.

Response example

.. code-block::

   {
        "id": "0000-0000-0000-13-56ef71f5745764348192f844658dd144",
         "time": 1499817600,
         "policy_id": "xxx",
         "sip": "X.X.1.1",
         "host": "a.com",
         "host_id": "123",
         "url": "/login",
         "attack": "sqli",
         "rule": "20001",
         "payload": "1 or 1=1",
         "action": "block",
         "payload_location": "params",
         "request_line": "GET / ",
         "headers": {
           "Connection": "keep-alive",
           "User-Agent": "curl"
         },
         "cookie": "sid=123; uid=456",
         "body": "user=admin&pass=abc123"
       }

Status Code
-----------

:ref:`Table 3 <waf_02_0071__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0071__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
