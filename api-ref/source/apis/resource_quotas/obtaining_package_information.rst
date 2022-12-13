:original_name: waf_02_0009.html

.. _waf_02_0009:

Obtaining Package Information
=============================

Function Description
--------------------

This API is used to obtain package information of a user.

URI
---

-  URI format

   GET /v1/{project_id}/waf/bundle

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

   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | Parameter | Type                                              | Description                                               |
   +===========+===================================================+===========================================================+
   | type      | Integer                                           | Specifies version information.                            |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | name      | String                                            | Specifies the package name.                               |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | options   | :ref:`Table 3 <waf_02_0009__table1272813819259>`  | Specifies the protection switches.                        |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | rule      | :ref:`Table 4 <waf_02_0009__table16103191716381>` | Specifies the maximum number of rules in a policy.        |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | host      | :ref:`Table 5 <waf_02_0009__table951693116344>`   | Specifies the maximum number of domain names in a policy. |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+
   | other     | :ref:`Table 6 <waf_02_0009__table027365911177>`   | Specifies other restrictions in the package.              |
   +-----------+---------------------------------------------------+-----------------------------------------------------------+

.. _waf_02_0009__table1272813819259:

.. table:: **Table 3** **options**

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                       |
   +=======================+=======================+===================================================================================================================================================================+
   | webattack             | Boolean               | Specifies whether Basic Web Protection is enabled.                                                                                                                |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | common                | Boolean               | Specifies whether General Check in Basic Web Protection is enabled.                                                                                               |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | crawler               | Boolean               | Specifies whether the master crawler detection switch in Basic Web Protection is enabled.                                                                         |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | .. note::                                                                                                                                                         |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       |    If **crawler** is **false**, all the subswitches, **crawler_engine**, **crawler_scanner**, **crawler_script**, and **crawler_other** are invalid.              |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | crawler_engine        | Boolean               | Specifies whether the Search Engine switch in Basic Web Protection is enabled.                                                                                    |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | crawler_scanner       | Boolean               | Specifies whether the Scanner switch in Basic Web Protection is enabled.                                                                                          |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | crawler_script        | Boolean               | Specifies whether the Script Tool switch in Basic Web Protection is enabled.                                                                                      |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | crawler_other         | Boolean               | Specifies whether detection of other crawlers in Basic Web Protection is enabled.                                                                                 |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | webshell              | Boolean               | Specifies whether webshell detection is enabled.                                                                                                                  |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cc                    | Boolean               | Specifies whether CC Attack Protection is enabled.                                                                                                                |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | custom                | Boolean               | Specifies whether Precise Protection is enabled.                                                                                                                  |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | whiteblackip          | Boolean               | Specifies whether Blacklist and Whitelist is enabled.                                                                                                             |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | privacy               | Boolean               | Specifies whether Data Masking is enabled.                                                                                                                        |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Ignore                | Boolean               | Specifies whether False Alarm Masking is enabled.                                                                                                                 |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | antitamper            | Boolean               | Specifies whether Web Tamper Protection is enabled.                                                                                                               |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: enabled.                                                                                                                                             |
   |                       |                       | -  **false**: disabled.                                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | full_detection        | Boolean               | Specifies whether the full detection mode in Precise Protection is enabled.                                                                                       |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: full detection. Full detection finishes all threat detections before blocking requests that meet Precise Protection specified conditions.            |
   |                       |                       | -  **false**: instant detection. Instant detection immediately ends threat detection after blocking a request that meets Precise Protection specified conditions. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | log_download          | Boolean               | Specifies whether log download is available.                                                                                                                      |
   |                       |                       |                                                                                                                                                                   |
   |                       |                       | -  **true**: available.                                                                                                                                           |
   |                       |                       | -  **false**: unavailable.                                                                                                                                        |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0009__table16103191716381:

.. table:: **Table 4** **rule**

   +--------------+---------+--------------------------------------------------------------------------------------------+
   | Parameter    | Type    | Description                                                                                |
   +==============+=========+============================================================================================+
   | antitamper   | Integer | Specifies the total number of web tamper protection rules. The maximum value is **100**.   |
   +--------------+---------+--------------------------------------------------------------------------------------------+
   | cc           | Integer | Specifies the total number of CC attack protection rules. The maximum value is **100**.    |
   +--------------+---------+--------------------------------------------------------------------------------------------+
   | custom       | Integer | Specifies the total number of precise protection rules. The maximum value is **100**.      |
   +--------------+---------+--------------------------------------------------------------------------------------------+
   | ignore       | Integer | Specifies the total number of false alarm masking rules. The maximum value is **1000**.    |
   +--------------+---------+--------------------------------------------------------------------------------------------+
   | privacy      | Integer | Specifies the total number of data masking rules. The maximum value is **1000**.           |
   +--------------+---------+--------------------------------------------------------------------------------------------+
   | whiteblackip | Integer | Specifies the total number of blacklist and whitelist rules. The maximum value is **100**. |
   +--------------+---------+--------------------------------------------------------------------------------------------+

.. note::

   Contact the administrator to increase the maximum values in :ref:`Table 4 <waf_02_0009__table16103191716381>`.

.. _waf_02_0009__table951693116344:

