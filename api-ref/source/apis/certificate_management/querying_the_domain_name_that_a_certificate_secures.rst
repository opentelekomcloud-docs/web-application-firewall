:original_name: waf_02_0024.html

.. _waf_02_0024:

Querying the Domain Name that A Certificate Secures
===================================================

Function Description
--------------------

This API is used to query the domain name that a certificate secures.

URI
---

-  URI format

   GET /v1/{project_id}/waf/certificate/{certificate_id}/host

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

   ========= ===== ===========================
   Parameter Type  Description
   ========= ===== ===========================
   hostname  Array Specifies the domain names.
   ========= ===== ===========================

Example
-------

Response example

.. code-block::

   {
       "hostname": ["www.a.com","www.b.com"]
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0024__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0024__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
