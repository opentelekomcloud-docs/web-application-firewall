:original_name: waf_01_0095.html

.. _waf_01_0095:

Why Do Cookies Contain the CLOUDWAFSESID and CLOUDWAFSESTIME Fields After a Domain is Connected to WAF?
=======================================================================================================

When a visitor accesses a protected domain name, WAF automatically inserts the **CLOUDWAFSESID** and **CLOUDWAFSESTIME** fields into the cookie of the access request. The fields are described as follows:

-  **CLOUDWAFSESID**: indicates the session ID of WAF.
-  **CLOUDWAFSESTIME**: indicates the timestamp of WAF.

Fields **CLOUDWAFSESID** and **CLOUDWAFSESTIME** inserted into cookies are used for WAF to implement its functions only, such as statistical functions. There are no impacts on web services.
