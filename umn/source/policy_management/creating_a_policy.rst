:original_name: waf_01_0074.html

.. _waf_01_0074:

Creating a Policy
=================

A policy is a combination of multiple rules, such as basic web protection, blacklist or whitelist, and precise protection rules. A policy can be applied to multiple domain names. This section describes how to create a policy.

Prerequisites
-------------

Login credentials have been obtained.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the management console and select a region or project.
#. Choose **Security** > **Web Application Firewall**. In the navigation pane, choose **Policies**.

4. Click **Create Policy** in the upper right corner of the list. :ref:`Figure 1 <waf_01_0074__fig1769985133814>` shows an example.

   .. _waf_01_0074__fig1769985133814:

   .. figure:: /_static/images/en-us_image_0000001321474654.png
      :alt: **Figure 1** Creating a policy

      **Figure 1** Creating a policy

   .. note::

      In the upper part of the protection policy list, click **Quota details** to view the quota of the protection policy.

5. In the dialog box displayed, enter a policy name and click **OK**. :ref:`Figure 2 <waf_01_0074__fig0843200133618>` shows an example.

   .. _waf_01_0074__fig0843200133618:

   .. figure:: /_static/images/en-us_image_0000001321794522.png
      :alt: **Figure 2** Create Policy dialog box

      **Figure 2** Create Policy dialog box

6. In the **Policy Name** column, click the target policy name. On the displayed page, add rules to the policy by referring to Section :ref:`Rule Configurations <waf_01_0007>`.


   .. figure:: /_static/images/en-us_image_0000001372795301.png
      :alt: **Figure 3** Policies page

      **Figure 3** Policies page

   .. note::

      -  To modify a policy name, click |image2| next to the target policy name. In the dialog box displayed, enter a new policy name.
      -  After a domain name is created, WAF protection is enabled by default. The mode of Basic Web Protection is **Log only** (detected attacks are only logged but not blocked.). By default, WAF creates a CC attack protection rule to the policy. The rule can be modified but cannot be deleted.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
.. |image2| image:: /_static/images/en-us_image_0000001372554657.png
