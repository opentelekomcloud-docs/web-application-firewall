:original_name: waf_02_0092.html

.. _waf_02_0092:

Querying Instances by Tag
=========================

Function Description
--------------------

This API is used to query protected domain name instances by tag.

URI
---

-  URI format

   POST /v1/{project_id}/waf/resource_instances/action

-  Parameter description

   .. table:: **Table 1** Path parameters

      ========== ========= ====== =========================
      Parameter  Mandatory Type   Description
      ========== ========= ====== =========================
      project_id Yes       String Specifies the project ID.
      ========== ========= ====== =========================

Request
-------

Request parameters

.. table:: **Table 2** Parameter description

   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   +=================+=================+================================================+======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | without_any_tag | No              | boolean                                        | If this parameter is set to **true**, all resources without tags are queried. In this case, the tags, tags_any, not_tags, and not_tags_any fields are ignored.                                                                                                                                                                                                                                                                                                                                                       |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags            | No              | :ref:`Table 3 <waf_02_0092__table38371299527>` | Includes specified tags.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This field contains a maximum of 20 tag keys, and each tag key has a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Keys must be unique and values of a key must be unique. The response returns resources containing all tags in this list. Keys in this list are in an AND relationship while values in each key-value structure is in an OR relationship. If no tag filtering condition is specified, full data is returned.    |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tags_any        | No              | :ref:`Table 3 <waf_02_0092__table38371299527>` | Includes any of the specified tags.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This field contains a maximum of 20 tag keys, and each tag key has a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Keys must be unique and values of a key must be unique. The response returns resources containing the tags in this list. Keys in this list are in an OR relationship and values in each key-value structure are also in an OR relationship. If no tag filtering condition is specified, full data is returned. |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags        | No              | :ref:`Table 3 <waf_02_0092__table38371299527>` | Excludes specified tags.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This field contains a maximum of 20 tag keys, and each tag key has a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Keys must be unique and values of a key must be unique. The response returns resources containing no tags in this list. Keys in this list are in an AND relationship while values in each key-value structure are in an OR relationship. If no tag filtering condition is specified, full data is returned.    |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | not_tags_any    | No              | :ref:`Table 3 <waf_02_0092__table38371299527>` | Excludes any of the specified tags.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This field contains a maximum of 20 tag keys, and each tag key has a maximum of 10 tag values. The tag value corresponding to each tag key can be an empty array but the structure cannot be missing. Keys must be unique and values of a key must be unique. The response returns resources containing no tags in this list. Keys in this list are in an OR relationship and values in each key-value structure are also in an OR relationship. If no tag filtering condition is specified, full data is returned.  |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | String                                         | Specifies the number of records to be queried. This parameter is unavailable if **action** is **count**. If **action** is **filter**, the maximum value of **limit** is **1000** by default.                                                                                                                                                                                                                                                                                                                         |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This parameter value cannot be a negative number. The minimum value is **1**.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | String                                         | Specifies the query index. This parameter is unavailable if **action** is **count**.                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | If **offset** is set to *N*, the resource query starts from the *N+1* piece of data. If **action** is set to **filter**, **offset** is **0** by default, indicating that the query starts from the first piece of data.                                                                                                                                                                                                                                                                                              |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | This parameter value cannot be a negative number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | Yes             | String                                         | Specifies the operation. The value can be **filter** or **count**.                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | -  **filter**: Query by filter criteria.                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                                                | -  **count**: Only the total number of records needs to be returned.                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | No              | :ref:`Table 4 <waf_02_0092__table10200716215>` | Specified the search field.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |                 |                 |                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |                 |                 |                                                | -  **key** indicates the field to be matched. For example, **resource_name**. If **key** is **resource_name**, fuzzy search is used by default. The key is a fixed dictionary value and cannot contain duplicate keys or unsupported keys.                                                                                                                                                                                                                                                                           |
   |                 |                 |                                                | -  **value** indicates the matched domain name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------+-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0092__table38371299527:

