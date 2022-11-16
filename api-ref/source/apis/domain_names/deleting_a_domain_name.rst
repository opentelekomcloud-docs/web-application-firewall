:original_name: waf_02_0016.html

.. _waf_02_0016:

Deleting a Domain Name
======================

Function Description
--------------------

This API is used to delete a domain name.

.. important::

   Deleting a domain name relies on some components, such as DNS. These components may cause deletion failed.

URI
---

-  URI format

   DELETE /v1/{project_id}/waf/instance/{instance_id}?keepPolicy={keepPolicy}

-  Parameter description

   .. table:: **Table 1** Path parameters

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
      | Parameter       | Mandatory       | Type            | Description                                                         |
      +=================+=================+=================+=====================================================================+
      | project_id      | Yes             | String          | Specifies the project ID.                                           |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
      | instance_id     | Yes             | String          | Specifies the instance ID or domain ID.                             |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
      | keepPolicy      | No              | Boolean         | Specifies whether to retain the policy when deleting a domain name. |
      |                 |                 |                 |                                                                     |
      |                 |                 |                 | -  **true**: The policy is retained.                                |
      |                 |                 |                 | -  **false**: The policy is deleted.                                |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+

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

:ref:`Table 2 <waf_02_0016__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0>` describes the normal status code returned by the API.

.. _waf_02_0016__waf_02_0012_t82c3440f3efb42a38b9d4dc4011a33d0:

.. table:: **Table 2** Status code

   +-------------+-------------+---------------------------------------------------------------------------------+
   | Status Code | Description | Meaning                                                                         |
   +=============+=============+=================================================================================+
   | 204         | No Content  | The server successfully processed the request and is not returning any content. |
   +-------------+-------------+---------------------------------------------------------------------------------+

For details about error status codes, see :ref:`Status Codes <waf_02_0085>`.
