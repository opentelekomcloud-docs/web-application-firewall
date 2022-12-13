:original_name: waf_02_0022.html

.. _waf_02_0022:

Changing the Name of a Certificate
==================================

Function Description
--------------------

This API is used to change the name of a certificate.

URI
---

-  URI format

   PUT /v1/{project_id}/waf/certificate/{certificate_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      ============== ========= ====== =============================
      Parameter      Mandatory Type   Description
      ============== ========= ====== =============================
      project_id     Yes       String Specifies the project ID.
      certificate_id Yes       String Specifies the certificate ID.
      ============== ========= ====== =============================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                               |
   +===========+===========+========+===========================================================================================================================================+
   | name      | Yes       | String | Specifies the certificate name. The maximum length is 256 characters. Only digits, letters, underscores (_), and hyphens (-) are allowed. |
   +-----------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

   ========== ====== ====================================================
   Parameter  Type   Description
   ========== ====== ====================================================
   id         String Specifies the certificate ID.
   name       String Specifies the certificate name.
   expireTime Long   Specifies the time when the certificate expires.
   timestamp  Long   Specifies the time when the certificate is uploaded.
   ========== ====== ====================================================

Examples
--------

A certificate named **cert_a** is used as an example.

-  Request example

   .. code-block::

      {
       "name": "cert_b"
      }

-  Response example

   .. code-block::

      {
          "id": "388a7789d55b41d1918b3088a8f1e7f3",
          "name": "cert_b",
          "expireTime": 1565467166765,
          "timestamp": 1545467166765
      }

Status Code
-----------

:ref:`Table 4 <waf_02_0022__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0022__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
