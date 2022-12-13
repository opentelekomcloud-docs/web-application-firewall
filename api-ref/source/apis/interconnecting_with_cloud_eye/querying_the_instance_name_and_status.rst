:original_name: waf_02_0097.html

.. _waf_02_0097:

Querying the Instance Name and Status
=====================================

Function Description
--------------------

This API is used to query the name and status of the instance for interconnecting with Cloud Eye.

URI
---

-  URI format

   GET /v1/{project_id}/waf/instance/{instance_id}/metrics

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

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   =============== ====== ===============================================
   Parameter       Type   Description
   =============== ====== ===============================================
   waf_instance_id String Specifies the identifier of a metric dimension.
   name            String Specifies the name of a resource instance.
   status          String Specifies the status of a resource instance.
   =============== ====== ===============================================

Example
-------

Response example

.. code-block::

   {
        "waf_instance_id": "dhbvhdfbvdhbasdkjvfhwoow",
        "name": "www.test.com",
        "status": "enable"
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0097__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0097__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
