:original_name: waf_02_0076.html

.. _waf_02_0076:

Querying the Number of Attack Source IP Addresses
=================================================

Function Description
--------------------

This API is used to query the number of attack source IP addresses.

URI
---

-  URI format

   GET /v1/{project_id}/waf/event/attack/source/num?from={from}&to={to}&hosts={hostids}

   .. note::

      An example of a URI is as follows:

      GET /v1/3ac26c59e15a4a11bb680a103a29ddb6/waf/event/attack/type?from=1543976973635&to=1563976973635&hosts=3211757cafa3437aae24d760022e79ba&hosts=93029844064b43739b51ca63036fbc4b&hosts=34fe5f5c60ef4e43a9975296765d1217

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+---------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                     |
      +============+===========+========+=================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                       |
      +------------+-----------+--------+---------------------------------------------------------------------------------+
      | from       | Yes       | Long   | Specifies the start time (UTC) in milliseconds. For example, **1548172800000**. |
      +------------+-----------+--------+---------------------------------------------------------------------------------+
      | to         | Yes       | Long   | Specifies the end time (UTC) in milliseconds. For example, **1548431999000**.   |
      +------------+-----------+--------+---------------------------------------------------------------------------------+
      | hosts      | No        | Array  | Specifies the domain IDs.                                                       |
      +------------+-----------+--------+---------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   ========= ======= ===================================================
   Parameter Type    Description
   ========= ======= ===================================================
   sip       Integer Specifies the number of attack source IP addresses.
   ========= ======= ===================================================

Example
-------

Response example

.. code-block::

   {
     "sip":  50
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0076__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0076__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
