:original_name: waf_02_0082.html

.. _waf_02_0082:

Updating Alarm Notification Configurations
==========================================

Function Description
--------------------

This API is used to update alarm notification configurations.

URI
---

-  URI format

   PUT /v1/{project_id}/waf/config/alert/{alertconfig_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +----------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter      | Mandatory | Type   | Description                                                                                                                                                                                             |
      +================+===========+========+=========================================================================================================================================================================================================+
      | project_id     | Yes       | String | Specifies the project ID.                                                                                                                                                                               |
      +----------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | alertconfig_id | Yes       | String | Specifies the ID of the alarm notification configuration to be updated. For details about how to query the alarm configuration ID, see :ref:`Querying Alarm Notification Configurations <waf_02_0081>`. |
      +----------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================================================================================================+
   | enabled         | Yes             | Boolean         | Specifies whether to send an alarm notification.                                                                                                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                              |
   |                 |                 |                 | -  **true**: Send the alarm notification.                                                                                                                                                                    |
   |                 |                 |                 | -  **false**: Do not send the alarm notification.                                                                                                                                                            |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | topic_urn       | Yes             | String          | Specifies the SMN topic to which an alarm is sent.                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                                              |
   |                 |                 |                 | .. note::                                                                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                                              |
   |                 |                 |                 |    The selected topic must be a topic whose subscription information has been configured on the SMN console.                                                                                                 |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sendfreq        | Yes             | Integer         | Specifies the minimum interval between two alarms in minutes. The options are **5**, **15**, **30**, and **60**.                                                                                             |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | times           | Yes             | Integer         | Specifies the alarm threshold. Alarm notifications are sent when the number of attacks is greater than or equal to the threshold within the configured period. This value is greater than or equal to **1**. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | threat          | Yes             | List<String>    | Specifies the list of event types.                                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                                              |
   |                 |                 |                 | -  **all** refers to all types of events.                                                                                                                                                                    |
   |                 |                 |                 | -  **cc** refers to CC attack.                                                                                                                                                                               |
   |                 |                 |                 | -  **cmdi** refers to command injection.                                                                                                                                                                     |
   |                 |                 |                 | -  **custom** refers to Precise Protection events.                                                                                                                                                           |
   |                 |                 |                 | -  **illegal** refers to invalid requests.                                                                                                                                                                   |
   |                 |                 |                 | -  **sqli** refers to SQL injection.                                                                                                                                                                         |
   |                 |                 |                 | -  **lfi** refers to local file inclusion.                                                                                                                                                                   |
   |                 |                 |                 | -  **robot** refers to malicious crawlers.                                                                                                                                                                   |
   |                 |                 |                 | -  **antitamper** refers to Web Tamper Protection events.                                                                                                                                                    |
   |                 |                 |                 | -  **rfi** refers to remote file inclusion.                                                                                                                                                                  |
   |                 |                 |                 | -  **vuln** refers to other types of attacks.                                                                                                                                                                |
   |                 |                 |                 | -  **xss** refers to XSS attack.                                                                                                                                                                             |
   |                 |                 |                 | -  **whiteblackip** refers to Blacklist and Whitelist events.                                                                                                                                                |
   |                 |                 |                 | -  **webshell** refers to webshells.                                                                                                                                                                         |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | locale          | No              | String          | Specifies the language configuration. Only **zh-cn** and **en-us** are supported. The default value is **en-us**.                                                                                            |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

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
   | topic_urn             | String                | Specifies the user-defined SMN topic. Users can receive alarm notifications by SMS or email.                                                                                                                 |
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

Examples
--------

-  Request example

   .. code-block::

      {
          "enabled": true,
          "topic_urn": "urn:smn:eude:fca6f667ac5f4d9798d1641dfd38106b:wbtest",
          "sendfreq": 5,
          "times": 200,
          "threat": ["xss", "sqli", "cmdi"]
      }

-  Response example

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

:ref:`Table 4 <waf_02_0082__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0082__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 4** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
