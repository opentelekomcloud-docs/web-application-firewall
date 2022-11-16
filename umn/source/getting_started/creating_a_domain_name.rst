:original_name: waf_01_0002.html

.. _waf_01_0002:

Creating a Domain Name
======================

This section describes how to create a domain name and connect it to WAF. After connecting a domain name, WAF works as a reverse proxy between the client and server. The real IP address of the server is hidden and only the IP address of WAF is visible to web visitors.

Prerequisites
-------------

Login credentials have been obtained.

Domain Configuration Principle
------------------------------

-  :ref:`Figure 1 <waf_01_0002__en-us_topic_0110861354_fig030435404518>` shows how WAF works if the web server is using a proxy.

   .. _waf_01_0002__en-us_topic_0110861354_fig030435404518:

   .. figure:: /_static/images/en-us_image_0000001321794498.png
      :alt: **Figure 1** A proxy configured

      **Figure 1** A proxy configured

   -  DNS resolves the domain name to the IP address of a proxy (such as AAD) before your site is moved to WAF. In this case, the traffic passes through the proxy and then the proxy routes the traffic back to the origin server.
   -  After your site is moved to WAF, DNS resolves your domain name to the access address of WAF. In this way, the proxy forwards the traffic to WAF. WAF then filters out illegitimate traffic and only routes legitimate traffic back to the origin server.

      #. Change the back-to-source IP address of the proxy to the access address of WAF.
      #. Add a WAF subdomain name and TXT record to the DNS records of your DNS provider.

-  :ref:`Figure 2 <waf_01_0002__en-us_topic_0110861354_fig1624119317528>` shows how WAF works if the web server does not use a proxy.

   .. _waf_01_0002__en-us_topic_0110861354_fig1624119317528:

   .. figure:: /_static/images/en-us_image_0000001321634566.png
      :alt: **Figure 2** No proxy configured

      **Figure 2** No proxy configured

   -  DNS resolves your domain name to the origin server IP address before your site is connected to WAF. Therefore, web visitors can directly access the server.
   -  After your website is connected to WAF, DNS resolves your domain name to the CNAME record of WAF. In this way, the traffic passes through WAF. WAF then filters out illegitimate traffic and only routes legitimate traffic back to the origin server.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**.

#. In the navigation pane, choose **Domains**. :ref:`Figure 3 <waf_01_0002__fig15593418182219>` shows an example.

   .. _waf_01_0002__fig15593418182219:

   .. figure:: /_static/images/en-us_image_0000001321634542.png
      :alt: **Figure 3** Domains

      **Figure 3** Domains

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the upper right corner of the domain name list, click **Create Domain**.

