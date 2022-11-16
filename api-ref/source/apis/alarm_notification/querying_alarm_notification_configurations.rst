:original_name: waf_02_0081.html

.. _waf_02_0081:

Querying Alarm Notification Configurations
==========================================

Function Description
--------------------

This API is used to query alarm notification configurations.

URI
---

-  URI format

   GET /v1/{project_id}/waf/config/alert

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

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                                  |
   +=======================+=======================+==============================================================================================================================================================================================================+
   | id                    | String                | Specifies the unique ID of an alarm configuration.                                                                                                                                                           |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enabled               | Boolean               | Specifies whether to send an alarm notification.                                                                                                                                                             |
   |                       |                       |                                                                                                                                                                                                              |
   |                       |                       | -  **true**: Send the alarm notification.                                                                                                                                                                    |
   |                       |                       | -  **false**: Do not send the alarm notification.                                                                                                                                                            |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | topic_urn             | String                | Specifies the SMN topic to which an alarm is sent.                                                                                                                                                           |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sendfreq              | Integer               | Specifies the minimum interval between two alarms in minutes. The options are **5**, **15**, **30**, and **60**.                                                                                             |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | times                 | Integer               | Specifies the alarm threshold. Alarm notifications are sent when the number of attacks is greater than or equal to the threshold within the configured period. This value is greater than or equal to **1**. |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | threat                | List<String>          | Specifies the list of event types.                                                                                                                                                                           |
   |                       |                       |                                                                                                                                                                                                              |
   |                       |                       | -  **all** refers to all types of events.                                                                                                                                                                    |
   |                       |                       | -  **cc** refers to CC attack.                                                                                                                                                                               |
   |                       |                       | -  **cmdi** refers to command injection.                                                                                                                                                                     |
   |                       |                       | -  **custom** refers to Precise Protection events.                                                                                                                                                           |
   |                       |                       | -  **illegal** refers to invalid requests.                                                                                                                                                                   |
   |                       |                       | -  **sqli** refers to SQL injection.                                                                                                                                                                         |
   |                       |                       | -  **lfi** refers to local file inclusion.                                                                                                                                                                   |
   |                       |                       | -  **robot** refers to malicious crawlers.                                                                                                                                                                   |
   |                       |                       | -  **antitamper** refers to Web Tamper Protection events.                                                                                                                                                    |
   |                       |                       | -  **rfi** refers to remote file inclusion.                                                                                                                                                                  |
   |                       |                       | -  **vuln** refers to other types of attacks.                                                                                                                                                                |
   |                       |                       | -  **xss** refers to XSS attack.                                                                                                                                                                             |
   |                       |                       | -  **whiteblackip** refers to Blacklist and Whitelist events.                                                                                                                                                |
   |                       |                       | -  **webshell** refers to webshells.                                                                                                                                                                         |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | locale                | String                | Specifies the language configuration. Only **zh-cn** and **en-us** are supported. The default value is **en-us**.                                                                                            |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
       "id": "37b4bbe8a562453aa0163a96e6b71dd6",
       "enabled": true,
       "topic_urn": "urn:smn:eude:fca6f667ac5f4d9798d1641dfd38106b:wbtest",
       "sendfreq": 5,
       "times": 200,
       "threat": ["xss", "sqli", "cmdi"],
       "locale": "en-us"
   }

Status Code
-----------

:ref:`Table 3 <waf_02_0081__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0081__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 3** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
