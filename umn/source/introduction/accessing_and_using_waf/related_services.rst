:original_name: waf_01_0051.html

.. _waf_01_0051:

Related Services
================

This section describes the relationship between WAF and other cloud services.

CTS
---

Cloud Trace Service (CTS) provides records of operations on WAF. With CTS, you can query, audit, and backtrack these operations. For details, see the *Cloud Trace Service User Guide*.

.. table:: **Table 1** WAF operations that can be recorded by CTS

   +---------------------------------------------------+-------------------+-------------------------+
   | Operation                                         | Resource Type     | Trace Name              |
   +===================================================+===================+=========================+
   | Creating a WAF instance                           | instance          | createInstance          |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a WAF instance                           | instance          | deleteInstance          |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a WAF instance                          | instance          | modifyInstance          |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying the protection status of a WAF instance | instance          | modifyProtectStatus     |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying the connection status of a WAF instance | instance          | modifyAccessStatus      |
   +---------------------------------------------------+-------------------+-------------------------+
   | Creating a policy                                 | policy            | createPolicy            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Applying a policy                                 | policy            | applyToPolicy           |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a policy                                | policy            | modifyPolicy            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a policy                                 | policy            | deletePolicy            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying alarm notification settings             | alertNoticeConfig | modifyAlertNoticeConfig |
   +---------------------------------------------------+-------------------+-------------------------+
   | Uploading a certificate                           | certificate       | createCertificate       |
   +---------------------------------------------------+-------------------+-------------------------+
   | Changing the name of a certificate                | certificate       | modifyCertificate       |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a certificate                            | certificate       | deleteCertificate       |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a CC attack protection rule                | policy            | createCc                |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a CC attack protection rule             | policy            | modifyCc                |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a CC attack protection rule              | policy            | deleteCc                |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a precise protection rule                  | policy            | createCustom            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a precise protection rule               | policy            | modifyCustom            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a precise protection rule                | policy            | deleteCustom            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a blacklist or whitelist rule              | policy            | createWhiteblackip      |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a blacklist or whitelist rule           | policy            | modifyWhiteblackip      |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a blacklist or whitelist rule            | policy            | deleteWhiteblackip      |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a web tamper protection rule               | policy            | createAntitamper        |
   +---------------------------------------------------+-------------------+-------------------------+
   | Updating a web tamper protection rule             | policy            | refreshAntitamper       |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a web tamper protection rule             | policy            | deleteAntitamper        |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a false alarm masking rule                 | policy            | createIgnore            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a false alarm masking rule               | policy            | deleteIgnore            |
   +---------------------------------------------------+-------------------+-------------------------+
   | Adding a data masking rule                        | policy            | createPrivacy           |
   +---------------------------------------------------+-------------------+-------------------------+
   | Modifying a data masking rule                     | policy            | modifyPrivacy           |
   +---------------------------------------------------+-------------------+-------------------------+
   | Deleting a data masking rule                      | policy            | deletePrivacy           |
   +---------------------------------------------------+-------------------+-------------------------+

Cloud Eye
---------

Cloud Eye monitors the metrics of WAF, so that you can understand the protection status of WAF in a timely manner, and set protection policies accordingly. For details, see the *Cloud Eye User Guide*.

For details about monitoring metrics, see :ref:`Monitoring Metrics <waf_01_0092>`.

TMS
---

Tag Management Service (TMS) is a visualized service for fast and unified tag management that enables you to label and manage WAF instances by tags.

.. table:: **Table 2** WAF operations supported by TMS

   =========================== ============= =================
   Operation                   Resource Type Event Name
   =========================== ============= =================
   Creating a WAF instance tag Tag           createResourceTag
   Deleting a WAF instance tag Tag           deleteResourceTag
   =========================== ============= =================

IAM
---

Identity and Access Management (IAM) provides the permission management function for WAF. Only users granted with the WAF Administrator permissions can use WAF. To obtain the permissions, contact users who have the Security Administrator permissions. For details, see the *Identity and Access Management User Guide*.

SMN
---

The Simple Message Notification (SMN) service provides the notification function. After the notification function is enabled in WAF, users will receive an SMS message or email when an attack on a protected domain is detected.

For details about SMN, see the *Simple Message Notification User Guide*.