#. On the **Create Domain** page, specify required parameters by referring to :ref:`Table 1 <waf_01_0002__table7692122554811>`. :ref:`Figure 4 <waf_01_0002__fig175731754141418>` shows an example.

   .. _waf_01_0002__fig175731754141418:

   .. figure:: /_static/images/en-us_image_0000001372914993.png
      :alt: **Figure 4** Configuring basic settings

      **Figure 4** Configuring basic settings

   .. _waf_01_0002__table7692122554811:

   .. table:: **Table 1** Parameter description

      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Example Value                            |
      +=======================+==============================================================================================================================================================================================================================================================================================================================================================================================================================================================================+==========================================+
      | Domain Name           | A domain name to be protected, which can be a single domain name or a wildcard domain name.                                                                                                                                                                                                                                                                                                                                                                                  | Single domain name: **www.example.com**  |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | -  Single domain name: For example, *www.example.com*                                                                                                                                                                                                                                                                                                                                                                                                                        | Wildcard domain name: **\*.example.com** |
      |                       | -  Wildcard domain name                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       |    -  If the server IP address of each subdomain name is the same, enter a wildcard domain name. For example, **\*.example.com**.                                                                                                                                                                                                                                                                                                                                            |                                          |
      |                       |    -  If the server IP addresses of subdomain names are different, add subdomain names as single domain names one by one.                                                                                                                                                                                                                                                                                                                                                    |                                          |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Non-standard Port     | Set this parameter only if **Non-standard Port** is selected.                                                                                                                                                                                                                                                                                                                                                                                                                | **4443**                                 |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | -  If **Client Protocol** is **HTTP**, WAF protects the standard port 80 only by default. To protect a non-standard port, select **Non-standard Port** and then select a value from the **Non-standard Port** drop-down list.                                                                                                                                                                                                                                                |                                          |
      |                       | -  If **Client Protocol** is **HTTPS**, WAF protects the standard port 443 by default. To protect a non-standard port, select **Non-standard Port** and then select a value from the **Non-standard Port** drop-down list.                                                                                                                                                                                                                                                   |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | For details about non-standard ports supported by WAF, see :ref:`Web Application Firewall <waf_01_0045>`.                                                                                                                                                                                                                                                                                                                                                                    |                                          |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Server Configuration  | Address configurations of the web server, including **Client Protocol**, **Server Protocol**, **Server Address**, and **Server Port**.                                                                                                                                                                                                                                                                                                                                       | **Client Protocol**: **HTTPS**           |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | -  **Client Protocol**: Type of client protocol. The options are **HTTP** and **HTTPS**.                                                                                                                                                                                                                                                                                                                                                                                     | **Server Protocol**: **HTTP**            |
      |                       | -  **Server Protocol**: Protocol used by WAF to forward requests to the server. The options are **HTTP** and **HTTPS**.                                                                                                                                                                                                                                                                                                                                                      |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | **Server Address**: *XXX.XXX.1.1*        |
      |                       |    .. note::                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | **Server Port**: **80**                  |
      |                       |       For details about configuring **Client Protocol** and **Server Protocol**, see :ref:`Rules for Configuring Client Protocol and Server Protocol <waf_01_0002__section645014318511>`.                                                                                                                                                                                                                                                                                    |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | -  **Server Address**: IP address (generally the A record before the domain name is connected to WAF) or domain name (generally the CNAME before the domain name is connected to WAF) of the web server that a client accesses                                                                                                                                                                                                                                               |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       |    .. note::                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       |       Web Application Firewall (WAF) does not support health check. If you want to use health check, use WAF along with Elastic Load Balancing (ELB). For details about how to configure ELB, see `Backend Server (Enhanced Load Balancer) <https://docs.otc.t-systems.com/en-us/usermanual/elb/en-us_topic_0052569729.html>`__. After ELB is configured, the elastic IP address (EIP) of ELB is used as the value of **Server Address** to connect to WAF for health check. |                                          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |
      |                       | -  **Server Port**: Port number used by the web server                                                                                                                                                                                                                                                                                                                                                                                                                       |                                          |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Certificate Name      | If **Client Protocol** is **HTTPS**, select an existing certificate or upload a new certificate. For details about how to upload a new certificate, see :ref:`Step 7 <waf_01_0002__li1098265701316>`.                                                                                                                                                                                                                                                                        | None                                     |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------+

#. .. _waf_01_0002__li1098265701316:

   Upload a new certificate if **Client Protocol** is **HTTPS**.

   a. Click **Upload Certificate**. In the displayed **Upload Certificate** dialog box, enter the certificate name and paste the certificate file and private key to the corresponding text boxes. :ref:`Figure 5 <waf_01_0002__fig7846148397>` shows an example.

      .. _waf_01_0002__fig7846148397:

      .. figure:: /_static/images/en-us_image_0000001321314946.png
         :alt: **Figure 5** Uploading a certificate

         **Figure 5** Uploading a certificate

      .. note::

         -  In the **Upload Certificate** dialog box, click **Quota details** to view the certificate quota.
         -  WAF encrypts and saves the private key to keep it safe.
         -  For details about the combination sequence of a certificate chain, see :ref:`How Do I Fix an Incomplete Certificate Chain? <waf_01_0082>`

      Currently, only .pem certificates are supported. If the certificate is not in .pem format, convert it into a .pem certificate by referring to :ref:`Table 2 <waf_01_0002__table1184924815910>` before uploading.

      .. _waf_01_0002__table1184924815910:

      .. table:: **Table 2** Certificate conversion commands

         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
         | Format                            | Usage (Using `OpenSSL <https://www.openssl.org/>`__)                                                                       |
         +===================================+============================================================================================================================+
         | CER/CRT                           | Rename the **cert.crt** certificate file to **cert.pem**.                                                                  |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
         | PFX                               | -  Obtain a private key. For example, run the following command to convert **cert.pfx** into **cert.key**:                 |
         |                                   |                                                                                                                            |
         |                                   |    **openssl pkcs12 -in cert.pfx -nocerts -out cert.key -nodes**                                                           |
         |                                   |                                                                                                                            |
         |                                   | -  Obtain a certificate. For example, run the following command to convert **cert.pfx** into **cert.pem**:                 |
         |                                   |                                                                                                                            |
         |                                   |    **openssl** **pkcs12** **-in** **cert.pfx** **-nokeys** **-out** **cert.pem**                                           |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
         | P7B                               | #. Convert a certificate. For example, run the following command to convert **cert.p7b** into **cert.cer**:                |
         |                                   |                                                                                                                            |
         |                                   |    **openssl** **pkcs7** **-print_certs** **-in** **cert.p7b** **-out** **cert.cer**                                       |
         |                                   |                                                                                                                            |
         |                                   | #. Rename certificate file **cert.cer** to **cert.pem**.                                                                   |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
         | DER                               | -  Obtain a private key. For example, run the following command to convert ****privatekey.der**** into **privatekey.pem**: |
         |                                   |                                                                                                                            |
         |                                   |    **openssl** **rsa** **-inform** **DER** **-outform** **PEM** **-in** **privatekey.der** **-out** **privatekey.pem**     |
         |                                   |                                                                                                                            |
         |                                   | -  Obtain a certificate. As an example, run the following command to convert **cert.cer** into **cert.pem**:               |
         |                                   |                                                                                                                            |
         |                                   |    **openssl** **x509** **-inform** **der** **-in** **cert.cer** **-out cert.pem**                                         |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+

   b. Click **OK**.

