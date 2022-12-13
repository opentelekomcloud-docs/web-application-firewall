:original_name: waf_02_0017.html

.. _waf_02_0017:

Querying the Source IP Header
=============================

Function Description
--------------------

This API is used to query the source IP header.

URI
---

-  URI format

   GET /v1/{project_id}/waf/map/sipheader?lang={lang}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                    |
      +============+===========+========+================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                      |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------+
      | lang       | No        | String | Specifies the language configuration. The options are **zh-cn** and **en-us**. The default value is **en-us**. |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +--------------+---------------------------------------------------+------------------------------------------+
   | Parameter    | Type                                              | Description                              |
   +==============+===================================================+==========================================+
   | sipheadermap | :ref:`Table 3 <waf_02_0017__table10363184164611>` | Specifies the list of source IP headers. |
   +--------------+---------------------------------------------------+------------------------------------------+
   | locale       | :ref:`Table 4 <waf_02_0017__table5644135016296>`  | Specifies additional information.        |
   +--------------+---------------------------------------------------+------------------------------------------+

.. _waf_02_0017__table10363184164611:

.. table:: **Table 3** **sipheadermap**

   +------------+-------+----------------------------------------------------------------------------------------------+
   | Parameter  | Type  | Description                                                                                  |
   +============+=======+==============================================================================================+
   | default    | Array | Specifies the default HTTP request header to identify the real source IP address.            |
   +------------+-------+----------------------------------------------------------------------------------------------+
   | cloudflare | Array | Specifies the HTTP request header used by Cloudflare to identify the real source IP address. |
   +------------+-------+----------------------------------------------------------------------------------------------+
   | akamai     | Array | Specifies the HTTP request header used by Akamai to identify the real source IP address.     |
   +------------+-------+----------------------------------------------------------------------------------------------+
   | custom     | Array | Specifies the custom HTTP request header to identify the real source IP address.             |
   +------------+-------+----------------------------------------------------------------------------------------------+

.. _waf_02_0017__table5644135016296:

.. table:: **Table 4** **locale**

   ========== ====== ============================
   Parameter  Type   Description
   ========== ====== ============================
   default    String The value is **Default**.
   cloudflare String The value is **CloudFlare**.
   akamai     String The value is **Akamai**.
   custom     String The value is **Custom**.
   ========== ====== ============================

Example
-------

Response example

.. code-block::

   {
     "sipheadermap": {
         "default": ["X-Forwarded-For"],
         "cloudflare": ["CF-Connecting-IP", "X-Forwarded-For"],
         "akamai": ["True-Client-IP"],
         "custom": []
     },
     "locale": {
          "default": "Default",
          "cloudflare": "CloudFlare",
          "akamai": "Akamai",
          "custom": "Custom"
      }
   }

Status Code
-----------

:ref:`Table 5 <waf_02_0017__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0017__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 5** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
