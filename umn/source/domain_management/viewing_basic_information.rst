:original_name: waf_01_0020.html

.. _waf_01_0020:

Viewing Basic Information
=========================

This section describes how to view domain information and edit server information.

Prerequisites
-------------

Login credentials have been obtained.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**. In the navigation pane on the left, choose **Domains**. :ref:`Figure 1 <waf_01_0020__fig15765259143313>` shows an example. :ref:`Table 1 <waf_01_0020__table147842051135211>` describes parameters.

   In the upper right corner of the list, query domain information by domain name, policy name, or tag.

   .. _waf_01_0020__fig15765259143313:

   .. figure:: /_static/images/en-us_image_0000001321794518.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

   .. _waf_01_0020__table147842051135211:

   .. table:: **Table 1** Parameter description

      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                          | Description                                                                                                                                                                                 |
      +====================================+=============================================================================================================================================================================================+
      | Name                               | Protected domain name                                                                                                                                                                       |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Mode                               | WAF mode of the protected domain name                                                                                                                                                       |
      |                                    |                                                                                                                                                                                             |
      |                                    | -  **Enabled**: WAF is enabled.                                                                                                                                                             |
      |                                    | -  **Disabled**: WAF is disabled.                                                                                                                                                           |
      |                                    | -  **Bypassed**: In this mode, requests are directly sent to the backend server without passing through WAF.                                                                                |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | DNS                                | DNS resolution status                                                                                                                                                                       |
      |                                    |                                                                                                                                                                                             |
      |                                    | -  **Unconfigured**: The domain name is not connected to WAF or domain connection fails. To solve the problem, see :ref:`What Should I Do If the DNS Status Is Unconfigured? <waf_01_0056>` |
      |                                    | -  **Normal**: The domain name is connected to WAF.                                                                                                                                         |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protection Status over Past 3 Days | Protection status of the domain name over the past three days. Choose **More >View Attack** in the **Operation** column to view specific protection logs.                                   |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Policy                             | Policy configuration of the domain name. Click **Configure Policy** to configure rules by referring to :ref:`Rule Configurations <waf_01_0007>`.                                            |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. In the **Name** column, click the target domain name to go to the basic information page.

#. View domain information.

   a. View **Basic Information** and **WAF Information**. :ref:`Figure 2 <waf_01_0020__fig1902122615546>` and :ref:`Figure 3 <waf_01_0020__fig16903112618542>` show examples.

      In the upper right corner of the domain information page, click |image2| to refresh the page.

      .. _waf_01_0020__fig1902122615546:

      .. figure:: /_static/images/en-us_image_0000001321474650.png
         :alt: **Figure 2** Viewing basic information (with a proxy)

         **Figure 2** Viewing basic information (with a proxy)

      .. note::

         -  **Domain ID**: unique ID that is generated randomly for a domain name.
         -  **Creation Time**: time when the domain name is created.
         -  Click |image3| in the **Access Address**, **Subdomain Name**, **TXT Record**, or **WAF IP Address Range** row to copy the required value.
         -  If **Client Protocol** is set to **HTTPS**, updating the certificate is required. To do so, click |image4| next to **Certificate Name**. In the displayed dialog box, select an existing certificate.
         -  If your web server stops using a proxy, click |image5| next to the value of **Proxy Configured**. In the dialog box displayed, select **No**.

      .. _waf_01_0020__fig16903112618542:

      .. figure:: /_static/images/en-us_image_0000001321794506.png
         :alt: **Figure 3** Viewing basic information (without a proxy)

         **Figure 3** Viewing basic information (without a proxy)

      .. note::

         -  **Domain ID**: unique ID that is generated randomly for a domain name.
         -  **Creation Time**: time when the domain name is created.
         -  Click |image6| in the target row to copy the value of **CNAME** or **WAF IP Address Range**.
         -  If **Client Protocol** is set to **HTTPS**, updating the certificate is required. To do so, click |image7| next to **Certificate Name**. In the displayed dialog box, select an existing certificate.
         -  If your web server starts using a proxy, click |image8| next to the value of **Proxy Configured**. In the dialog box displayed, select **Yes**.

   b. View **Server Information**. :ref:`Figure 4 <waf_01_0020__fig104141220121620>` shows an example.

      .. _waf_01_0020__fig104141220121620:

      .. figure:: /_static/images/en-us_image_0000001372795297.png
         :alt: **Figure 4** Server Information

         **Figure 4** Server Information

      Click **Edit Server Information**. On the **Edit Server Information** page shown in :ref:`Figure 5 <waf_01_0020__fig3368635172714>`, edit server configurations (such as client protocol and associated certificate).

      .. _waf_01_0020__fig3368635172714:

      .. figure:: /_static/images/en-us_image_0000001372554661.png
         :alt: **Figure 5** Editing server information

         **Figure 5** Editing server information

      .. note::

         Web Application Firewall (WAF) does not support health check. If you want to use health check, use WAF along with Elastic Load Balancing (ELB). For details about how to configure ELB, see `Backend Server (Enhanced Load Balancer) <https://docs.otc.t-systems.com/en-us/usermanual/elb/en-us_topic_0052569729.html>`__. After ELB is configured, the elastic IP address (EIP) of ELB is used as the value of **Server Address** to connect to WAF for health check.

   c. Click the **Tags** tab and view the tags, as shown in :ref:`Figure 6 <waf_01_0020__fig1814661617294>`.

      .. _waf_01_0020__fig1814661617294:

      .. figure:: /_static/images/en-us_image_0000001321314970.png
         :alt: **Figure 6** Tags

         **Figure 6** Tags

      -  In the **Operation** column of the tag list, click **Edit** to change the value.

      -  Click **Delete** to delete a tag. A deleted tag cannot be restored. Exercise caution when performing this operation.

      -  In the upper left corner of the tag list, click **Add Tag** to add one. See :ref:`Figure 7 <waf_01_0020__fig0811031133312>`.

         You can select an existing tag key and tag value from the **Tag key** and **Tag value** drop-down lists or click **View predefined tags** to create a tag on the TMS console.

         .. _waf_01_0020__fig0811031133312:

         .. figure:: /_static/images/en-us_image_0000001372714489.png
            :alt: **Figure 7** Add Tag

            **Figure 7** Add Tag

Related Operations
------------------

In the **Operation** column of the domain list, you can:

-  Click **Switch Mode** to switch the WAF working mode.
-  Click **Configure Policy** to configure WAF protection rules.
-  Choose **More** > **Check DNS** to check the DNS resolution status.
-  Choose **More** > **View Attack** to view the WAF protection logs.
-  Choose **More** > **View Metric** to view the WAF monitoring logs. For more details, see *Cloud Eye User Guide*.
-  Choose **More** > **Delete** to delete the protected domain.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372714485.png
.. |image3| image:: /_static/images/en-us_image_0000001321314934.png
.. |image4| image:: /_static/images/en-us_image_0000001372554657.png
.. |image5| image:: /_static/images/en-us_image_0000001372554657.png
.. |image6| image:: /_static/images/en-us_image_0000001321314934.png
.. |image7| image:: /_static/images/en-us_image_0000001372554657.png
.. |image8| image:: /_static/images/en-us_image_0000001372554657.png