#. Set **Proxy Configured**. The default value is **No**.

   .. important::

      The bypassed option is unavailable during proxy use.

   -  If your website is using a proxy such as Advanced Anti-DDoS (AAD), Content Delivery Network (CDN), or any other cloud acceleration service, select **Yes** so that the WAF security policies take effect on the origin server IP address. If this parameter is **No**, WAF cannot obtain the real IP address requested by a web visitor.

      .. note::

         If a proxy such as CDN is used, WAF obtains the real source IP address of a client from the HTTP Header **X-Forwarded-For** by default. If the proxy does not use **X-Forwarded-For** to identify the real source IP address of a client, click |image2| next to **X-Forwarded-For** in the row of **Source IP Header**. In the dialog box displayed, select an existing source IP header or select **Custom** and enter a source IP header.

   -  If your website does not use a proxy, select **No**.

#. (Optional) Configure a tag.

   You can select an existing tag key and tag value from the **Tag key** and **Tag value** drop-down lists or click **View predefined tags** to create a tag on the TMS console.

#. Click **Create Now**. In the upper right corner of the page, if **Domain created successfully** is displayed, the domain name is created.

   .. note::

      If you do not want to connect the domain name to WAF in this step, click **Next**. Then click **Finish**. **DNS** is displayed as **Unconfigured**. Later, you can refer to :ref:`Connecting a Domain Name <waf_01_0079>` to finish domain connection.

   -  If a proxy such as CDN or AAD is used, you need to configure the back-to-source IP address, subdomain name, and TXT record. :ref:`Figure 6 <waf_01_0002__en-us_topic_0270895331_fig450482413592>` shows an example.

      .. _waf_01_0002__en-us_topic_0270895331_fig450482413592:

      .. figure:: /_static/images/en-us_image_0000001156082152.png
         :alt: **Figure 6** Connecting a domain name

         **Figure 6** Connecting a domain name

      a. Configure the back-to-source IP address of the proxy on the website.

         For example, change the back-to-source IP address of CDN or AAD to the WAF IP address by following the instructions shown in :ref:`Figure 6 <waf_01_0002__en-us_topic_0270895331_fig450482413592>`.

      b. Configure **Subdomain Name** and **TXT Record**.

         Add a subdomain name and TXT record to the DNS records of your DNS provider by following the instructions shown in :ref:`Figure 6 <waf_01_0002__en-us_topic_0270895331_fig450482413592>`.

      .. important::

         The high availability of our system, which is based on multi-AZ deployments to support both active-active and disaster recovery, relies on the WAF CNAME record.

   -  If no proxy is used, the CNAME record must be configured. :ref:`Figure 7 <waf_01_0002__en-us_topic_0270895331_fig84741317702>` shows an example.

      .. _waf_01_0002__en-us_topic_0270895331_fig84741317702:

      .. figure:: /_static/images/en-us_image_0000001204042733.png
         :alt: **Figure 7** Connecting a domain name (CNAME record)

         **Figure 7** Connecting a domain name (CNAME record)

      a. Go to your DNS provider and configure the CNAME record. For details, contact your DNS provider.

         .. important::

            The high availability of our system, which is based on multi-AZ deployments to support both active-active and disaster recovery, relies on the WAF CNAME record. Therefore,

            #. Do not modify the hosts file. Add the CNAME record directly to the DNS records of your DNS provider.
            #. Do not use the A record to replace the CNAME record.

         The CNAME binding method of some common DNS providers is listed for your reference. If the following configuration is inconsistent with the actual configuration, rely on information provided by the DNS providers.

         #. Log in to the management console of the DNS provider.
         #. Go to the domain resolution record page.
         #. Set the CNAME resolution record.

            -  Set the record type to **CNAME**.
            -  Generally, enter the domain name prefix in the host record. For example, if the protected domain name is **admin.demo.com**, enter **admin** in the host record.
            -  The record value is the CNAME generated by WAF.
            -  Resolution line: keep the default value **TTL**.

         #. Click **Save**.

         .. important::

            The preceding resolution methods are provided by third parties. This document does not control or assume responsibility for any third party content, including but not limited to its accuracy, compatibility, reliability, availability, legitimacy, appropriateness, performance, non-infringement, or status update, unless otherwise specified in this document.

      b. Verify that the CNAME has been configured.

         #. In Windows, choose **Start** > **Run**. Then enter **cmd** and press **Enter**.

         #. Run the following command to query the CNAME. If the configured CNAME is displayed, the configuration is successful.

            **nslookup www.**\ *domain*\ **.com**

