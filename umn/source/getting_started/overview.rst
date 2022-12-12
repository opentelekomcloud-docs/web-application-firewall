:original_name: waf_01_0071.html

.. _waf_01_0071:

Overview
========

Before using WAF, you need to connect your domain name to it and enable it for protection to take effect.

:ref:`Table 1 <waf_01_0071__table186068221358>` describes the procedure to use WAF.

.. _waf_01_0071__table186068221358:

.. table:: **Table 1** Procedure to use WAF

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Step                              | Description                                                                                                                                                                                                                                                                                                                                             |
   +===================================+=========================================================================================================================================================================================================================================================================================================================================================+
   | Creating a domain name            | Add a website to be protected. For details, see :ref:`Creating a Domain Name <waf_01_0002>`.                                                                                                                                                                                                                                                            |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Enabling WAF protection           | Enable WAF protection to protect your web services. For details, see :ref:`Enabling WAF Protection <waf_01_0003>`.                                                                                                                                                                                                                                      |
   |                                   |                                                                                                                                                                                                                                                                                                                                                         |
   |                                   | .. note::                                                                                                                                                                                                                                                                                                                                               |
   |                                   |                                                                                                                                                                                                                                                                                                                                                         |
   |                                   |    -  The WAF engine does not run on your web server. Therefore, your web server performance will not be affected.                                                                                                                                                                                                                                      |
   |                                   |    -  After your domain name is connected to WAF, there will be a latency of tens of milliseconds, but might be raised based on the size of the requested page or number of incoming requests.                                                                                                                                                          |
   |                                   |    -  You are billed for queries per second (QPS) or service bandwidth. One HTTP GET request is counted as a query, and the maximum QPS WAF can handle is 10,000. The total volume of normal traffic to a website or domain names protected by WAF is counted as the service bandwidth, and the maximum service bandwidth WAF can handle is 300 Mbit/s. |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Configuring rules                 | In addition to the built-in protection rules, WAF provides a rich set of custom rules. For details, see :ref:`Rule Configurations <waf_01_0007>`.                                                                                                                                                                                                       |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Enabling alarm notification       | Once the function is enabled, users can receive attack logs at the earliest moment. For details, see :ref:`Enabling Alarm Notification <waf_01_0019>`.                                                                                                                                                                                                  |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Handling false alarms             | If the attack events blocked or logged are false positives, mask them. For details, see :ref:`Handling False Alarms <waf_01_0024>`.                                                                                                                                                                                                                     |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Viewing **Dashboard**             | View the request and attack statistics, event distribution, and top 5 attack resource IP addresses of yesterday, today, past 3 days, past 7 days, or past 30 days. For details, see :ref:`Dashboard <waf_01_0021>`.                                                                                                                                     |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

For details about how to connect your website to WAF, see :ref:`Figure 1 <waf_01_0071__fig62118250304>`.

.. _waf_01_0071__fig62118250304:

.. figure:: /_static/images/en-us_image_0000001321314978.png
   :alt: **Figure 1** Flowchart for connecting your website to WAF

   **Figure 1** Flowchart for connecting your website to WAF
