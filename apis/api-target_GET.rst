Retrieve Target (GET)
=====================
<TODO>

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target/<targetID>

Header
------
Authorization: Bearer <token>

To get a token the user must login via the API :doc:`api-authentication_POST`.

Body
----
============ ====== ========
**GET**
---------------------------- 
============ ====== ========

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
creationDate Date 	Required
...          ...    ...
============ ====== ========

**creationDate**

This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

Errors
------
If any error is raised no output is returned.

=== ===============================================
403 Not authorized with given token
405 Invalid input
=== ===============================================
