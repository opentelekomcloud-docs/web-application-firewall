:original_name: waf_02_0014.html

.. _waf_02_0014:

Querying a Domain Name
======================

Function Description
--------------------

This API is used to query details about a domain name.

URI
---

-  URI format

   GET /v1/{project_id}/waf/instance/{instance_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      =========== ========= ====== ==========================
      Parameter   Mandatory Type   Description
      =========== ========= ====== ==========================
      project_id  Yes       String Specifies the project ID.
      instance_id Yes       String Specifies the instance ID.
      =========== ========= ====== ==========================

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Response parameters

   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                       | Description                                                                                                                                                          |
   +=======================+============================================================+======================================================================================================================================================================+
   | id                    | String                                                     | Specifies the instance ID.                                                                                                                                           |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hostname              | String                                                     | Specifies the domain name.                                                                                                                                           |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cname                 | String                                                     | Specifies the CNAME value. For example, **efec1196267b41c399f2980ea4048517.waf.cloud.com**.                                                                          |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | txt_code              | String                                                     | Specifies the TXT record. This parameter is returned only when **proxy** is set to **true**.                                                                         |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sub_domain            | String                                                     | Specifies the subdomain name. This parameter is returned only when **proxy** is set to **true**.                                                                     |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | policy_id             | String                                                     | Specifies the policy ID.                                                                                                                                             |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protect_status        | Integer                                                    | Specifies the WAF mode.                                                                                                                                              |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **0**: disabled.                                                                                                                                                  |
   |                       |                                                            | -  **1**: enabled.                                                                                                                                                   |
   |                       |                                                            | -  **-1**: bypassed.                                                                                                                                                 |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | access_status         | Integer                                                    | Specifies whether a domain name is connected to WAF.                                                                                                                 |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **0**: The domain name is not connected to WAF.                                                                                                                   |
   |                       |                                                            | -  **1**: The domain name is connected to WAF.                                                                                                                       |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol              | String                                                     | Specifies the protocol type. The options are **HTTP**, **HTTPS**, and **HTTP,HTTPS**.                                                                                |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | certificate_id        | String                                                     | Specifies the certificate ID. This parameter is returned only when **client_protocol** is set to **HTTPS**.                                                          |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | server                | Array                                                      | Specifies the origin server information, including the **client_protocol**, **server_protocol**, **address**, and **port** fields.                                   |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **client_protocol**: protocol type of the client. The options are **HTTP** and **HTTPS**.                                                                         |
   |                       |                                                            | -  **server_protocol**: protocol used by WAF to forward client requests to the server. The options are **HTTP** and **HTTPS**.                                       |
   |                       |                                                            | -  **address**: public IP address or domain name of the web server that the client accesses                                                                          |
   |                       |                                                            | -  **port**: port number used by the web server. The value ranges from **0** to **65535**, for example, **8080**.                                                    |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | proxy                 | Boolean                                                    | Specifies whether a proxy is configured.                                                                                                                             |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **true**: A proxy is configured.                                                                                                                                  |
   |                       |                                                            | -  **false**: No proxy is configured.                                                                                                                                |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sip_header_name       | String                                                     | Specifies the type of the source IP header. This parameter is returned only when **proxy** is set to **true**.                                                       |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | The options are as follows: **default**, **cloudflare**, **akamai**, and **custom**.                                                                                 |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sip_header_list       | Array                                                      | Specifies the HTTP request header for identifying the real source IP address. This parameter is returned only when **proxy** is set to **true**.                     |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  If **sip_header_name** is **default**, **sip_header_list** is **["X-Forwarded-For"]**.                                                                            |
   |                       |                                                            | -  If **sip_header_name** is **cloudflare**, **sip_header_list** is **["CF-Connecting-IP", "X-Forwarded-For"]**.                                                     |
   |                       |                                                            | -  If **sip_header_name** is **akamai**, **sip_header_list** is **["True-Client-IP"]**.                                                                              |
   |                       |                                                            | -  If **sip_header_name** is **custom**, you can customize a value.                                                                                                  |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | timestamp             | Long                                                       | Specifies the time when a domain name is created.                                                                                                                    |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | block_page            | :ref:`BlockPage <waf_02_0014__table16354185321711>` object | Alarm page configuration                                                                                                                                             |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tls                   | String                                                     | Specifies the minimum TLS version for accessing the protected domain name. This parameter is returned only when **client_protocol** is set to **HTTPS**.             |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **TLS v1.1**: (Default) Only requests using TLS v1.1 or later can access the domain name.                                                                         |
   |                       |                                                            | -  **TLS v1.2**: Only requests using TLS v1.2 or later can access the domain name.                                                                                   |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | cipher                | String                                                     | Specifies the cipher suite supported by the protected domain name. This parameter is returned only when **client_protocol** is set to **HTTPS**.                     |
   |                       |                                                            |                                                                                                                                                                      |
   |                       |                                                            | -  **cipher_default**: (Default) Good browser compatibility, most clients supported, sufficient for most scenarios                                                   |
   |                       |                                                            | -  **cipher_1**: (Recommended) Best combination of compatibility and security                                                                                        |
   |                       |                                                            | -  **cipher_2**: Strict compliance with forward secrecy requirements of PCI DSS and excellent protection, but earlier browsers may be unable to access the websites. |
   |                       |                                                            | -  **cipher_3**: Support for ECDHE, DHE-GCM, and RSA-AES-GCM algorithms but not CBC                                                                                  |
   +-----------------------+------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0014__table16354185321711:

.. table:: **Table 3** BlockPage

   +--------------+-------------------------------------------------------------+-------------------+
   | Parameter    | Type                                                        | Description       |
   +==============+=============================================================+===================+
   | template     | String                                                      | Template name     |
   +--------------+-------------------------------------------------------------+-------------------+
   | custom_page  | :ref:`CustomPage <waf_02_0014__table11717326142414>` object | Custom alarm page |
   +--------------+-------------------------------------------------------------+-------------------+
   | redirect_url | String                                                      | URL               |
   +--------------+-------------------------------------------------------------+-------------------+

.. _waf_02_0014__table11717326142414:

.. table:: **Table 4** CustomPage

   +--------------+--------+-------------------------------------------------------------------------------------------------------------------+
   | Parameter    | Type   | Description                                                                                                       |
   +==============+========+===================================================================================================================+
   | status_code  | String | Status code                                                                                                       |
   +--------------+--------+-------------------------------------------------------------------------------------------------------------------+
   | content_type | String | The content type of the custom alarm page. The value can be **text/html**, **text/xml**, or **application/json**. |
   +--------------+--------+-------------------------------------------------------------------------------------------------------------------+
   | content      | String | Configure the page content based on the value for **content_type**.                                               |
   +--------------+--------+-------------------------------------------------------------------------------------------------------------------+

Example
-------

**www.a.com** is used as an example.

Response example

.. code-block::

   {
             "id": "388a7789d55b41d1918b3088a8f1e7f3",
             "hostname": "www.a.com",

             "cname": "3249d21e5eb34d21be12fdc817fcb67d.waf.cloud.com",
             "txt_code": "3249d21e5eb34d21be12fdc817fcb67d",
             "sub_domain": "3249d21e5eb34d21be12fdc817fcb67d.www.a.com",
             "policy_id": "xxxxxxxxxxxxxx",
             "certificate_id": "xxxxxxxxxxxxxxxxxxx",
             "protect_status": 0,
             "access_status": 0,
             "protocol": "HTTP,HTTPS",

             "server": [
                {"client_protocol": "HTTPS", "server_protocol":"HTTP", "address":"X.X.X.X.", "port":443},
                {"client_protocol": "HTTP", "server_protocol":"HTTP", "address":"X.X.X.X", "port":80}
             ],
            "proxy": true,
            "sip_header_name": "default",
            "sip_header_list": ["X-Forwarded-For"],
            "timestamp": 1499817600,
            "block_page" : {
            "template" : "default"
             },
            "cipher": "cipher_1",
            "tls": "TLS v1.1"
   }

Status Code
-----------

:ref:`Table 5 <waf_02_0014__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0014__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 5** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
