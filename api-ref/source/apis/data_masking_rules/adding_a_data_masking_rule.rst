:original_name: waf_02_0055.html

.. _waf_02_0055:

Adding a Data Masking Rule
==========================

Function Description
--------------------

This API is used to add a data masking rule.

URI
---

-  URI format

   POST /v1/{project_id}/waf/policy/{policy_id}/privacy

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      policy_id  Yes       String Specifies the policy ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------+-----------+--------+------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                        |
   +===========+===========+========+====================================================================================+
   | path      | Yes       | String | Specifies the URL to which the data masking rule applies (exact match by default). |
   +-----------+-----------+--------+------------------------------------------------------------------------------------+
   | category  | Yes       | String | Specifies the masked field. The options are **params** and **header**.             |
   +-----------+-----------+--------+------------------------------------------------------------------------------------+
   | index     | Yes       | String | Specifies the masked subfield.                                                     |
   +-----------+-----------+--------+------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

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

Examples
--------

-  Request example

   .. code-block::

      {
        "path": "/login",
        "category": "params",
        "index": "name"
      }

-  Response example

   .. code-block::

      {
            "id": "e1c0e55865544d1f8c95cf71df108c6b",
            "policy_id": "yuc0e55865544d1f8c95cf71df108c6b",
            "path": "/login",
            "category":"params",
            "index": "name",
            "timestamp": 123243414132
      }

Status Code
-----------

:ref:`Table 4 <waf_02_0055__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0055__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
