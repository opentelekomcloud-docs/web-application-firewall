:original_name: waf_02_0021.html

.. _waf_02_0021:

Querying a Certificate
======================

Function Description
--------------------

This API is used to query information about a certificate.

URI
---

-  URI format

   GET /v1/{project_id}/waf/certificate/{certificate_id}

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

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   ========== ====== ====================================================
   Parameter  Type   Description
   ========== ====== ====================================================
   id         String Specifies the certificate ID.
   name       String Specifies the certificate name.
   expireTime Long   Specifies the time when the certificate expires.
   timestamp  Long   Specifies the time when the certificate is uploaded.
   ========== ====== ====================================================

Example
-------

A certificate named **cert_b** is used as an example.

Response example

.. code-block::

   {
       "id": "388a7789d55b41d1918b3088a8f1e7f3",
       "name": "cert_b",
       "timestamp": 1545467166765,
       "expireTime": 1555467166765
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0021__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0021__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
