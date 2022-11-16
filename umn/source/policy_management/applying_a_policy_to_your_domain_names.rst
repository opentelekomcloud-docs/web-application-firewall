:original_name: waf_01_0075.html

.. _waf_01_0075:

Applying a Policy to Your Domain Names
======================================

This section describes how to apply a policy to your domain names.

Prerequisites
-------------

-  Login credentials have been obtained.
-  The domain name to be protected has been created.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#. Choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Policies**.

#. In the row containing the target policy name, click **Bind Domain** in the **Operation** column. :ref:`Figure 1 <waf_01_0075__fig169858225460>` shows an example.

   .. _waf_01_0075__fig169858225460:

   .. figure:: /_static/images/en-us_image_0000001372914961.png
      :alt: **Figure 1** Clicking Bind Domain

      **Figure 1** Clicking Bind Domain

#. Select one or more domain names from the **Domain Name** drop-down list. :ref:`Figure 2 <waf_01_0075__fig4167335513>` shows an example.

   To view information about all domain names, click **View Domains**.

   .. important::

      -  A protected domain name can use only one policy, but one policy can be applied to multiple domain names.
      -  To delete a policy bound to domain names, bind these domain names to other policies, and click **Delete** in the **Operation** column of the target policy name.

   .. _waf_01_0075__fig4167335513:

   .. figure:: /_static/images/en-us_image_0000001321314938.png
      :alt: **Figure 2** Selecting one or more domain names

      **Figure 2** Selecting one or more domain names

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
