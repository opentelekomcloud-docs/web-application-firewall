:original_name: waf_01_0010.html

.. _waf_01_0010:

Configuring Precise Protection Rules
====================================

This section describes how to configure precise protection rules.

With these rules, WAF allows you to customize combinations of HTTP headers, cookies, URLs, request parameters, and IP addresses, improving defense accuracy.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0010__waf_01_0008_fig164792010154510>` shows an example.

   .. _waf_01_0010__waf_01_0008_fig164792010154510:

   .. figure:: /_static/images/en-us_image_0000001321794478.png
      :alt: **Figure 1** Entrance to the domain configuration page

      **Figure 1** Entrance to the domain configuration page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the desired domain name. In the **Operation** column, click **Configure Policy**. :ref:`Figure 2 <waf_01_0010__waf_01_0008_fig16197124372015>` shows an example.

   .. _waf_01_0010__waf_01_0008_fig16197124372015:

   .. figure:: /_static/images/en-us_image_0000001321314926.png
      :alt: **Figure 2** Protection configuration page

      **Figure 2** Protection configuration page

#. .. _waf_01_0010__li58723545102836:

   In the **Precise Protection** area, specify **Status**. After the configuration completes, in the upper right corner of the **Protection Status** list, click **Save**. In the displayed dialog box, click **Yes** to save the settings. If you do not want to save the settings, click **Cancel**. :ref:`Figure 3 <waf_01_0010__fig275911394277>` shows an example.

   .. _waf_01_0010__fig275911394277:

   .. figure:: /_static/images/en-us_image_0000001372554673.png
      :alt: **Figure 3** Precise Protection configuration area

      **Figure 3** Precise Protection configuration area

#. Click **Customized Rule**. On the displayed page, specify **Detection Mode**. :ref:`Figure 4 <waf_01_0010__fig104318414612>` shows an example.

   .. note::

      If you do not click **Save** after changing **Status** in :ref:`Step 5 <waf_01_0010__li58723545102836>`, a **Warning** dialog box is displayed when you click **Customize Rule**.

      -  Click **Yes** to cancel the previous settings.
      -  Click **No** and then **Save** to save the settings.

   Two detection modes are available:

   -  Instant Detection: WAF immediately ends threat detection and blocks the request that hits the configured precise protection rule.
   -  Full Detection: WAF blocks all requests that hit the configured precise protection rule when it finishes all threat detections.

   The default detection mode is **Instant Detection**. After changing the detection mode, click **Save**.

   .. _waf_01_0010__fig104318414612:

   .. figure:: /_static/images/en-us_image_0000001372915005.png
      :alt: **Figure 4** Setting Detection Mode

      **Figure 4** Setting Detection Mode

#. In the upper left corner of the **Precise Protection** page, click **Add Rule**. :ref:`Figure 5 <waf_01_0010__fig124514224012>` shows an example.

   .. _waf_01_0010__fig124514224012:

   .. figure:: /_static/images/en-us_image_0000001321314982.png
      :alt: **Figure 5** Add Rule (Precise Protection)

      **Figure 5** Add Rule (Precise Protection)

   .. note::

      In the upper part of the protection rule list, click **Quota details** to view the quota of protection rules.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0010__table2299936310457>`. :ref:`Figure 6 <waf_01_0010__fig39459217174738>` shows an example.

   .. _waf_01_0010__fig39459217174738:

   .. figure:: /_static/images/en-us_image_0000001372795305.png
      :alt: **Figure 6** Adding a precise protection rule

      **Figure 6** Adding a precise protection rule

   .. _waf_01_0010__table2299936310457:

   .. table:: **Table 1** Rule parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                                  | Example Value                                       |
      +=======================+==============================================================================================================================================================================================================+=====================================================+
      | Rule Name             | Customizable rule name                                                                                                                                                                                       | waftest                                             |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
      | Protective Action     | Its value is **Block** or **Allow**. The default value is **Block**.                                                                                                                                         | **Block**                                           |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
      | Effective Since       | Select **Immediately** or select **Customize** to set a period. This period can only be a time segment in the future.                                                                                        | **Immediately**                                     |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
      | Condition List        | Click **Add** to add conditions. You must add one to thirty conditions to a protection rule. If more than one condition is added, all the conditions must be met simultaneously for the rule to take effect. | -  **Path** **Include** **/admin**                  |
      |                       |                                                                                                                                                                                                              | -  **User Agent** **Prefix is not** **mozilla/5.0** |
      |                       | -  **Field**                                                                                                                                                                                                 | -  **IP** **Equal to** **192.168.2.3**              |
      |                       | -  **Subfield**: Configure this field only when **Params**, **Cookie**, or **Header** is selected.                                                                                                           | -  **Cookie key1** **Prefix is not** **Nessus**     |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       |    .. important::                                                                                                                                                                                            |                                                     |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       |       NOTICE:                                                                                                                                                                                                |                                                     |
      |                       |       The length of a subfield cannot exceed 2048 bytes. Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                                 |                                                     |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       | -  **Logic**: Select the desired logical relationship from the drop-down list.                                                                                                                               |                                                     |
      |                       | -  **Content**: Enter or select the content of condition matching.                                                                                                                                           |                                                     |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       | .. note::                                                                                                                                                                                                    |                                                     |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       |    For detailed configurations, see :ref:`Table 2 <waf_01_0010__table13543174312394>`.                                                                                                                       |                                                     |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+
      | Priority              | Priority of a rule being executed                                                                                                                                                                            | 50                                                  |
      |                       |                                                                                                                                                                                                              |                                                     |
      |                       | Smaller values correspond to higher priorities. If two rules are assigned with the same priority, the rule added earlier has higher priority.                                                                |                                                     |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------+

   .. _waf_01_0010__table13543174312394:

   .. table:: **Table 2** Condition list configurations

      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | Field                                                                                                                                                                   | Example Subfield | Logic                                                                                                                           | Example Content                                                                           |
      +=========================================================================================================================================================================+==================+=================================================================================================================================+===========================================================================================+
      | **Path**: URL excluding a domain name. This value supports exact match only. For example, if the path to be protected is **/admin**, set **Path** to **/admin**.        | None             | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **/buy/phone/**                                                                           |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **User Agent**: A user agent of the scanner to be protected                                                                                                             | None             | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **Mozilla/5.0 (Windows NT 6.1)**                                                          |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **IP**: An IP address of the visitor to be protected                                                                                                                    | None             | **Equal to** or **Not equal to**                                                                                                | **192.168.2.3**                                                                           |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **Params**: A request parameter to be protected                                                                                                                         | **sttl**         | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **201901150929**                                                                          |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **Cookie**: A small piece of data to identify web visitors                                                                                                              | **name**         | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **Nessus**                                                                                |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **Referer**: A user-defined request resource                                                                                                                            | None             | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **http://www.test.com**                                                                   |
      |                                                                                                                                                                         |                  |                                                                                                                                 |                                                                                           |
      | For example, if the protected path is **/admin/xxx** and you do not want visitors to access the page from **www.test.com**, set **Content** to **http://www.test.com**. |                  |                                                                                                                                 |                                                                                           |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
      | **Header**: A user-defined HTTP header                                                                                                                                  | **Accept**       | **Include**, **Exclude**, **Equal to**, **Not equal to**, **Prefix is**, **Prefix is not**, **Suffix is**, or **Suffix is not** | **text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8** |
      +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+

#. Click **OK**.

   -  To modify the added rule, click **Modify** in the row containing the target rule.
   -  To delete the added rule, click **Delete** in the row containing the target rule.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
