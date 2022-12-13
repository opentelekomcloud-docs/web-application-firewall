:original_name: waf_02_0020.html

.. _waf_02_0020:

Uploading a Certificate
=======================

Function Description
--------------------

This API is used to upload a certificate.

URI
---

-  URI format

   POST /v1/{project_id}/waf/certificate

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                   |
   +=================+=================+=================+===============================================================================================================================================================================================================================+
   | name            | Yes             | String          | Specifies the certificate name. The maximum length is 256 characters. Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                     |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | content         | Yes             | String          | Specifies the certificate content.                                                                                                                                                                                            |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 | .. note::                                                                                                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |    -  The following is an example of the obtained certificate content:                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |       .. code:: text                                                                                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |          -----BEGIN CERTIFICATE-----                                                                                                                                                                                          |
   |                 |                 |                 |          MIIDezCCAmOgAwIBAgIJAMJcdOLsrN3iMA0GCSqGSIb3DQEBCwUAMFQxCzAJBgNV                                                                                                                                                     |
   |                 |                 |                 |          ...                                                                                                                                                                                                                  |
   |                 |                 |                 |          8qh1Vpk2FXoadOVze2fQFLBkkB7LPExj8Nrf76CJEA==                                                                                                                                                                         |
   |                 |                 |                 |          -----END CERTIFICATE-----                                                                                                                                                                                            |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |    -  Line endings are replaced with **\\n** by default before uploading the certificate content. For example:                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |       -----BEGIN CERTIFICATE-----**\\n**\ MIIDezCCAmOgAwIBAgIJAMJcdOLsrN3iMA0GCSqGSIb3DQEBCwUAMFQxCzAJBgNV\ **\\n**...\ **\\n**\ 8qh1Vpk2FXoadOVze2fQFLBkkB7LPExj8Nrf76CJEA==\ **\\n**-----END CERTIFICATE-----               |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | key             | Yes             | String          | Specifies the private key.                                                                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 | .. note::                                                                                                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |    -  The following is an example of the obtained private key:                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |       .. code:: text                                                                                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |          -----BEGIN RSA PRIVATE KEY-----                                                                                                                                                                                      |
   |                 |                 |                 |          MIIEowIBAAKCAQEAsj2QPAwXYcPDH0mvf6Jbej6RGgYlb4EFMS85BjKrKNPOTqZf                                                                                                                                                     |
   |                 |                 |                 |          ...                                                                                                                                                                                                                  |
   |                 |                 |                 |          4j0RY9DeUgSLdy625BBmew2it9l/NynIScG4Ow6w8Bu4iBANGv94                                                                                                                                                                 |
   |                 |                 |                 |          -----END RSA PRIVATE KEY-----                                                                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |    -  Line endings are replaced with **\\n** by default before uploading the private key. For example:                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                                                               |
   |                 |                 |                 |       ----BEGIN RSA PRIVATE KEY----**\\n**\ MIIEowIBAAKCAQEAsj2QPAwXYcPDH0mvf6Jbej6RGgYlb4EFMS85BjKrKNPOTqZf\ **\\n**...\ **\\n**\ 4j0RY9DeUgSLdy625BBmew2it9l/NynIScG4Ow6w8Bu4iBANGv94\ **\\n**-----END RSA PRIVATE KEY----- |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

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
       "name": "cert_a",
       "content": "-----BEGIN CERTIFICATE-----\nMIIDezCCAmOgAwIBAgIJAMJcdOLsrN3iMA0GCSqGSIb3DQEBCwUAMFQxCzAJBgNV\n...\n8qh1Vpk2FXoadOVze2fQFLBkkB7LPExj8Nrf76CJEA==\n-----END CERTIFICATE-----",
       "key": "----BEGIN RSA PRIVATE KEY----\nMIIEowIBAAKCAQEAsj2QPAwXYcPDH0mvf6Jbej6RGgYlb4EFMS85BjKrKNPOTqZf\n...\n4j0RY9DeUgSLdy625BBmew2it9l/NynIScG4Ow6w8Bu4iBANGv94\n-----END RSA PRIVATE KEY-----"
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

:ref:`Table 4 <waf_02_0020__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0020__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
