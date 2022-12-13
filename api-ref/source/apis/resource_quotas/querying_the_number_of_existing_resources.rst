:original_name: waf_02_0010.html

.. _waf_02_0010:

Querying the Number of Existing Resources
=========================================

Function Description
--------------------

This API is used to query the number of existing resources of a user.

URI
---

-  URI format

   GET /v1/{project_id}/waf/bundle/usage/{resource_type}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +---------------+-----------+--------+---------------------------------------------------------------------------------------------+
      | Parameter     | Mandatory | Type   | Description                                                                                 |
      +===============+===========+========+=============================================================================================+
      | project_id    | Yes       | String | Specifies the project ID.                                                                   |
      +---------------+-----------+--------+---------------------------------------------------------------------------------------------+
      | resource_type | Yes       | String | Specifies the resource type. The options are **instance**, **policy**, and **certificate**. |
      +---------------+-----------+--------+---------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   ========= ======= ===========================================
   Parameter Type    Description
   ========= ======= ===========================================
   count     Integer Specifies the number of existing resources.
   ========= ======= ===========================================

Example
-------

The following shows the response if the number of uploaded certificates is queried.

Response example

.. code-block::

   {
      "count": 2
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0010__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0010__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