#. After the domain name is connected to WAF, click **Next**.

#. Click **Finish**.

   You can view the DNS status and mode of the domain name in the domain list.

   .. note::

      -  If your web server is using other firewalls, disable the firewalls or whitelist the WAF IP address ranges.
      -  If your web server is using personal security software, replace it with enterprise security software and whitelist the WAF IP address ranges.
      -  If a domain name has been connected to WAF, **DNS** should be **Normal**. If **DNS** is **Unconfigured**, choose **More > Check DNS** in the **Operation** column of the target domain name to check the DNS status. If the problem persists, perform domain connection again by referring to :ref:`What Should I Do If the DNS Status Is Unconfigured? <waf_01_0056>`
      -  After a domain name is created, WAF protection is enabled by default. The mode of Basic Web Protection is **Log only** (detected attacks are only logged but not blocked.). WAF creates a CC attack protection rule for the domain name by default. The rule can be modified but cannot be deleted. **Rate Limit** in the rule is 500 requests/5 seconds by default and it can be adjusted up to 10000 requests/5 seconds. If you want a higher rate limit than the maximum value, contact the administrator.

.. _waf_01_0002__section645014318511:

Rules for Configuring Client Protocol and Server Protocol
---------------------------------------------------------

WAF provides various protocol types. If your website is www.example.com, WAF provides the following four access modes:

-  HTTP mode. :ref:`Figure 8 <waf_01_0002__fig53041342142615>` shows an example.

   .. _waf_01_0002__fig53041342142615:

   .. figure:: /_static/images/en-us_image_0000001372914989.png
      :alt: **Figure 8** HTTP mode

      **Figure 8** HTTP mode

   .. important::

      This configuration allows web visitors to access your website over HTTP only. If they access over HTTPS, they receive the 302 Found code and are redirected to http://www.example.com.

-  HTTPS mode. This configuration allows web visitors to access your website over HTTPS only. If they access over HTTP, they are redirected to https://www.example.com. :ref:`Figure 9 <waf_01_0002__fig7444410153315>` shows an example.

   .. _waf_01_0002__fig7444410153315:

   .. figure:: /_static/images/en-us_image_0000001372795277.png
      :alt: **Figure 9** HTTPS mode

      **Figure 9** HTTPS mode

   .. important::

      -  If web visitors access your website over HTTPS, the website returns a successful response.
      -  If web visitors access your website over HTTP, they receive the 302 Found code and are directed to https://www.example.com.

-  HTTP and HTTPS mode. :ref:`Figure 10 <waf_01_0002__fig3389134713400>` shows an example.

   .. _waf_01_0002__fig3389134713400:

   .. figure:: /_static/images/en-us_image_0000001321474634.png
      :alt: **Figure 10** HTTP and HTTPS mode

      **Figure 10** HTTP and HTTPS mode

   .. important::

      -  If web visitors access your website over HTTP, the website returns a successful response but no communication between the browser and website is encrypted.
      -  If web visitors access your website over HTTPS, the website returns a successful response and all communications between the browser and website are encrypted.

-  HTTPS/HTTP mode. :ref:`Figure 11 <waf_01_0002__fig11273129104514>` shows an example.

   .. _waf_01_0002__fig11273129104514:

   .. figure:: /_static/images/en-us_image_0000001321474630.png
      :alt: **Figure 11** HTTPS/HTTP mode

      **Figure 11** HTTPS/HTTP mode

   .. important::

      If web visitors access your website over HTTPS, WAF forwards the requests to your origin server over HTTP.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372554657.png
