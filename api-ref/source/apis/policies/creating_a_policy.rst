:original_name: waf_02_0030.html

.. _waf_02_0030:

Creating a Policy
=================

Function Description
--------------------

This API is used to create a policy.

URI
---

-  URI format

   POST /v1/{project_id}/waf/policy

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

.. table:: **Table 2** Parameter description

   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                          |
   +===========+===========+========+======================================================================================================================================+
   | name      | Yes       | String | Specifies the policy name. The maximum length is 256 characters. Only digits, letters, underscores (_), and hyphens (-) are allowed. |
   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 3** Parameter description

   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | Parameter             | Type                                             | Description                                                               |
   +=======================+==================================================+===========================================================================+
   | id                    | String                                           | Specifies the instance ID.                                                |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | name                  | String                                           | Specifies the policy name.                                                |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | options               | :ref:`Table 4 <waf_02_0030__table1272813819259>` | Specifies whether a protection rule is enabled.                           |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | action                | :ref:`Table 5 <waf_02_0030__table1231716412312>` | Specifies the mode of Basic Web Protection. The default value is **log**. |
   |                       |                                                  |                                                                           |
   |                       |                                                  | -  **block**: WAF blocks and logs detected attacks.                       |
   |                       |                                                  | -  **log**: WAF logs detected attacks only.                               |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | level                 | Integer                                          | Specifies the protection level.                                           |
   |                       |                                                  |                                                                           |
   |                       |                                                  | -  **1**: low                                                             |
   |                       |                                                  | -  **2**: medium                                                          |
   |                       |                                                  | -  **3**: high                                                            |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | full_detection        | Boolean                                          | Specifies the detection mode in Precise Protection.                       |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | hosts                 | Array                                            | Specifies the domain IDs.                                                 |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+
   | timestamp             | Long                                             | Specifies the time when a policy is created.                              |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------+

.. _waf_02_0030__table1272813819259:

.. table:: **Table 4** **options**

   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                     |
   +=======================+=======================+=================================================================================================================================+
   | webattack             | Boolean               | Specifies whether Basic Web Protection is enabled. By default, this function is enabled.                                        |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | common                | Boolean               | Specifies whether General Check in Basic Web Protection is enabled. By default, this function is enabled.                       |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | crawler               | Boolean               | Specifies whether the master crawler detection switch in Basic Web Protection is enabled. By default, this function is enabled. |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | crawler_engine        | Boolean               | Specifies whether the Search Engine switch in Basic Web Protection is enabled. By default, this function is disabled.           |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | crawler_scanner       | Boolean               | Specifies whether the Scanner switch in Basic Web Protection is enabled. By default, this function is enabled.                  |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | crawler_script        | Boolean               | Specifies whether the Script Tool switch in Basic Web Protection is enabled. By default, this function is disabled.             |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | crawler_other         | Boolean               | Specifies whether detection of other crawlers in Basic Web Protection is enabled. By default, this function is disabled.        |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | webshell              | Boolean               | Specifies whether webshell detection in Basic Web Protection is enabled. By default, this function is disabled.                 |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | cc                    | Boolean               | Specifies whether CC Attack Protection is enabled. By default, this function is enabled.                                        |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | custom                | Boolean               | Specifies whether Precise Protection is enabled. By default, this function is enabled.                                          |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | whiteblackip          | Boolean               | Specifies whether Blacklist and Whitelist is enabled. By default, this function is enabled.                                     |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | privacy               | Boolean               | Specifies whether Data Masking is enabled. By default, this function is enabled.                                                |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | Ignore                | Boolean               | Specifies whether False Alarm Masking is enabled. By default, this function is enabled.                                         |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+
   | antitamper            | Boolean               | Specifies whether Web Tamper Protection is enabled. By default, this function is enabled.                                       |
   |                       |                       |                                                                                                                                 |
   |                       |                       | -  **true**: enabled.                                                                                                           |
   |                       |                       | -  **false**: disabled.                                                                                                         |
   +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0030__table1231716412312:

.. table:: **Table 5** **action**

   +-----------------------+-----------------------+---------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                               |
   +=======================+=======================+===========================================================================+
   | category              | String                | Specifies the mode of Basic Web Protection. The default value is **log**. |
   |                       |                       |                                                                           |
   |                       |                       | -  **block**: WAF blocks and logs detected attacks.                       |
   |                       |                       | -  **log**: WAF logs detected attacks only.                               |
   +-----------------------+-----------------------+---------------------------------------------------------------------------+

Examples
--------

A policy named **policy_1** is used as an example.

-  Request example

   .. code-block::

      {
        "name": "policy_1"
      }

-  Response example

   .. code-block::

      {
                "id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
                "name": "policy_1",
                "action": {
                    "category": "block"
                 },
                 "options": {
                     "webattack": true,
                     "common": true,
                     "crawler": true,
                     "crawler_engine": true,
                     "crawler_scanner": true,
                     "crawler_script": true,
                     "crawler_other": true,
                     "webshell": true,
                     "cc": true,
                     "custom": true,
                     "whiteblackip": true,
                     "ignore": true,
                     "privacy": true,
                     "antitamper": true
                  },
                 "level": 1,
                 "full_detection": false,
                 "hosts": [],
                 "timestamp": 1499817612
      }

Status Code
-----------

:ref:`Table 6 <waf_02_0030__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0030__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 6** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
