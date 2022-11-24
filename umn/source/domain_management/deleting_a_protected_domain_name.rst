:original_name: waf_01_0005.html

.. _waf_01_0005:

Deleting a Protected Domain Name
================================

This section describes how to delete a protected domain name from WAF.

.. important::

   -  If the domain name to be deleted has been connected to WAF, re-resolve it with the DNS provider before you delete it to make it point to the origin server IP address. Otherwise, traffic intended to it will not be directed to the server, affecting access.
   -  Deletion takes effect within 1 minute and deleted domain names cannot be recovered. Therefore, exercise caution when deleting a domain name.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be deleted is resolved to the origin server address.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**. In the navigation pane on the left, choose **Domains**. :ref:`Figure 1 <waf_01_0005__f6b9e0be38f9b4498a46fea967ef351ae>` shows an example.

   .. _waf_01_0005__f6b9e0be38f9b4498a46fea967ef351ae:

   .. figure:: /_static/images/en-us_image_0000001321794518.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. Locate the row that contains the domain name to be deleted. In the **Operation** column, choose **More** > **Delete**.

   -  No proxy used (see :ref:`Figure 2 <waf_01_0005__fig11194454171217>`)

      .. note::

         -  After confirmation, select "**The CNAME of the domain name has been deleted from the DNS provider, and an A-record has been configured to the origin server IP address, or services carried on the domain name have been brought offline.**"
         -  If you want to retain the policy bound to the domain name, select **Retain the policy of this domain name**.

      .. _waf_01_0005__fig11194454171217:

      .. figure:: /_static/images/en-us_image_0000001321634530.png
         :alt: **Figure 2** Deleting a domain name (without a proxy)

         **Figure 2** Deleting a domain name (without a proxy)

   -  Proxy used (see :ref:`Figure 3 <waf_01_0005__fig8903356111915>`)

      .. note::

         -  After confirmation, select **The domain name has been pointed to the origin server on the Advanced Anti-DDoS, CDN, or cloud acceleration service side, or services carried on the domain name have been brought offline**.
         -  If you want to retain the policy bound to the domain name, select **Retain the policy of this domain name**.

      .. _waf_01_0005__fig8903356111915:

      .. figure:: /_static/images/en-us_image_0000001372714449.png
         :alt: **Figure 3** Deleting a domain name (with a proxy)

         **Figure 3** Deleting a domain name (with a proxy)

#. Click **Yes**. If **Domain deleted successfully** is displayed in the upper right corner, the domain name is deleted.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
