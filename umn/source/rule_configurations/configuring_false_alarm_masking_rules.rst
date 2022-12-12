:original_name: waf_01_0016.html

.. _waf_01_0016:

Configuring False Alarm Masking Rules
=====================================

This section describes how to configure false alarm masking rules.

You can add false alarms to the whitelist and ignore certain event IDs (for example, skip XSS check for a specified URL).

False alarm masking only applies to events logged by built-in basic web protection rules. If you want to mask events logged by custom rules, delete the rules.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0016__waf_01_0008_fig164792010154510>` shows an example.

   .. _waf_01_0016__waf_01_0008_fig164792010154510:

   .. figure:: /_static/images/en-us_image_0000001321794478.png
      :alt: **Figure 1** Entrance to the domain configuration page

      **Figure 1** Entrance to the domain configuration page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the desired domain name. In the **Operation** column, click **Configure Policy**. :ref:`Figure 2 <waf_01_0016__waf_01_0008_fig16197124372015>` shows an example.

   .. _waf_01_0016__waf_01_0008_fig16197124372015:

   .. figure:: /_static/images/en-us_image_0000001321314926.png
      :alt: **Figure 2** Protection configuration page

      **Figure 2** Protection configuration page

#. .. _waf_01_0016__li58723545102836:

   In the **False Alarm Masking** area, specify **Status**. After the configuration completes, in the upper right corner of the **Protection Status** list, click **Save**. In the displayed dialog box, click **Yes** to save the settings. If you do not want to save the settings, click **Cancel**. :ref:`Figure 3 <waf_01_0016__fig44151977327>` shows an example.

   .. _waf_01_0016__fig44151977327:

   .. figure:: /_static/images/en-us_image_0000001372714409.png
      :alt: **Figure 3** False Alarm Masking configuration area

      **Figure 3** False Alarm Masking configuration area

#. Click **Customize Rule**. On the displayed **False Alarm Masking** page, click **Add Rule** in the upper left corner. :ref:`Figure 4 <waf_01_0016__fig106802271583>` shows an example.

   .. note::

      If you do not click **Save** after changing **Status** in :ref:`Step 5 <waf_01_0016__li58723545102836>`, a **Warning** dialog box is displayed when you click **Customize Rule**.

      -  Click **Yes** to cancel the previous settings.
      -  Click **No** and then **Save** to save the settings.

   .. _waf_01_0016__fig106802271583:

   .. figure:: /_static/images/en-us_image_0000001321314894.png
      :alt: **Figure 4** Add Rule (False Alarm Masking)

      **Figure 4** Add Rule (False Alarm Masking)

   .. note::

      In the upper part of the protection rule list, click **Quota details** to view the quota of protection rules.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0016__table4696626918715>`. :ref:`Figure 5 <waf_01_0016__fig14415389105236>` shows an example.

   .. note::

      False alarm masking only applies to events logged by built-in basic web protection rules. If you want to mask events logged by custom rules, delete the rules.

   .. _waf_01_0016__fig14415389105236:

   .. figure:: /_static/images/en-us_image_0000001321634494.png
      :alt: **Figure 5** Adding a false alarm masking rule

      **Figure 5** Adding a false alarm masking rule

   .. _waf_01_0016__table4696626918715:

   .. table:: **Table 1** Rule parameters

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                 | Example Value                                                                                            |
      +=======================+=============================================================================================================================================================================================================================================================+==========================================================================================================+
      | Path                  | Misreported URL excluding a domain name                                                                                                                                                                                                                     | **/admin**                                                                                               |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       | -  Prefix match: The path ending with \* indicates that the path is used as a prefix. For example, if the path to be protected is **/admin/test.php** or **/adminabc**, set **Path** to **/admin\***.                                                       | For example, if the URL to be protected is **http://www.example.com/admin**, set **Path** to **/admin**. |
      |                       | -  Exact match: The path to be entered must match the path to be protected. If the path to be protected is **/admin**, set **Path** to **/admin**.                                                                                                          |                                                                                                          |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       | .. note::                                                                                                                                                                                                                                                   |                                                                                                          |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       |    -  The path supports prefix and exact matches only and does not support regular expressions.                                                                                                                                                             |                                                                                                          |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, the WAF engine converts **///** to **/**.                                                                                              |                                                                                                          |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+
      | Event ID              | ID of the built-in rule corresponding to the attack event for which the false alarm masking is to be performed                                                                                                                                              | 000006                                                                                                   |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       | This value consists of six digits and cannot be empty.                                                                                                                                                                                                      |                                                                                                          |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       | .. note::                                                                                                                                                                                                                                                   |                                                                                                          |
      |                       |                                                                                                                                                                                                                                                             |                                                                                                          |
      |                       |    To obtain the event ID, go to the **Events** page, select the **Search** tab, locate the row where the attack event resides, and click **Handle False Alarm** in the **Operation** column. You can then obtain the event ID on the displayed dialog box. |                                                                                                          |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+

#. Click **OK**. If **Rule added successfully** is displayed in the upper right corner, the rule is added.

   To delete the added rule, click **Delete** in the row containing the target rule.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
