:original_name: waf_01_0092.html

.. _waf_01_0092:

Monitoring Metrics
==================

Function Description
--------------------

This section describes monitoring metrics reported by WAF to Cloud Eye as well as their namespaces and dimensions. You can use the management console or APIs provided by Cloud Eye to query the monitoring metrics of the monitored object and alarms generated for WAF.

Namespace
---------

SYS.WAF

.. note::

   A namespace is an abstract collection of resources and objects. Multiple namespaces can be created in a single cluster, but they are isolated from each other. This enables namespaces to share the same cluster services without affecting each other.

Metrics
-------

.. table:: **Table 1** Monitoring metrics

   +-----------+-------------+------------------------------------------------------------------------+-------------+-------------------------------------------+--------------------------------+
   | Metric ID | Metric Name | Meaning                                                                | Value Range | Measurement Object & Dimension            | Monitoring Interval (Raw Data) |
   +===========+=============+========================================================================+=============+===========================================+================================+
   | attacks   | attacks     | Total number of attacks on a protected domain name in a given period   | >= 0 count  | Measurement object: protected domain name | 5 minutes                      |
   |           |             |                                                                        |             |                                           |                                |
   |           |             |                                                                        |             | Dimension: waf_instance_id                |                                |
   +-----------+-------------+------------------------------------------------------------------------+-------------+-------------------------------------------+--------------------------------+
   | requests  | requests    | Total number of requests for a protected domain name in a given period | >= 0 count  | Measurement object: protected domain name | 5 minutes                      |
   |           |             |                                                                        |             |                                           |                                |
   |           |             |                                                                        |             | Dimension: waf_instance_id                |                                |
   +-----------+-------------+------------------------------------------------------------------------+-------------+-------------------------------------------+--------------------------------+

Dimensions
----------

.. table:: **Table 2** Dimensions

   =============== ==============
   Key             Value
   =============== ==============
   waf_instance_id Domain name ID
   =============== ==============
