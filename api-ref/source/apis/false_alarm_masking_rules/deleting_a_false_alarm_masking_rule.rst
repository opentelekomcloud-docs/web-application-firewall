:original_name: waf_02_0068.html

.. _waf_02_0068:

Deleting a False Alarm Masking Rule
===================================

Function Description
--------------------

This API is used to delete a false alarm masking rule.

URI
---

-  URI format

   DELETE /v1/{project_id}/waf/policy/{policy_id}/ignore/{ignore_rule_id}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +----------------+-----------+--------+-------------------------------------------------+
      | Parameter      | Mandatory | Type   | Description                                     |
      +================+===========+========+=================================================+
      | project_id     | Yes       | String | Specifies the project ID.                       |
      +----------------+-----------+--------+-------------------------------------------------+
      | policy_id      | Yes       | String | Specifies the policy ID.                        |
      +----------------+-----------+--------+-------------------------------------------------+
      | ignore_rule_id | Yes       | String | Specifies the ID of a false alarm masking rule. |
      +----------------+-----------+--------+-------------------------------------------------+

Request
-------

Request parameters

None

Response
--------

Response parameters

None

Status Code
-----------

:ref:`Table 2 <waf_02_0068__waf_02_0016_waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0068__waf_02_0016_waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 2** Status code

   +-------------+-------------+---------------------------------------------------------------------------------+
   | Status Code | Description | Meaning                                                                         |
   +=============+=============+=================================================================================+
   | 204         | No Content  | The server successfully processed the request and is not returning any content. |
   +-------------+-------------+---------------------------------------------------------------------------------+

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
