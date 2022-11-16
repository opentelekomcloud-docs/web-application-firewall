:original_name: waf_01_0069.html

.. _waf_01_0069:

Setting WAF Bypassed Mode
=========================

This section describes how to set the bypassed mode whereby requests are sent directly to the backend server without passing through WAF.

.. note::

   In special scenarios such as testing, if services need to be restored to the state where the domain name is not connected to WAF, use the **Bypassed** mode.

Prerequisites
-------------

-  Login credentials have been obtained.
-  **Mode** for WAF to protect the domain name is **Enabled** or **Disabled**.
-  Your web server does not use a proxy.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Click **Service List** at the top of the page and choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0069__waf_01_0004_f43a0d099aa8b4a959f5f15efa37a602b>` shows an example.

   .. _waf_01_0069__waf_01_0004_f43a0d099aa8b4a959f5f15efa37a602b:

   .. figure:: /_static/images/en-us_image_0000001372554637.png
      :alt: **Figure 1** Domain name list

      **Figure 1** Domain name list

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Operation** column of the target domain name, click **Switch Mode**.

#. In the dialog box displayed, select **Bypassed** and then click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
