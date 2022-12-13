:original_name: waf_02_0078.html

.. _waf_02_0078:

Querying the List of Event Log Files
====================================

Function Description
--------------------

This API is used to query the list of event log files.

URI
---

-  URI format

   GET /v1/{project_id}/waf/event/dump?offset={offset}&limit={limit}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Mandatory | Type   | Description                                                                                                                         |
      +============+===========+========+=====================================================================================================================================+
      | project_id | Yes       | String | Specifies the project ID.                                                                                                           |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | offset     | No        | Long   | Specifies the number of returned pages. Its value ranges from **0** to **65535**. The default value is **0**.                       |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+
      | limit      | No        | Long   | Specifies the maximum number of records displayed on each page. Its value ranges from **0** to **50**. The default value is **10**. |
      +------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

.. table:: **Table 2** Parameter description

   +-----------+---------------------------------------------------+------------------------------------------+
   | Parameter | Type                                              | Description                              |
   +===========+===================================================+==========================================+
   | total     | Integer                                           | Specifies the total number of log files. |
   +-----------+---------------------------------------------------+------------------------------------------+
   | items     | :ref:`Table 3 <waf_02_0078__table16394183011019>` | Specifies the log file objects.          |
   +-----------+---------------------------------------------------+------------------------------------------+

.. _waf_02_0078__table16394183011019:

.. table:: **Table 3** **items**

   ========= ======= ===================================================
   Parameter Type    Description
   ========= ======= ===================================================
   id        String  Specifies the ID of a log file.
   filename  String  Specifies the name of a log file.
   total     Integer Specifies the total number of events in a log file.
   url       String  Specifies the URL to download a log file.
   timestamp Long    Specifies the time when a log file is generated.
   ========= ======= ===================================================

Example
-------

**total** with a value of **2** is used as an example.

Response example

.. code-block::

   {
     "total": 2,
     "items": [{
         "id": "3a9b5c0f96784ec8abd8ba61a98064ef",
         "filename": "WAF-eu-de-2019-01-15.csv",
         "total": "100",
         "url": "https://obs_server/obs-waf-log/WAF-eu-de-2019-01-15-xxxxxxxxxx.csv?AWSAccessKeyId=XXXXXXXXXXXX&Expires=1547632&Signature=nC7ipaGzLQs",
         "timestamp": 1499817600
       }, {
         "id": "44d887434169475794b2717438f7fa78",
         "filename": "WAF-eu-deW-2019-01-14.csv",
         "total": "200",
         "url": "https://obs_server/obs-waf-log/WAF-eu-de-2019-01-14-xxxxxxxxxx.csv?AWSAccessKeyId=XXXXXXXXXXXX&Expires=1547632&Signature=nC7ipaGzLQs",
         "timestamp": 1499817601
       }
     ]
   }
