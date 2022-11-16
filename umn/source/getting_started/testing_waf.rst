:original_name: waf_01_0073.html

.. _waf_01_0073:

Testing WAF
===========

This section describes how to connect your domain to WAF on a local PC and then access the site to verify whether WAF works properly.

Before testing WAF, ensure that the protocol, address, and port number used by the origin server of the domain name (for example, **www.test.com**), and uploaded certificate content and private key if **Client Protocol** is **HTTPS** are correct.

Prerequisites
-------------

-  Login credentials have been obtained.
-  A domain name without using any other proxy has been created.

Connecting Your Domain to WAF Locally
-------------------------------------

#. Obtain the CNAME value.

   a. Log in to the management console.

   b. Click |image1| in the upper left corner of the management console and select a region or project.

   c. Choose **Security** > **Web Application Firewall**.

   d. In the navigation pane, choose **Domains**. :ref:`Figure 1 <waf_01_0073__fig179871053191112>` shows an example.

      .. _waf_01_0073__fig179871053191112:

      .. figure:: /_static/images/en-us_image_0000001321794518.png
         :alt: **Figure 1** Domains page

         **Figure 1** Domains page

      .. note::

         In the upper part of the domain name list, click **Quota details** to view the domain name quota.

   e. In the row of the desired domain name, under the **Name** column, click the domain name you want to test. :ref:`Figure 2 <waf_01_0073__fig14325952203617>` shows an example.

      .. _waf_01_0073__fig14325952203617:

      .. figure:: /_static/images/en-us_image_0000001321634538.png
         :alt: **Figure 2** Copying the CNAME value

         **Figure 2** Copying the CNAME value

   f. In the **CNAME** row, click |image2| to copy the CNAME value.

#. .. _waf_01_0073__li132916207364:

   Ping the CNAME value and record the corresponding IP address (for example, **192.168.0.1**).

#. Add the domain name and WAF IP address to the **hosts** file.

   a. Use a text editor, such as Notepad or Notepad++, to open the **hosts** file. Generally, the **hosts** file is stored in the **C:\\Windows\\System32\\drivers\\etc\\** directory.

   b. .. _waf_01_0073__li4860411142315:

      Add the back-to-source IP address of WAF obtained in :ref:`Step 2 <waf_01_0073__li132916207364>` and protected domain name to the **hosts** file. :ref:`Figure 3 <waf_01_0073__fig934381520563>` shows an example.

      .. _waf_01_0073__fig934381520563:

      .. figure:: /_static/images/en-us_image_0000001321474614.png
         :alt: **Figure 3** Adding a record

         **Figure 3** Adding a record

   c. Save the **hosts** file and ping the protected domain name on the local PC.

      It is expected that the resolved IP address is the back-to-source IP address of WAF obtained in :ref:`Step 2 <waf_01_0073__li4860411142315>`. If the resolved IP address is the origin server address, run the **ipconfig/flushdns** command in the Windows operating system to refresh the DNS cache.

Verifying Whether WAF Forwarding Is Normal
------------------------------------------

#. Clear the browser cache and enter the domain name in the address box of a browser to check whether the website can be accessed.

   If the domain name resolves to the back-to-source IP address of WAF and WAF configurations are correct, the website can be accessed.


   .. figure:: /_static/images/en-us_image_0000001372914957.png
      :alt: **Figure 4** Normal access

      **Figure 4** Normal access

#. Simulate simple web attack commands.

   a. Set the mode of Basic Web Protection to **Block**. For details, see :ref:`Enabling Basic Web Protection <waf_01_0008>`.

   b. Clear the browser cache, enter **http://www.test.com?id=1%20or%201%20=1** in the address box of the browser to simulate an SQL injection attack, and check whether WAF blocks the attack. See :ref:`Figure 5 <waf_01_0073__fig1713141245913>`.

      .. _waf_01_0073__fig1713141245913:

      .. figure:: /_static/images/en-us_image_0000001321794486.png
         :alt: **Figure 5** Request blocked

         **Figure 5** Request blocked

   c. Choose **Security** > **Web Application Firewall**. On the displayed page, click **Events** and view test data on the displayed page. :ref:`Figure 6 <waf_01_0073__fig1413231215916>` shows an example.

      .. _waf_01_0073__fig1413231215916:

      .. figure:: /_static/images/en-us_image_0000001372554629.png
         :alt: **Figure 6** Viewing test data

         **Figure 6** Viewing test data

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001321314934.png
