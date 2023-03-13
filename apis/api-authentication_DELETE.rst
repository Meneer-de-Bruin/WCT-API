Delete token (DELETE)
===================
Takes username, password and token as input and invalidates the specified token. This essentially menas the user logs out.

If the user cannot be authenticated based upon the given username and password an error is returned. 

If the token is unknown no error is given. This could happen if the token already has been invalidated due to inactivity. 

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/token/{token} <https://--WCT_base--/api/v1/token/{token}>`_

**token**
| Token is given upon a succesful login via the API :doc:`api-authentication_POST`.

Header
------
There are no specific header fields for this API.

Body
----
The body of the request is empty. No additional information is required.

**username**

Username of to be authenticated user in WCT.

**password**

Password of to be authenticated user in WCT.

Response
--------
200: OK

**Body**
--------
The body of the response is empty.

Errors
------
If any error is the token given is not invalidated.

=== ==================================================================
400 Bad Request, if username and/or password is not given.
403 Not authorized, with given username and password.
405 Method not allowed, if anything other then POST or DELETE is used.
=== ==================================================================

