:original_name: waf_02_0073.html

.. _waf_02_0073:

Querying Request Statistics and Attack Statistics in a Specified Time Range
===========================================================================

Function Description
--------------------

This API is used to query request statistics and attack statistics in a specified time range.

URI
---

-  URI format

   GET /v1/{project_id}/waf/event/timeline?from={from}&to={to}&timezone={timezone}&hosts={hostids}

   .. note::

      An example of a URI is as follows:

      GET /v1/3ac26c59e15a4a11bb680a103a29ddb6/waf/event/attack/type?from=1543976973635&to=1563976973635&hosts=3211757cafa3437aae24d760022e79ba&hosts=93029844064b43739b51ca63036fbc4b&hosts=34fe5f5c60ef4e43a9975296765d1217

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+----------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                  |
      +============+===========+========+==============================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                    |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------+
      | from       | Yes       | Long   | Specifies the start time (UTC) in milliseconds. For example, **1548172800000**.              |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------+
      | to         | Yes       | Long   | Specifies the end time (UTC) in milliseconds. For example, **1548431999000**.                |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------+
      | timezone   | No        | String | Time zone. For example, the time zone for London is +00:00. The default value is **+00:00**. |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------+
      | hosts      | No        | Array  | Specifies the domain IDs.                                                                    |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+--------------------------------------------------+-------------------------------+
   | Parameter | Type                                             | Description                   |
   +===========+==================================================+===============================+
   | requests  | :ref:`Table 3 <waf_02_0073__table1864743120361>` | Specifies request statistics. |
   +-----------+--------------------------------------------------+-------------------------------+
   | attacks   | :ref:`Table 4 <waf_02_0073__table1441245463618>` | Specifies attack statistics.  |
   +-----------+--------------------------------------------------+-------------------------------+

.. _waf_02_0073__table1864743120361:

.. table:: **Table 3** **requests**

   +-----------+---------+----------------------------------------------------------+
   | Parameter | Type    | Description                                              |
   +===========+=========+==========================================================+
   | time      | Integer | Specifies the end time since Unix Epoch in milliseconds. |
   +-----------+---------+----------------------------------------------------------+
   | num       | Integer | Specifies the number of requests.                        |
   +-----------+---------+----------------------------------------------------------+

.. _waf_02_0073__table1441245463618:

.. table:: **Table 4** **attacks**

   +-----------+---------+----------------------------------------------------------+
   | Parameter | Type    | Description                                              |
   +===========+=========+==========================================================+
   | time      | Integer | Specifies the end time since Unix Epoch in milliseconds. |
   +-----------+---------+----------------------------------------------------------+
   | num       | Integer | Specifies the number of attacks.                         |
   +-----------+---------+----------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
     "requests": [
           {"time": 1499817600, "num": 123400},
           {"time": 1499817601, "num": 123401},
           {"time": 1499817602, "num": 123402}
     ],
     "attacks": [
           {"time": 1499817600, "num": 1234},
           {"time": 1499817601, "num": 1235},
           {"time": 1499817602, "num": 1236}
     ]
   }

Status Code
-----------

:ref:`Table 5 <waf_02_0073__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0073__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 5** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
