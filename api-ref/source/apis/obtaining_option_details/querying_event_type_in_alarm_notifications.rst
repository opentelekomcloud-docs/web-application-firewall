:original_name: waf_02_0080.html

.. _waf_02_0080:

Querying Event Type in Alarm Notifications
==========================================

Function Description
--------------------

This API is used to query event type in an alarm notification.

URI
---

-  URI format

   GET /v1/{project_id}/waf/map/threat?lang={lang}

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

   +-----------+---------------------------------------------------+------------------------------------+
   | Parameter | Type                                              | Description                        |
   +===========+===================================================+====================================+
   | threats   | List                                              | Specifies the list of event types. |
   +-----------+---------------------------------------------------+------------------------------------+
   | locale    | :ref:`Table 3 <waf_02_0080__table10363184164611>` | Specifies event names.             |
   +-----------+---------------------------------------------------+------------------------------------+

.. _waf_02_0080__table10363184164611:

.. table:: **Table 3** **locale**

   ============ ====== ==================================
   Parameter    Type   Description
   ============ ====== ==================================
   xss          String Specifies XSS attack.
   sqli         String Specifies SQL injection.
   cmdi         String Specifies command injection.
   cc           String Specifies CC attack.
   custom       String Specifies Precise Protection.
   illegal      String Specifies invalid requests.
   lfi          String Specifies local file inclusion.
   robot        String Specifies malicious crawlers.
   antitamper   String Specifies Web Tamper Protection.
   rfi          String Specifies remote file inclusion.
   vuln         String Specifies other types of attacks.
   whiteblackip String Specifies Blacklist and Whitelist.
   webshell     String Specifies webshells.
   ============ ====== ==================================

Example
-------

Response example

.. code-block::

   {
     "threats": ["xss", "sqli", "cmdi"],
     "locale": {
          "xss":  "Cross Site Scripting",
          "sqli": "SQL Injection",
          "cmdi": "Command Injection"
      }
   }

Status Code
-----------

:ref:`Table 4 <waf_02_0080__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0080__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
