:original_name: waf_01_0077.html

.. _waf_01_0077:

Downloading Events Data
=======================

This section describes how to download events (logged and blocked events) data over the past five days. An event file is generated at 01:00:00 (UTC time) of the second day.

Prerequisites
-------------

-  Login credentials have been obtained for logging in to the management console.
-  An event file has been generated.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner of the management console and select a region or project.

#.  Choose **Security** > **Web Application Firewall**. In the navigation pane on the left, choose **Events**. On the displayed page, click the **Download** tab. :ref:`Table 1 <waf_01_0077__table3449146163213>` lists related parameters. :ref:`Figure 1 <waf_01_0077__fig667514141105>` shows an example.

   .. _waf_01_0077__fig667514141105:

   .. figure:: /_static/images/en-us_image_0000001372554593.png
      :alt: **Figure 1** Download tab page

      **Figure 1** Download tab page

   .. _waf_01_0077__table3449146163213:

   .. table:: **Table 1** Parameter description

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                             |
      +===================================+=========================================================================================================================+
      | Name                              | The format is *file name*.\ **csv**.                                                                                    |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
      | Number of Events                  | Total number of blocked and logged events                                                                               |
      |                                   |                                                                                                                         |
      |                                   | .. note::                                                                                                               |
      |                                   |                                                                                                                         |
      |                                   |    The maximum number of events in a file is 10,000. If the number of events exceeds 10,000, another file is generated. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+

#. In the **Operation** column, click **Download Data** to download data to the local PC.

.. |image1| image:: /_static/images/en-us_image_0000001372714457.png
