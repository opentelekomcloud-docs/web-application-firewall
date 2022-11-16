:original_name: waf_02_0088.html

.. _waf_02_0088:

Querying a False Alarm Masking Rule
===================================

Function Description
--------------------

This API is used to query details about a false alarm masking rule.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/ignore/{ignore_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+-------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                     |
      +============+===========+========+=================================================+
      | project_id | Yes       | String | Specifies the project ID.                       |
      +------------+-----------+--------+-------------------------------------------------+
      | policy_id  | Yes       | String | Specifies the policy ID.                        |
      +------------+-----------+--------+-------------------------------------------------+
      | ignore_id  | Yes       | String | Specifies the ID of a false alarm masking rule. |
      +------------+-----------+--------+-------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

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
   | timestamp  | Long   | Specifies the time when a false alarm masking rule is added.             |
   +------------+--------+--------------------------------------------------------------------------+
   | rule       | String | Specifies the rule ID, which consists of six digits and cannot be empty. |
   +------------+--------+--------------------------------------------------------------------------+

Example
-------

-  Response example

   .. code-block::

      {
        "id": "6cdc116040d444f6b3e1bf1dd629f1d0",
        "policy_id": "44d887434169475794b2717438f7fa78",
        "path": "/a",
        "event_id": "3737fb122f2140f39292f597ad3b7e9a",
        "event_type": "xss",
        "rule": "100001",
        "timestamp": 1499817600
      }

Status Code
-----------

:ref:`Table 3 <waf_02_0088__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0088__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
