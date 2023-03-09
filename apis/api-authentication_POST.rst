Create token (POST)
===================
Takes username and password as input and returns a token that is valid until <x> minutes of inactivity. The time 
of inactivity (<x>) is configurable in WCT.


Each call to a WCT API (except for authentication for obvious reasons) must contain a valid token. The token must 
be added to the HTTP header of each call:
Authorization: Bearer <token> 

If the user cannot be authenticated based upon the given username and password an error is returned.

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/token

Header
------
There are no specific header fields for this API.

Body
----
======== ====== ========
**POST**
------------------------
username String Required
password String Required
======== ====== ========

**username**

Username of to be authenticated user in WCT.

**password**

Password of to be authenticated user in WCT.

Response
--------
200: OK

===== ====== ========
**Body**
---------------------
token String Optional
===== ====== ========

Errors
------
If any error is raised no token is returned.

=== ==================================================================
400 Bad Request, if username and/or password is not given.
403 Not authorized, with given username and password.
405 Method not allowed, if anything other then POST or DELETE is used.
=== ==================================================================