.. table:: **Table 5** **host**

   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | Parameter             | Type                                            | Description                                                                      |
   +=======================+=================================================+==================================================================================+
   | wildcard              | Boolean                                         | Specifies whether a wildcard domain is supported.                                |
   |                       |                                                 |                                                                                  |
   |                       |                                                 | -  **true**: supported.                                                          |
   |                       |                                                 | -  **false**: unsupported.                                                       |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | ports                 | :ref:`Table 7 <waf_02_0009__table512720205117>` | Specifies the range of ports supported.                                          |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | protocol              | :ref:`Table 8 <waf_02_0009__table587623519166>` | Specifies the client protocol.                                                   |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | server                | Integer                                         | Specifies the number of backend servers supported. The maximum value is **30**.  |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | host                  | Integer                                         | Specifies the number of subdomain names supported. The maximum value is **100**. |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | domain                | Integer                                         | Specifies the number of domain names supported. The maximum value is **100**.    |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | cert_num              | Integer                                         | Specifies the number of certificates supported. The maximum value is **100**.    |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | policy_apply_to       | Boolean                                         | Specifies whether a policy can be applied to multiple domain names.              |
   |                       |                                                 |                                                                                  |
   |                       |                                                 | -  **true**: A policy can be applied to multiple domain names.                   |
   |                       |                                                 | -  **false**: A policy cannot be applied to multiple domain names.               |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+
   | policy_num            | Integer                                         | Specifies the number of policies supported. The maximum value is **5000**.       |
   +-----------------------+-------------------------------------------------+----------------------------------------------------------------------------------+

.. _waf_02_0009__table027365911177:

.. table:: **Table 6** **other**

   +------------+---------+-------------------------------------------------------------------------------------------------------+
   | Parameter  | Type    | Description                                                                                           |
   +============+=========+=======================================================================================================+
   | default_cc | Integer | Specifies the maximum number of requests from a web visitor in a default CC attack protection policy. |
   +------------+---------+-------------------------------------------------------------------------------------------------------+

.. _waf_02_0009__table512720205117:

.. table:: **Table 7** **ports**

   +-----------------------+-----------------------+-----------------------------------------------------+
   | Parameter             | Type                  | Description                                         |
   +=======================+=======================+=====================================================+
   | http                  | Array                 | Specifies the list of HTTP ports supported.         |
   +-----------------------+-----------------------+-----------------------------------------------------+
   | https                 | Array                 | Specifies the list of HTTPS ports supported.        |
   +-----------------------+-----------------------+-----------------------------------------------------+
   | max_num               | Integer               | Specifies the number of ports supported.            |
   +-----------------------+-----------------------+-----------------------------------------------------+
   | none_standard         | Boolean               | Specifies whether non-standard ports are supported. |
   |                       |                       |                                                     |
   |                       |                       | -  **true**: Non-standard ports are supported.      |
   |                       |                       | -  **false**: Non-standard ports are not supported. |
   +-----------------------+-----------------------+-----------------------------------------------------+

.. _waf_02_0009__table587623519166:

.. table:: **Table 8** **protocol**

   +-----------------------+-----------------------+---------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                   |
   +=======================+=======================+===============================================================+
   | http                  | Boolean               | Specifies whether the HTTP protocol is supported.             |
   |                       |                       |                                                               |
   |                       |                       | -  **true**: The HTTP protocol is supported.                  |
   |                       |                       | -  **false**: The HTTP protocol is not supported.             |
   +-----------------------+-----------------------+---------------------------------------------------------------+
   | https                 | Boolean               | Specifies whether the HTTPS protocol is supported.            |
   |                       |                       |                                                               |
   |                       |                       | -  **true**: The HTTPS protocol is supported.                 |
   |                       |                       | -  **false**: The HTTPS protocol is not supported.            |
   +-----------------------+-----------------------+---------------------------------------------------------------+
   | http_https            | Boolean               | Specifies whether the HTTP and HTTPS protocols are supported. |
   |                       |                       |                                                               |
   |                       |                       | -  **true**: Both HTTP and HTTPS are supported.               |
   |                       |                       | -  **false**: Neither HTTP nor HTTPS is supported.            |
   +-----------------------+-----------------------+---------------------------------------------------------------+

Example
-------

Response example

.. code-block::

   {
     "type": 1,
     "name": "Basic",
     "options": {
       "webattack": true,
       "common": true,
       "crawler": true,
       "webshell": false,
       "cc": false,
       "custom": false,
       "whiteblackip": true,

       "privacy": true,
       "ignore": true,
       "antitamper": false,
   "log_download": true,
     },
     "rule": {
       "cc": 0,
       "custom": 0,
       "whiteblackip": 10,

       "privacy": 10,
       "ignore": 1000,
   "antitamper": 0,
     },
     "host": {
       "wildcard": false,
       "protocol": {
         "http": true,
         "https": false,
         "http_https": false
       },
       "ports": {
         "none_standard": false,
         "http": [],
         "https": [],
         "max_num": 0
       },
       "domain": 1,
       "host": 10,
       "server": 10,
       "route": false
     },
     "other": {
         "default_cc": 25000
       }
   }

Status Code
-----------

:ref:`Table 9 <waf_02_0009__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0009__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 9** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
