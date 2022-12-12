:original_name: waf_01_0004.html

.. _waf_01_0004:

Disabling WAF Protection
========================

This section describes how to disable WAF protection. In this mode, WAF only forwards requests, but does not detect them.

Prerequisites
-------------

-  Login credentials have been obtained.
-  **Mode** for WAF to protect the domain name is **Enabled** or **Bypassed**.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0004__f43a0d099aa8b4a959f5f15efa37a602b>` shows an example.

   .. _waf_01_0004__f43a0d099aa8b4a959f5f15efa37a602b:

   .. figure:: /_static/images/en-us_image_0000001372554637.png
      :alt: **Figure 1** Domain name list

      **Figure 1** Domain name list

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Operation** column of the target domain name, click **Switch Mode**.

#. In the **Switch Mode** dialog box, select **Disabled** and then click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
