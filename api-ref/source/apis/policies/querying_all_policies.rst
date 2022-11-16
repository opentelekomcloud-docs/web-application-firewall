:original_name: waf_02_0029.html

.. _waf_02_0029:

Querying All Policies
=====================

Function Description
--------------------

This API is used to query the list of policies.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy?policyname={policyname}&offset={offset}&limit={limit}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                                |
      +============+===========+========+============================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                                  |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------+
      | policyname | No        | String | Specifies the policy name. GET /v1/{project_id}/waf/policy/{policy_id}/whiteblackip?offset={offset}&limit={limit}          |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------+
      | offset     | No        | Long   | Specifies the number of returned pages. Its value ranges from **0** to **65535**. The default value is **0**.              |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------+
      | limit      | No        | Long   | Specifies the maximum number of records displayed on each page. Value range: (**0**, **10**]. The default value is **10**. |
      +------------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+---------------------------------------------------+-----------------------------------------+
   | Parameter | Type                                              | Description                             |
   +===========+===================================================+=========================================+
   | total     | Integer                                           | Specifies the total number of policies. |
   +-----------+---------------------------------------------------+-----------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0029__table16394183011019>` | Specifies the policy objects.           |
   +-----------+---------------------------------------------------+-----------------------------------------+

.. _waf_02_0029__table16394183011019:

.. table:: **Table 3** **items**

   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                             | Description                                                                                                                                                                                                                                                                           |
   +=======================+==================================================+=======================================================================================================================================================================================================================================================================================+
   | id                    | String                                           | Specifies the instance ID.                                                                                                                                                                                                                                                            |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                                           | Specifies the policy name.                                                                                                                                                                                                                                                            |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | options               | :ref:`Table 4 <waf_02_0029__table1272813819259>` | Specifies whether a protection rule is enabled.                                                                                                                                                                                                                                       |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action                | :ref:`Table 5 <waf_02_0029__table1231716412312>` | Specifies the mode of Basic Web Protection.                                                                                                                                                                                                                                           |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  | -  **block**: WAF blocks and logs detected attacks.                                                                                                                                                                                                                                   |
   |                       |                                                  | -  **log**: WAF logs detected attacks only.                                                                                                                                                                                                                                           |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | level                 | Integer                                          | Specifies the protection level.                                                                                                                                                                                                                                                       |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  | -  **1**: low                                                                                                                                                                                                                                                                         |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  |    WAF detects wget, cURL, and more but does not detect XSS and command injection attacks in the header, so you may miss more vulnerabilities that in fact exist. If you find out that configured protection rules are affecting your services, adjust the protection level to **1**. |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  | -  **2**: medium                                                                                                                                                                                                                                                                      |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  |    By default, **2** is selected. In this level, WAF detects remote file inclusion, third-party software vulnerabilities, webshell, and cp and ftp commands.                                                                                                                          |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  | -  **3**: high                                                                                                                                                                                                                                                                        |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  |    WAF detects Netcat, Nmap, kill commands, and more. If you need stricter protection, select **3** to avoid unreported vulnerabilities but you may see more vulnerabilities that in fact unlikely exist.                                                                             |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | full_detection        | Boolean                                          | Specifies the detection mode in Precise Protection.                                                                                                                                                                                                                                   |
   |                       |                                                  |                                                                                                                                                                                                                                                                                       |
   |                       |                                                  | -  **true**: full detection. Full detection finishes all threat detections before blocking requests that meet Precise Protection specified conditions.                                                                                                                                |
   |                       |                                                  | -  **false**: instant detection. Instant detection immediately ends threat detection after blocking a request that meets Precise Protection specified conditions.                                                                                                                     |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hosts                 | Array                                            | Specifies the domain IDs.                                                                                                                                                                                                                                                             |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                                             | Specifies the time when a policy is created.                                                                                                                                                                                                                                          |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0029__table1272813819259:

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

.. _waf_02_0029__table1231716412312:

.. table:: **Table 5** **action**

   +-----------------------+-----------------------+-----------------------------------------------------+
   | Parameter             | Type                  | Description                                         |
   +=======================+=======================+=====================================================+
   | category              | String                | Specifies the mode of Basic Web Protection.         |
   |                       |                       |                                                     |
   |                       |                       | -  **block**: WAF blocks and logs detected attacks. |
   |                       |                       | -  **log**: WAF logs detected attacks only.         |
   +-----------------------+-----------------------+-----------------------------------------------------+

Example
-------

**total** with a value of **2** is used as an example.

Response example

.. code-block::

   {
       "total": 2,
       "items": [
           {
             "id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
             "name": "policy_1",
             "action": {
                 "category ": "block"
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
           }, {
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
        ]
   }

Status Code
-----------

:ref:`Table 6 <waf_02_0029__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0029__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 6** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
