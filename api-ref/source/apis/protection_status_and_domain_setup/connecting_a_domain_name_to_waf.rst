:original_name: waf_02_0027.html

.. _waf_02_0027:

Connecting a Domain Name to WAF
===============================

Function Description
--------------------

This API is used to connect a domain name to WAF.

URI
---

-  URI format

   PUT /v1/{project_id}/waf/instance/{instance_id}/access_status

-  Parameter description

   .. table:: **Table 1** Path parameters

      =========== ========= ====== ==========================
      Parameter   Mandatory Type   Description
      =========== ========= ====== ==========================
      projecte_id Yes       String Specifies the project ID.
      instance_id Yes       String Specifies the instance ID.
      =========== ========= ====== ==========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+-----------------+------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                          |
   +=================+=================+=================+======================================================+
   | access_status   | Yes             | Integer         | Specifies whether a domain name is connected to WAF. |
   |                 |                 |                 |                                                      |
   |                 |                 |                 | **1**: The domain name is connected to WAF.          |
   +-----------------+-----------------+-----------------+------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | access_status   | Yes             | Integer         | Specifies whether a domain name is connected to WAF.                                              |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  **1**: The domain name is connected to WAF.                                                    |
   |                 |                 |                 | -  **0**: The domain name is not connected to WAF.                                                |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | protect_status  | Yes             | Integer         | Specifies the WAF mode of a domain name.                                                          |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | -  **1**: enabled.                                                                                |
   |                 |                 |                 | -  **0**: disabled.                                                                               |
   |                 |                 |                 | -  **-1**: bypassed. That is, a client sends a request to the server without passing through WAF. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

Examples
--------

**access_status** with a value of **1** is used as an example.

-  Request example

   .. code-block::

      {
       "access_status": 1
      }

-  Response examples

   The following shows the response if the domain name is connected to WAF:

   .. code-block::

      {
        "access_status": 1,
        "protect_status": 1
      }

   The following shows the response if connection fails:

   .. code-block::

      {
       "access_status": 0,
       "protect_status": 0
      }

Status Code
-----------

:ref:`Table 4 <waf_02_0027__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0027__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
