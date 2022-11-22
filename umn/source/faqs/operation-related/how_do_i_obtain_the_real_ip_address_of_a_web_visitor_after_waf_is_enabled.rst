:original_name: waf_01_0062.html

.. _waf_01_0062:

How Do I Obtain the Real IP Address of a Web Visitor After WAF Is Enabled?
==========================================================================

Generally, a proxy such as CDN, WAF, and AAD is deployed between the client and server. Web visitors cannot directly access the server. For example, **web visitor** > **CDN/WAF/AAD** > **origin server**. Then, how does the server obtain the real IP address of the client when multiple proxies are used?

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**. In the navigation pane on the left, choose **Domains**.\ :ref:`Figure 1 <waf_01_0062__en-us_topic_0000001221127281_en-us_topic_0154713166_f6b9e0be38f9b4498a46fea967ef351ae>` shows an example.

   .. _waf_01_0062__en-us_topic_0000001221127281_en-us_topic_0154713166_f6b9e0be38f9b4498a46fea967ef351ae:

   .. figure:: /_static/images/en-us_image_0000001221367359.png
      :alt: **Figure 1** Domains page

      **Figure 1** Domains page

   .. note::

      In the upper part of the domain name list, click **Quota details** to view the domain name quota.

#. In the **Name** column, click the target domain name to go to the basic information page.

#. View **Source IP Header**. By default, WAF obtains the real IP address of a web visitor from the HTTP header **X-Forwarded-For**. The first IP address in the **X-Forwarded-For** field is the real IP address of the web visitor. You can also click |image2| to customize the field to identify the real IP address. :ref:`Figure 2 <waf_01_0062__en-us_topic_0000001221127281_fig41979345127>` shows an example.

   .. _waf_01_0062__en-us_topic_0000001221127281_fig41979345127:

   .. figure:: /_static/images/en-us_image_0000001221127307.png
      :alt: **Figure 2** Basic domain information

      **Figure 2** Basic domain information

.. |image1| image:: /_static/images/en-us_image_0000001175607540.png
.. |image2| image:: /_static/images/en-us_image_0000001221127319.png
