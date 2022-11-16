:original_name: waf_02_0019.html

.. _waf_02_0019:

Obtaining the Certificate List
==============================

Function Description
--------------------

This API is used to obtain the certificate list of a user.

URI
---

-  URI format

   GET /v1/{project_id}/waf/certificate?offset={offset}&limit={limit}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                                                                                                           |
      +============+===========+========+=======================================================================================================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                                                                                                             |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset     | No        | Long   | Specifies the number of returned pages. Its value ranges from **0** to **65535**. The default value is **0**.                                                                                         |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | limit      | No        | Long   | Specifies the maximum number of records displayed on each page. Its value ranges from **0** to **50**. The default value is **10**. If **limit** is **-1**, one page with 65535 records is displayed. |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+---------------------------------------------------+---------------------------------------------+
   | Parameter | Type                                              | Description                                 |
   +===========+===================================================+=============================================+
   | total     | Integer                                           | Specifies the total number of certificates. |
   +-----------+---------------------------------------------------+---------------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0019__table16394183011019>` | Specifies the certificate objects.          |
   +-----------+---------------------------------------------------+---------------------------------------------+

.. _waf_02_0019__table16394183011019:

.. table:: **Table 3** **items**

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

**total** with a value of **2** is used as an example.

Response example

.. code-block::

   {
      "total": 2,
       "items": [
           {
             "id": "388a7789d55b41d1918b3088a8f1e7f3",
             "name": "cert_a",
             "timestamp": 1544756441859,
             "expireTime": 1545978662373
           }, {
             "id": "388a7789d55b41d1918b3088a8f1e7f4",
             "name": "cert_b",
             "timestamp": 1544756441859,
             "expireTime": 1545978662356
           }]
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0019__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0019__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
