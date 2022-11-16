:original_name: waf_01_0012.html

.. _waf_01_0012:

Configuring Blacklist or Whitelist Rules
========================================

This section describes how to configure blacklist or whitelist rules to block or allow specific IP addresses or address ranges.

Blacklist and Whitelist only takes effect for specified domain names.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0012__waf_01_0008_fig164792010154510>` shows an example.

   .. _waf_01_0012__waf_01_0008_fig164792010154510:

   .. figure:: /_static/images/en-us_image_0000001321794478.png
      :alt: **Figure 1** Entrance to the domain configuration page

      **Figure 1** Entrance to the domain configuration page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the desired domain name. In the **Operation** column, click **Configure Policy**. :ref:`Figure 2 <waf_01_0012__waf_01_0008_fig16197124372015>` shows an example.

   .. _waf_01_0012__waf_01_0008_fig16197124372015:

   .. figure:: /_static/images/en-us_image_0000001321314926.png
      :alt: **Figure 2** Protection configuration page

      **Figure 2** Protection configuration page

#. .. _waf_01_0012__li33536816115011:

   In the **Blacklist and Whitelist** area, specify **Status**. After the configuration completes, in the upper right corner of the **Protection Status** list, click **Save**. In the displayed dialog box, click **Yes** to save the settings. If you do not want to save the settings, click **Cancel**. :ref:`Figure 3 <waf_01_0012__fig0358162863015>` shows an example.

   .. _waf_01_0012__fig0358162863015:

   .. figure:: /_static/images/en-us_image_0000001321474594.png
      :alt: **Figure 3** Blacklist and Whitelist configuration area

      **Figure 3** Blacklist and Whitelist configuration area

#. Click **Customize Rule**. On the displayed **Blacklist and Whitelist** page, click **Add Rule** in the upper left corner. :ref:`Figure 4 <waf_01_0012__fig337411411269>` shows an example.

   .. note::

      If you do not click **Save** after changing **Status** in :ref:`Step 5 <waf_01_0012__li33536816115011>`, a **Warning** dialog box is displayed when you click **Customize Rule**.

      -  Click **Yes** to cancel the previous settings.
      -  Click **No** and then **Save** to save the settings.

   .. _waf_01_0012__fig337411411269:

   .. figure:: /_static/images/en-us_image_0000001321474598.png
      :alt: **Figure 4** Add Rule (Blacklist and Whitelist)

      **Figure 4** Add Rule (Blacklist and Whitelist)

   .. note::

      In the upper part of the protection rule list, click **Quota details** to view the quota of protection rules.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0012__table27095251482>`. :ref:`Figure 5 <waf_01_0012__fig22686744114137>` shows an example.

   .. _waf_01_0012__fig22686744114137:

   .. figure:: /_static/images/en-us_image_0000001321794470.png
      :alt: **Figure 5** Adding a blacklist or whitelist rule

      **Figure 5** Adding a blacklist or whitelist rule

   .. _waf_01_0012__table27095251482:

   .. table:: **Table 1** Rule parameters

      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                    | Example Value         |
      +=======================+================================================================================================+=======================+
      | IP Address or Range   | -  IP address: IP address to be added to the blacklist or whitelist                            | -  XXX.XXX.1.1        |
      |                       | -  IP address range: IP address and subnet mask defining a network segment                     | -  XXX.XXX.1.0/24     |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Protective Action     | If **IP Address or Range** is to be added to a whitelist, set this parameter to **Whitelist**. | **Blacklist**         |
      |                       |                                                                                                |                       |
      |                       | If **IP Address or Range** is to be added to a blacklist, set this parameter to **Blacklist**. |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   -  To modify the added rule, click **Modify** in the row containing the target rule.
   -  To delete the added rule, click **Delete** in the row containing the target rule.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
