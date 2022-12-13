:original_name: waf_02_0031.html

.. _waf_02_0031:

Querying a Policy
=================

Function Description
--------------------

This API is used to query details about a policy.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      policy_id  Yes       String Specifies the policy ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                             | Description                                                                                                                                                       |
   +=======================+==================================================+===================================================================================================================================================================+
   | id                    | String                                           | Specifies the instance ID.                                                                                                                                        |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                                           | Specifies the policy name.                                                                                                                                        |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action                | :ref:`Table 3 <waf_02_0031__table1231716412312>` | Specifies the protective action after a rule is matched.                                                                                                          |
   |                       |                                                  |                                                                                                                                                                   |
   |                       |                                                  | -  **block**: block and log detected attacks.                                                                                                                     |
   |                       |                                                  | -  **log**: only log detected attacks.                                                                                                                            |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | options               | :ref:`Table 4 <waf_02_0031__table1272813819259>` | Specifies the protection switches.                                                                                                                                |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | level                 | Integer                                          | Specifies the protection level.                                                                                                                                   |
   |                       |                                                  |                                                                                                                                                                   |
   |                       |                                                  | -  **1**: low                                                                                                                                                     |
   |                       |                                                  | -  **2**: medium                                                                                                                                                  |
   |                       |                                                  | -  **3**: high                                                                                                                                                    |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | full_detection        | Boolean                                          | Specifies the detection mode in Precise Protection.                                                                                                               |
   |                       |                                                  |                                                                                                                                                                   |
   |                       |                                                  | -  **true**: full detection. Full detection finishes all threat detections before blocking requests that meet Precise Protection specified conditions.            |
   |                       |                                                  | -  **false**: instant detection. Instant detection immediately ends threat detection after blocking a request that meets Precise Protection specified conditions. |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hosts                 | Array                                            | Specifies the domain IDs.                                                                                                                                         |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                                             | Specifies the time when a policy is created.                                                                                                                      |
   +-----------------------+--------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0031__table1231716412312:

.. table:: **Table 3** **action**

   +-----------------------+-----------------------+-----------------------------------------------------+
   | Parameter             | Type                  | Description                                         |
   +=======================+=======================+=====================================================+
   | category              | String                | Specifies the protective action.                    |
   |                       |                       |                                                     |
   |                       |                       | -  **block**: WAF blocks and logs detected attacks. |
   |                       |                       | -  **log**: WAF logs detected attacks only.         |
   +-----------------------+-----------------------+-----------------------------------------------------+

.. _waf_02_0031__table1272813819259:

.. table:: **Table 4** **options**

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                               |
   +=======================+=======================+===========================================================================================+
   | webattack             | Boolean               | Specifies whether Basic Web Protection is enabled.                                        |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | common                | Boolean               | Specifies whether General Check in Basic Web Protection is enabled.                       |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | crawler               | Boolean               | Specifies whether the master crawler detection switch in Basic Web Protection is enabled. |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | crawler_engine        | Boolean               | Specifies whether the Search Engine switch in Basic Web Protection is enabled.            |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | crawler_scanner       | Boolean               | Specifies whether the Scanner switch in Basic Web Protection is enabled.                  |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | crawler_script        | Boolean               | Specifies whether the Script Tool switch in Basic Web Protection is enabled.              |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | crawler_other         | Boolean               | Specifies whether detection of other crawlers in Basic Web Protection is enabled.         |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | webshell              | Boolean               | Specifies whether webshell detection in Basic Web Protection is enabled.                  |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | cc                    | Boolean               | Specifies whether CC Attack Protection is enabled.                                        |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | custom                | Boolean               | Specifies whether Precise Protection is enabled.                                          |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | whiteblackip          | Boolean               | Specifies whether Blacklist and Whitelist is enabled.                                     |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | privacy               | Boolean               | Specifies whether Data Masking is enabled.                                                |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | Ignore                | Boolean               | Specifies whether False Alarm Masking is enabled.                                         |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+
   | antitamper            | Boolean               | Specifies whether Web Tamper Protection is enabled.                                       |
   |                       |                       |                                                                                           |
   |                       |                       | -  **true**: enabled.                                                                     |
   |                       |                       | -  **false**: disabled.                                                                   |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------+

Example
-------

A policy named **policy_2** is used as an example.

Response example

.. code-block::

   {
             "id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
             "name": "policy_2",
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
              "hosts": ["11111111111111111", "2222222222222222222"],
              "timestamp": 1499817612
   }

Status Code
-----------

:ref:`Table 5 <waf_02_0031__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0031__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 5** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
