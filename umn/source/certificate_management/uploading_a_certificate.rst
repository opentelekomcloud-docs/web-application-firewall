:original_name: waf_01_0090.html

.. _waf_01_0090:

Uploading a Certificate
=======================

This section describes how to upload a certificate.

Prerequisites
-------------

Login credentials have been obtained.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**.

#. In the navigation pane, choose **Certificates**. The **Certificates** page is displayed, as shown in :ref:`Figure 1 <waf_01_0090__fig29851531163210>`.

   .. _waf_01_0090__fig29851531163210:

   .. figure:: /_static/images/en-us_image_0000001372795273.png
      :alt: **Figure 1** Certificates

      **Figure 1** Certificates

   .. note::

      In the upper part of the certificate list, click **Quota details** to view the certificate quota.

#. In the upper right corner of the displayed page, click **Upload Certificate**. In the displayed **Upload Certificate** dialog box, enter the certificate name and paste the certificate file and private key to the corresponding text boxes. :ref:`Figure 2 <waf_01_0090__fig682518517383>` shows an example.

   .. _waf_01_0090__fig682518517383:

   .. figure:: /_static/images/en-us_image_0000001321314946.png
      :alt: **Figure 2** Uploading a certificate

      **Figure 2** Uploading a certificate

   .. note::

      -  In the **Upload Certificate** dialog box, click **Quota details** to view the certificate quota.
      -  WAF encrypts and saves the private key to keep it safe.
      -  For details about the combination sequence of a certificate chain, see :ref:`How Do I Fix an Incomplete Certificate Chain? <waf_01_0082>`

   Currently, only .pem certificates are supported. If the certificate is not in .pem format, convert it into a .pem certificate by referring to :ref:`Table 1 <waf_01_0090__waf_01_0002_table1184924815910>` before uploading.

   .. _waf_01_0090__waf_01_0002_table1184924815910:

   .. table:: **Table 1** Certificate conversion commands

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
      | P7B                               | a. Convert a certificate. For example, run the following command to convert **cert.p7b** into **cert.cer**:                |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **pkcs7** **-print_certs** **-in** **cert.p7b** **-out** **cert.cer**                                       |
      |                                   |                                                                                                                            |
      |                                   | b. Rename certificate file **cert.cer** to **cert.pem**.                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+
      | DER                               | -  Obtain a private key. For example, run the following command to convert ****privatekey.der**** into **privatekey.pem**: |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **rsa** **-inform** **DER** **-outform** **PEM** **-in** **privatekey.der** **-out** **privatekey.pem**     |
      |                                   |                                                                                                                            |
      |                                   | -  Obtain a certificate. As an example, run the following command to convert **cert.cer** into **cert.pem**:               |
      |                                   |                                                                                                                            |
      |                                   |    **openssl** **x509** **-inform** **der** **-in** **cert.cer** **-out cert.pem**                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   .. note::

      -  If the number of uploaded certificates reaches the upper limit, delete the certificates that are not associated with any domain names by referring to :ref:`Deleting a Certificate <waf_01_0091>` and then upload a certificate again.
      -  To modify a certificate name, click |image2| next to the target certificate name in the **Certificate Name** column.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372554657.png
