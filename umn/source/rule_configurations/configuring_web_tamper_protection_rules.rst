:original_name: waf_01_0014.html

.. _waf_01_0014:

Configuring Web Tamper Protection Rules
=======================================

This section describes how to configure web tamper protection (WTP) rules.

You can configure these rules to prevent a static web page from being tampered with.

WTP has the following advantages:

-  Quicker response to requests

   After a WTP rule is configured, WAF caches the static web page on the server. When receiving a request from a web visitor, WAF returns the cached page to the visitor.

-  Web tamper protection

   If an attacker modifies a static web page on the server, WAF returns the cached original web page to web visitors, ensuring that visitors never access tampered-with pages.

   WAF can randomly extract a request from a web visitor to compare the requested page with the web page on the server. If WAF detects that the page has been tampered with, it notifies the user by SMS or email. For details about alarm notification settings, see :ref:`Enabling Alarm Notification <waf_01_0019>`.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0014__waf_01_0008_fig164792010154510>` shows an example.

   .. _waf_01_0014__waf_01_0008_fig164792010154510:

   .. figure:: /_static/images/en-us_image_0000001321794478.png
      :alt: **Figure 1** Entrance to the domain configuration page

      **Figure 1** Entrance to the domain configuration page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the desired domain name. In the **Operation** column, click **Configure Policy**. :ref:`Figure 2 <waf_01_0014__waf_01_0008_fig16197124372015>` shows an example.

   .. _waf_01_0014__waf_01_0008_fig16197124372015:

   .. figure:: /_static/images/en-us_image_0000001321314926.png
      :alt: **Figure 2** Protection configuration page

      **Figure 2** Protection configuration page

#. .. _waf_01_0014__li58723545102836:

   In the **Web Tamper Protection** area, specify **Status**. After the configuration completes, in the upper right corner of the **Protection Status** list, click **Save**. In the displayed dialog box, click **Yes** to save the settings. If you do not want to save the settings, click **Cancel**. :ref:`Figure 3 <waf_01_0014__fig10572033304>` shows an example.

   .. _waf_01_0014__fig10572033304:

   .. figure:: /_static/images/en-us_image_0000001372554601.png
      :alt: **Figure 3** Web Tamper Protection configuration area

      **Figure 3** Web Tamper Protection configuration area

#. Click **Customize Rule**. On the displayed **Web Tamper Protection** page, click **Add Rule** in the upper left corner. :ref:`Figure 4 <waf_01_0014__fig13289432775>` shows an example.

   .. note::

      If you do not click **Save** after changing **Status** in :ref:`Step 5 <waf_01_0014__li58723545102836>`, a **Warning** dialog box is displayed when you click **Customize Rule**.

      -  Click **Yes** to cancel the previous settings.
      -  Click **No** and then **Save** to save the settings.

   .. _waf_01_0014__fig13289432775:

   .. figure:: /_static/images/en-us_image_0000001321634498.png
      :alt: **Figure 4** Add Rule (Web Tamper Protection)

      **Figure 4** Add Rule (Web Tamper Protection)

   .. note::

      In the upper part of the protection rule list, click **Quota details** to view the quota of protection rules.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0014__table2046816299203>`. :ref:`Figure 5 <waf_01_0014__fig13729129125420>` shows an example.

   .. _waf_01_0014__fig13729129125420:

   .. figure:: /_static/images/en-us_image_0000001321474590.png
      :alt: **Figure 5** Adding a web tamper protection rule

      **Figure 5** Adding a web tamper protection rule

   .. _waf_01_0014__table2046816299203:

   .. table:: **Table 1** Rule parameters

      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+
      | Parameter             | Description                                                                                                                                                    | Example Value                                                                                            |
      +=======================+================================================================================================================================================================+==========================================================================================================+
      | Domain Name           | Domain name to be protected                                                                                                                                    | **www.example.com**                                                                                      |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+
      | Path                  | URL excluding a domain name                                                                                                                                    | **/admin**                                                                                               |
      |                       |                                                                                                                                                                |                                                                                                          |
      |                       | .. note::                                                                                                                                                      | For example, if the URL to be protected is **http://www.example.com/admin**, set **Path** to **/admin**. |
      |                       |                                                                                                                                                                |                                                                                                          |
      |                       |    -  The path does not support regular expressions.                                                                                                           |                                                                                                          |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, the WAF engine converts **///** to **/**. |                                                                                                          |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   -  In the event of changes on the protected web page, WAF needs to re-cache the web page content. In this case, click **Update Cache** in the row containing the target rule.
   -  To delete the added rule, click **Delete** in the row containing the target rule.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
