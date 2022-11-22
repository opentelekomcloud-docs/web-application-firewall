:original_name: waf_01_0003.html

.. _waf_01_0003:

Enabling WAF Protection
=======================

This section describes how to enable WAF protection.

.. note::

   -  The WAF engine does not run on your web server. Therefore, your web server performance will not be affected.
   -  After your domain name is connected to WAF, there will be a latency of tens of milliseconds, but might be raised based on the size of the requested page or number of incoming requests.
   -  You are billed for queries per second (QPS) or service bandwidth. One HTTP GET request is counted as a query, and the maximum QPS WAF can handle is 10,000. The total volume of normal traffic to a website or domain names protected by WAF is counted as the service bandwidth, and the maximum service bandwidth WAF can handle is 300 Mbit/s.

Prerequisites
-------------

-  Login credentials have been obtained.
-  **Mode** for WAF to protect the domain name is **Disabled** or **Bypassed**.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**. In the navigation pane on the left, choose **Domains**. :ref:`Figure 1 <waf_01_0003__f6b9e0be38f9b4498a46fea967ef351ae>` shows an example.

   .. _waf_01_0003__f6b9e0be38f9b4498a46fea967ef351ae:

   .. figure:: /_static/images/en-us_image_0000001372795237.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Operation** column of the target domain name, click **Switch Mode**.

#. In the **Switch Mode** dialog box, select **Enabled** and then click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
