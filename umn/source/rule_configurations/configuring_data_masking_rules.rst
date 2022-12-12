:original_name: waf_01_0017.html

.. _waf_01_0017:

Configuring Data Masking Rules
==============================

This section describes how to configure data masking rules. Data Masking prevents such data as usernames and passwords from being displayed in event logs.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0017__waf_01_0008_fig164792010154510>` shows an example.

   .. _waf_01_0017__waf_01_0008_fig164792010154510:

   .. figure:: /_static/images/en-us_image_0000001321794478.png
      :alt: **Figure 1** Entrance to the domain configuration page

      **Figure 1** Entrance to the domain configuration page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the desired domain name. In the **Operation** column, click **Configure Policy**. :ref:`Figure 2 <waf_01_0017__waf_01_0008_fig16197124372015>` shows an example.

   .. _waf_01_0017__waf_01_0008_fig16197124372015:

   .. figure:: /_static/images/en-us_image_0000001321314926.png
      :alt: **Figure 2** Protection configuration page

      **Figure 2** Protection configuration page

#. .. _waf_01_0017__li45442459125143:

   In the **Data Masking** area, specify **Status**. After the configuration completes, in the upper right corner of the **Protection Status** list, click **Save**. In the displayed dialog box, click **Yes** to save the settings. If you do not want to save the settings, click **Cancel**. :ref:`Figure 3 <waf_01_0017__fig163378412590>` shows an example.

   .. _waf_01_0017__fig163378412590:

   .. figure:: /_static/images/en-us_image_0000001372714413.png
      :alt: **Figure 3** Data Masking configuration area

      **Figure 3** Data Masking configuration area

#. Click **Customize Rule**. On the displayed **Data Masking** page, click **Add Rule** in the upper left corner. :ref:`Figure 4 <waf_01_0017__fig187391447920>` shows an example.

   .. note::

      If you do not click **Save** after changing **Status** in :ref:`Step 5 <waf_01_0017__li45442459125143>`, a **Warning** dialog box is displayed when you click **Customize Rule**.

      -  Click **Yes** to cancel the previous settings.
      -  Click **No** and then **Save** to save the settings.

   .. _waf_01_0017__fig187391447920:

   .. figure:: /_static/images/en-us_image_0000001372554605.png
      :alt: **Figure 4** Add Rule (Data Masking)

      **Figure 4** Add Rule (Data Masking)

   .. note::

      In the upper part of the protection rule list, click **Quota details** to view the quota of protection rules.

#. In the displayed dialog box, specify the parameters by referring to :ref:`Table 1 <waf_01_0017__table4696626918715>`. :ref:`Figure 5 <waf_01_0017__fig49385421125519>` shows an example

   .. _waf_01_0017__fig49385421125519:

   .. figure:: /_static/images/en-us_image_0000001321634502.png
      :alt: **Figure 5** Adding a data masking rule

      **Figure 5** Adding a data masking rule

   .. _waf_01_0017__table4696626918715:

   .. table:: **Table 1** Rule parameters

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Description                                                                                                                                                                                           | Example Value                                                                                                                                                            |
      +=======================+=======================================================================================================================================================================================================+==========================================================================================================================================================================+
      | Path                  | URL excluding a domain name                                                                                                                                                                           | **/admin/login.php**                                                                                                                                                     |
      |                       |                                                                                                                                                                                                       |                                                                                                                                                                          |
      |                       | -  Prefix match: The path ending with \* indicates that the path is used as a prefix. For example, if the path to be protected is **/admin/test.php** or **/adminabc**, set **Path** to **/admin\***. | For example, if the URL to be protected is **http://www.example.com/admin/login.php**, set **Path** to **/admin/login.php**.                                             |
      |                       | -  Exact match: The path to be entered must match the path to be protected. If the path to be protected is **/admin**, set **Path** to **/admin**.                                                    |                                                                                                                                                                          |
      |                       |                                                                                                                                                                                                       |                                                                                                                                                                          |
      |                       | .. note::                                                                                                                                                                                             |                                                                                                                                                                          |
      |                       |                                                                                                                                                                                                       |                                                                                                                                                                          |
      |                       |    -  The path supports prefix and exact matches only and does not support regular expressions.                                                                                                       |                                                                                                                                                                          |
      |                       |    -  The path cannot contain two or more consecutive slashes. For example, **///admin**. If you enter **///admin**, the WAF engine converts **///** to **/**.                                        |                                                                                                                                                                          |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Masked Field          | A field set to be masked                                                                                                                                                                              | -  If **Masked Field** is set to **Params**, configure **Subfield** based on your needs. If it is set to **id**, the content that matches **id** will be masked.         |
      |                       |                                                                                                                                                                                                       | -  If **Masked Field** is set to **Header**, configure **Subfield** based on your needs. If it is set to **Accept**, the content that matches **Accept** will be masked. |
      |                       | -  **Params**: A request parameter                                                                                                                                                                    |                                                                                                                                                                          |
      |                       | -  **Header**: A user-defined HTTP header                                                                                                                                                             |                                                                                                                                                                          |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Subfield              | Set the parameter based on **Masked Field**. The masked field will not be displayed in the log.                                                                                                       |                                                                                                                                                                          |
      |                       |                                                                                                                                                                                                       |                                                                                                                                                                          |
      |                       | .. important::                                                                                                                                                                                        |                                                                                                                                                                          |
      |                       |                                                                                                                                                                                                       |                                                                                                                                                                          |
      |                       |    NOTICE:                                                                                                                                                                                            |                                                                                                                                                                          |
      |                       |    The length of a subfield cannot exceed 2048 bytes. Only digits, letters, underscores (_), and hyphens (-) are allowed.                                                                             |                                                                                                                                                                          |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   -  To modify the added rule, click **Modify** in the row containing the target rule.
   -  To delete the added rule, click **Delete** in the row containing the target rule.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
