:original_name: waf_01_0094.html

.. _waf_01_0094:

Modifying the Alarm Page
========================

If a visitor triggers block by WAF, the **Default** block page of WAF is returned by default. You can also configure **Custom** or **Redirection** for the block page to be returned as required.

-  **Custom**: The content of the text/html, text/xml, and application/json pages can be configured on the custom block page to be returned.
-  **Redirection**: The root domain name of the redirection address must be the same as the currently protected domain name, including a wildcard domain name. For example:

   -  If the protected domain name is **www.example.com** and the port number is **8080**, the redirection URL can be set to **http://www.example.com:8080/error.html**.
   -  If the protected wildcard domain name is **\*.example.com** and the port number is **8080**, the redirection URL can be set to **http://*.example.com:8080/error.html**.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been added.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall** > **Domains**. :ref:`Figure 1 <waf_01_0094__waf_01_0093_fig1174417294716>` shows an example.

   .. _waf_01_0094__waf_01_0093_fig1174417294716:

   .. figure:: /_static/images/en-us_image_0000001321794518.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Name** column, click the target domain name to go to the basic information page.

#. Click |image2| next to the template name in the row where **Alarm Page** locates.


   .. figure:: /_static/images/en-us_image_0000001321634558.png
      :alt: **Figure 2** Modifying Alarm Page

      **Figure 2** Modifying Alarm Page

#. In the **Alarm Page** dialog box, select a template in the **Page Template** field.

   -  If **Default** is selected for **Page Template**, the block page with the built-in HTTP return code 418 is returned by default.


      .. figure:: /_static/images/en-us_image_0000001372795289.png
         :alt: **Figure 3** Default alarm page

         **Figure 3** Default alarm page

   -  If **Custom** is selected for **Page Template**, configure the parameters as needed. :ref:`Table 1 <waf_01_0094__table292835123913>` describes the parameters.


      .. figure:: /_static/images/en-us_image_0000001321314966.png
         :alt: **Figure 4** Custom alarm page

         **Figure 4** Custom alarm page

      .. _waf_01_0094__table292835123913:

      .. table:: **Table 1** Parameters for the custom alarm page

         +------------------+-------------------------------------------------------------------------------------+
         | Parameter        | Description                                                                         |
         +==================+=====================================================================================+
         | HTTP Return Code | Return code configured on a custom page                                             |
         +------------------+-------------------------------------------------------------------------------------+
         | Block Page Type  | The options are **text/html**, **text/xml**, and **application/json**.              |
         +------------------+-------------------------------------------------------------------------------------+
         | Page Content     | Configure the page content based on the page type specified in **Block Page Type**. |
         +------------------+-------------------------------------------------------------------------------------+

   -  If **Redirection** is selected for **Page Template**, configure the redirection URL as prompted.

      The root domain name of the redirection URL must be the same as the currently protected domain name, including a wildcard domain name. Examples:

      -  If the protected domain name is **www.example.com** and the port number is **8080**, the redirection URL can be set to **http://www.example.com:8080/error.html**.
      -  If the protected wildcard domain name is **\*.example.com** and the port number is **8080**, the redirection URL can be set to **http://*.example.com:8080/error.html**.


      .. figure:: /_static/images/en-us_image_0000001321794510.png
         :alt: **Figure 5** Redirection alarm page

         **Figure 5** Redirection alarm page

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372554657.png
