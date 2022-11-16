:original_name: waf_02_0045.html

.. _waf_02_0045:

Querying a CC Attack Protection Rule
====================================

Function Description
--------------------

This API is used to query details about a CC attack protection rule.

URI
---

-  URI format

   GET /v1/{project_id}/waf/policy/{policy_id}/cc/{ccrule_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+--------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                      |
      +============+===========+========+==================================================+
      | project_id | Yes       | String | Specifies the project ID.                        |
      +------------+-----------+--------+--------------------------------------------------+
      | policy_id  | Yes       | String | Specifies the policy ID.                         |
      +------------+-----------+--------+--------------------------------------------------+
      | ccrule_id  | Yes       | String | Specifies the ID of a CC attack protection rule. |
      +------------+-----------+--------+--------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                            | Description                                                                                                                |
   +=======================+=================================================+============================================================================================================================+
   | id                    | String                                          | Specifies the ID of a CC attack protection rule.                                                                           |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | policy_id             | String                                          | Specifies the policy ID.                                                                                                   |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | path                  | String                                          | Specifies the URL to which the rule applies, excluding a domain name.                                                      |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | limit_num             | Integer                                         | Specifies the number of requests allowed from a web visitor in a rate limiting period.                                     |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | limit_period          | Integer                                         | Specifies the rate limiting period.                                                                                        |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | lock_time             | Integer                                         | Specifies the lock duration. The value ranges from **0** seconds to **2\ 32** seconds.                                     |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | tag_type              | String                                          | Specifies the rate limit mode.                                                                                             |
   |                       |                                                 |                                                                                                                            |
   |                       |                                                 | -  **ip**: A web visitor is identified by the IP address.                                                                  |
   |                       |                                                 | -  **cookie**: A web visitor is identified by the cookie key value.                                                        |
   |                       |                                                 | -  **other**: A web visitor is identified by the Referer field (user-defined request source).                              |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | tag_index             | String                                          | If **tag_type** is set to **cookie**, this parameter indicates cookie name.                                                |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | tag_condition         | :ref:`Table 3 <waf_02_0045__table2115782102>`   | Specifies the **Referer** (customized request source) field. This field is returned when **tag_type** is set to **other**. |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | action                | :ref:`Table 4 <waf_02_0045__table191681818102>` | Specifies the action taken when the number of requests reaches the upper limit.                                            |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                                            | Specifies the time when a CC attack protection rule is added.                                                              |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | default               | Boolean                                         | Specifies whether the rule is the default CC attack protection rule.                                                       |
   |                       |                                                 |                                                                                                                            |
   |                       |                                                 | -  **true**: The rule is the default CC attack protection rule created by the system when creating a domain name.          |
   |                       |                                                 | -  **false**: The rule is created by users.                                                                                |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0045__table2115782102:

.. table:: **Table 3** **tag_condition**

   ========= ====== =================================================
   Parameter Type   Description
   ========= ====== =================================================
   category  String Specifies the category. The value is **Referer**.
   contents  List   Specifies the category content.
   ========= ====== =================================================

.. _waf_02_0045__table191681818102:

.. table:: **Table 4** **action**

   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                             | Description                                                                                                                                 |
   +=======================+==================================================+=============================================================================================================================================+
   | category              | String                                           | Specifies the action. The default value is **block**.                                                                                       |
   |                       |                                                  |                                                                                                                                             |
   |                       |                                                  | -  **block**: block the requests.                                                                                                           |
   |                       |                                                  | -  **captcha**: Verification code. The user needs to enter the correct verification code after blocking to restore the correct access page. |
   |                       |                                                  |                                                                                                                                             |
   |                       |                                                  | The default value is **block**.                                                                                                             |
   |                       |                                                  |                                                                                                                                             |
   |                       |                                                  | If **tag_type** is set to **other**, this parameter value can only be **block**.                                                            |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | detail                | :ref:`Table 5 <waf_02_0045__table1060217107105>` | Specifies the action details. If **detail** is **null**, the default block page is displayed by default.                                    |
   +-----------------------+--------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0045__table1060217107105:

.. table:: **Table 5** **detail**

   +-----------+-------------------------------------------------+------------------------------+
   | Parameter | Type                                            | Description                  |
   +===========+=================================================+==============================+
   | response  | :ref:`Table 6 <waf_02_0045__table671153413914>` | Specifies the returned page. |
   +-----------+-------------------------------------------------+------------------------------+

.. _waf_02_0045__table671153413914:

.. table:: **Table 6** **response**

   +-----------------------+-----------------------+------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                            |
   +=======================+=======================+========================================================================+
   | content_type          | String                | Specifies the type of the returned page.                               |
   |                       |                       |                                                                        |
   |                       |                       | The options are **application/json**, **text/html**, and **text/xml**. |
   +-----------------------+-----------------------+------------------------------------------------------------------------+
   | content               | String                | Specifies the content of the returned page.                            |
   +-----------------------+-----------------------+------------------------------------------------------------------------+

Example
-------

-  Response example

   .. code-block::

      {
        "id": "3a9b5c0f96784ec8abd8ba61a98064ef",
        "policy_id": "9tre832yf96784ec8abd8ba61a98064ef",
        "path": "/abc1",
        "limit_num": 10,
        "limit_period": 60,
        "lock_time": "",
        "tag_type": "cookie",
        "tag_index": "sesssionid",
        "action": {
          "category": "block",
          "detail": {
            "response": {
              "content_type": "application/json",
              "content": "{\"error\":\"forbidden\"}"
            }
          }
        },
        "timestamp": 1499817600,
         "default": false
      }

Status Code
-----------

:ref:`Table 7 <waf_02_0045__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0045__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 7** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
