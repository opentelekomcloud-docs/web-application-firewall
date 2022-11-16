:original_name: waf_02_0072.html

.. _waf_02_0072:

Querying Event Distribution
===========================

Function Description
--------------------

This API is used to query event distribution.

URI
---

-  URI format

   GET /v1/{project_id}/waf/event/attack/type?from={from}&to={to}&hosts={hostids}

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

   +--------------+---------+----------------------------------------------------------------------------------------+
   | Parameter    | Type    | Description                                                                            |
   +==============+=========+========================================================================================+
   | xss          | Integer | Specifies the number of XSS attacks detected within the time range.                    |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | sqli         | Integer | Specifies the number of SQL injection attacks detected within the time range.          |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | cmdi         | Integer | Specifies the number of command injection attacks detected within the time range.      |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | cc           | Integer | Specifies the number of CC attacks detected within the time range.                     |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | custom       | Integer | Specifies the number of Precise Protection events detected within the time range.      |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | illegal      | Integer | Specifies the number of invalid requests detected within the time range.               |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | lfi          | Integer | Specifies the number of local file inclusion attacks detected within the time range.   |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | robot        | Integer | Specifies the number of malicious crawlers detected within the time range.             |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | antitamper   | Integer | Specifies the number of webpage tampering attacks detected within the time range.      |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | rfi          | Integer | Specifies the number of remote file inclusion attacks detected within the time range.  |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | vuln         | Integer | Specifies the number of other attacks detected within the time range.                  |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | whiteblackip | Integer | Specifies the number of Blacklist and Whitelist events detected within the time range. |
   +--------------+---------+----------------------------------------------------------------------------------------+
   | webshell     | Integer | Specifies the number of webshell attacks detected within the time range.               |
   +--------------+---------+----------------------------------------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
       "xss": 150,
       "sqli": 321,
       "cmdi": 120,
       "robot": 10,
       "whiteblackip": 30,
       "custom": 50,
       "cc": 60,
       "illegal": 10
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0072__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0072__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
