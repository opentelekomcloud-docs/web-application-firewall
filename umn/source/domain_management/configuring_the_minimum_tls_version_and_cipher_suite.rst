:original_name: waf_01_0093.html

.. _waf_01_0093:

Configuring the Minimum TLS Version and Cipher Suite
====================================================

The Transport Layer Security (TLS) protocol provides confidentiality and integrity of data sent between applications over the Internet. HTTPS is a network protocol constructed based on TLS and HTTP for encrypted transmission and identity authentication. When **Client Protocol** for a domain name to be protected is set to **HTTPS**, you can use WAF to set the minimum TLS version and cipher suite (a set of cryptographic algorithms) for the domain name. All requests using the TLS earlier than the minimum TLS version cannot access the protected domain names so that your service is secured.

If **Client Protocol** for the domain name to be protected is set to **HTTP**, TLS is not involved. In this case, skip this section.

TLS v1.1 and the default cipher suite are configured by default in WAF for general security. To better protect your services, you are advised to set the minimum TLS version to a later version and cipher suite to the one having higher security.

Prerequisites
-------------

-  The domain name to be protected has been added.
-  **Client Protocol** is set to **HTTPS** for the protected domain name.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall** > **Domains**. :ref:`Figure 1 <waf_01_0093__fig1174417294716>` shows an example.

   .. _waf_01_0093__fig1174417294716:

   .. figure:: /_static/images/en-us_image_0000001321794518.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Name** column, click the target domain name to go to the basic information page.

#. Click |image2| next to the cipher suite name in the row where **TLS Configuration** locates.


   .. figure:: /_static/images/en-us_image_0000001321474658.png
      :alt: **Figure 2** Modifying TLS configurations

      **Figure 2** Modifying TLS configurations

#. In the **TLS Configuration** dialog box, select the minimum TLS version and cipher suite. :ref:`Table 1 <waf_01_0093__table205284916443>` describes the parameters.


   .. figure:: /_static/images/en-us_image_0000001321794530.png
      :alt: **Figure 3** TLS Configuration

      **Figure 3** TLS Configuration

   .. _waf_01_0093__table205284916443:

   .. table:: **Table 1** TLS configuration parameters

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                             |
      +===================================+=========================================================================================================================================================================+
      | Minimum TLS Version               | Minimum TLS version for accessing the protected domain name                                                                                                             |
      |                                   |                                                                                                                                                                         |
      |                                   | -  TLS v1.1: Requests using TLS v1.1 or later can access the domain name.                                                                                               |
      |                                   | -  TLS v1.2: Requests using TLS v1.2 or later can the access domain name.                                                                                               |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Cipher Suite                      | -  **Default cipher suite**: Good browser compatibility, most clients supported, sufficient for most scenarios                                                          |
      |                                   | -  **Cipher suite 1**: Recommended configuration, best combination of compatibility and security                                                                        |
      |                                   | -  **Cipher suite 2**: Strict compliance with forward secrecy requirements of PCI DSS and excellent protection, but older browsers may be unable to access the websites |
      |                                   | -  **Cipher suite 3**: Support for ECDHE, DHE-GCM, and RSA-AES-GCM algorithms but not CBC                                                                               |
      |                                   |                                                                                                                                                                         |
      |                                   | .. important::                                                                                                                                                          |
      |                                   |                                                                                                                                                                         |
      |                                   |    NOTICE:                                                                                                                                                              |
      |                                   |    Cipher suite 2 is not supported if TLS v1.1 is selected.                                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372554657.png