.. table:: **Table 3** tags

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                      |
   +=================+=================+=================+==================================================================================================================================================================================+
   | key             | Yes             | String          | Specifies the key.                                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | A key contains up to 127 Unicode characters.                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | **key** cannot be empty, an empty string, or spaces. Before using key, delete spaces of single-byte character (SBC) before and after the value.                                  |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | The system does not verify the character set of **key** in searching.                                                                                                            |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values          | Yes             | List<String>    | Specifies the list of values.                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | Each value contains a maximum of 255 Unicode characters. Before using **values**, delete SBC spaces before and after the value.                                                  |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | The value can be an empty array but cannot be left blank.                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | The asterisk (*) is reserved for the system. If the value starts with \*, fuzzy match is performed based on the value following \*. The value cannot contain only asterisks (*). |
   |                 |                 |                 |                                                                                                                                                                                  |
   |                 |                 |                 | The system does not verify the character set of **values** in searching, but verifies the length of **values**.                                                                  |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _waf_02_0092__table10200716215:

.. table:: **Table 4** matches

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                    |
   +=================+=================+=================+================================================================================================+
   | key             | Yes             | String          | Specifies the key.                                                                             |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | The value is fixed to **resource_name**.                                                       |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | value           | Yes             | String          | Specifies the list of values.                                                                  |
   |                 |                 |                 |                                                                                                |
   |                 |                 |                 | Each value contains a maximum of 255 Unicode characters and the character set is not verified. |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+

Response
--------

Response parameters

.. table:: **Table 5** Parameter description

   +-------------+-------------------------------------------------+----------------------------------------------------------------------+
   | Parameter   | Type                                            | Description                                                          |
   +=============+=================================================+======================================================================+
   | resources   | :ref:`Table 6 <waf_02_0092__table786112594181>` | Specifies details about resources that meet the filter criteria.     |
   +-------------+-------------------------------------------------+----------------------------------------------------------------------+
   | total_count | Integer                                         | Specifies the total number of records that meet the filter criteria. |
   +-------------+-------------------------------------------------+----------------------------------------------------------------------+

.. _waf_02_0092__table786112594181:

.. table:: **Table 6** resource

   +-----------------------+---------------------------------------------------+-----------------------------------------------------------------------+
   | Parameter             | Type                                              | Description                                                           |
   +=======================+===================================================+=======================================================================+
   | resource_id           | String                                            | Specifies the resource ID.                                            |
   +-----------------------+---------------------------------------------------+-----------------------------------------------------------------------+
   | resource_detail       | :ref:`Table 8 <waf_02_0092__table22387562>`       | Specifies details about a WAF instance.                               |
   +-----------------------+---------------------------------------------------+-----------------------------------------------------------------------+
   | tags                  | :ref:`Table 7 <waf_02_0092__table10823111182015>` | Specifies the tag list.                                               |
   |                       |                                                   |                                                                       |
   |                       |                                                   | If there is no tag, an empty array is used by default.                |
   +-----------------------+---------------------------------------------------+-----------------------------------------------------------------------+
   | resource_name         | String                                            | Specifies the resource name.                                          |
   |                       |                                                   |                                                                       |
   |                       |                                                   | This parameter is left blank by default if there is no resource name. |
   +-----------------------+---------------------------------------------------+-----------------------------------------------------------------------+

.. _waf_02_0092__table10823111182015:

.. table:: **Table 7** tags

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                              |
   +=======================+=======================+==========================================================================================+
   | key                   | String                | Specifies the key. It contains a maximum of 36 Unicode characters.                       |
   |                       |                       |                                                                                          |
   |                       |                       | The value of **key** must comply with :ref:`Character Set Specifications <waf_02_0086>`. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | value                 | String                | Specifies the value. Each value contains a maximum of 43 Unicode characters.             |
   |                       |                       |                                                                                          |
   |                       |                       | The value must comply with :ref:`Character Set Specifications <waf_02_0086>`.            |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+

.. _waf_02_0092__table22387562:

.. table:: **Table 8** resource_detail

   +-----------------------+-----------------------+------------------------------------------------------+
   | Parameter             | Type                  | Description                                          |
   +=======================+=======================+======================================================+
   | id                    | String                | Specifies the instance ID.                           |
   +-----------------------+-----------------------+------------------------------------------------------+
   | hostname              | String                | Specifies the domain name.                           |
   +-----------------------+-----------------------+------------------------------------------------------+
   | policy_id             | String                | Specifies the policy ID.                             |
   +-----------------------+-----------------------+------------------------------------------------------+
   | protect_status        | Integer               | Specifies the WAF mode.                              |
   |                       |                       |                                                      |
   |                       |                       | -  **0**: disabled.                                  |
   |                       |                       | -  **1**: enabled.                                   |
   |                       |                       | -  **-1**: bypassed.                                 |
   +-----------------------+-----------------------+------------------------------------------------------+
   | access_status         | Integer               | Specifies whether a domain name is connected to WAF. |
   |                       |                       |                                                      |
   |                       |                       | -  **0**: The domain name is not connected to WAF.   |
   |                       |                       | -  **1**: The domain name is connected to WAF.       |
   +-----------------------+-----------------------+------------------------------------------------------+
   | access_code           | String                | Specifies the access code.                           |
   +-----------------------+-----------------------+------------------------------------------------------+
   | proxy                 | Boolean               | Specifies whether a proxy is configured.             |
   |                       |                       |                                                      |
   |                       |                       | -  **true**: A proxy is configured.                  |
   |                       |                       | -  **false**: No proxy is configured.                |
   +-----------------------+-----------------------+------------------------------------------------------+
   | timestamp             | Long                  | Specifies the time when a domain name is created.    |
   +-----------------------+-----------------------+------------------------------------------------------+

Examples
--------

-  Request example

   Sample request when **action** is set to **filter**

   .. code-block::

      {
        "offset": "100",
        "limit": "100",
      "action": "filter",
      "without_any_tag": "true",
        "matches":[
      {
              "key": "resource_name",
              "value": "resource1"
             }
      ],
        "tags": [
          {
            "key": "key1",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "tags_any": [
          {
            "key": "key2",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "not_tags": [
          {
            "key": "key3",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "not_tags_any": [
          {
            "key": "key4",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ]
      }

   Sample request when **action** is set to **count**

   .. code-block::

      {


      "action": "count",
        "matches":[
      {
              "key": "resource_name",
              "value": "resource1"
             }
      ],
        "tags": [
          {
            "key": "key1",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "tags_any": [
          {
            "key": "key2",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "not_tags": [
          {
            "key": "key3",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ],
      "not_tags_any": [
          {
            "key": "key4",
            "values": [
              "*value1",
              "value2"
            ]
          }
        ]
      }

-  Response example

   Response body when **action** is set to **filter**

   .. code-block::

      {
            "resources": [
               {

            "resource_detail": {
                      "id": "1c9ca68c7f704fd398c62c070d96f5be",
                      "proxy": false,
                      "hostname": "www.waf.com",
                      "access_code": "13999b0e29694c09bde09d44b13daaa6",
                      "policy_id": "a2d8418c211e4c88b07c7f57b445a5f6",
                      "timestamp": 1557368735574,
                      "protect_status": 1,
                      "access_status": 0
                  },
                  "resource_id": "cdfs_cefs_wesas_12_dsad",
                  "resource_name": "resouece1",
                  "tags": [
                      {
                         "key": "key1",
                         "value": "value1"
                      },
                      {
                         "key": "key2",
                         "value": "value1"
                      }
                   ]
                }
             ],
            "total_count": 1000
      }

   Response body when **action** is set to **count**

   .. code-block::

      {
             "total_count": 1000
      }

Status Code
-----------

:ref:`Table 9 <waf_02_0092__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0092__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 9** Status code

   =========== =========== ==========================
   Status Code Description Meaning
   =========== =========== ==========================
   200         OK          The request has succeeded.
   =========== =========== ==========================

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
