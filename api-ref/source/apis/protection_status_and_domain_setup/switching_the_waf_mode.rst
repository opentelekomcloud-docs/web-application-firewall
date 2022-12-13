:original_name: waf_02_0026.html

.. _waf_02_0026:

Switching the WAF Mode
======================

Function Description
--------------------

This API is used to switch the WAF mode.

URI
---

-  URI format

   PUT /v1/{project_id}/waf/instance/{instance_id}/protect_status

-  Parameter description

   .. table:: **Table 1** Path parameters

      =========== ========= ====== ==========================
      Parameter   Mandatory Type   Description
      =========== ========= ====== ==========================
      project_id  Yes       String Specifies the project ID.
      instance_id Yes       String Specifies the instance ID.
      =========== ========= ====== ==========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | protect_status  | Yes             | Integer         | Specifies the WAF mode of a domain name.                                                          |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  **1**: enabled.                                                                                |
   |                 |                 |                 | -  **0**: disabled.                                                                               |
   |                 |                 |                 | -  **-1**: bypassed. That is, a client sends a request to the server without passing through WAF. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | protect_status  | Yes             | Integer         | Specifies the WAF mode of a domain name.                                                          |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  **1**: enabled.                                                                                |
   |                 |                 |                 | -  **0**: disabled.                                                                               |
   |                 |                 |                 | -  **-1**: bypassed. That is, a client sends a request to the server without passing through WAF. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

Examples
--------

**protect_status** with a value of **1** is used as an example.

-  Request example

   .. code-block::

      {
          "protect_status": 1
      }

-  Response example

   .. code-block::

      {
          "protect_status": 1
      }

Status Code
-----------

:ref:`Table 4 <waf_02_0026__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0026__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
