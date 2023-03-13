Delete token (DELETE)
=====================
Takes username, password and token as input and invalidates the specified token. This essentially menas the user logs out.

If the user cannot be authenticated based upon the given username and password an error is returned. 

If the token is unknown no error is given. This could happen if the token already has been invalidated due to inactivity. 

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/token/{token} <https://--WCT_base--/api/v1/token/{token}>`_

| **token**
| Token is given upon a succesful login via the API :doc:`api-authentication_POST`.

Header
------
There are no specific header fields for this API.

Body
----
.. include:: descriptions/desc-request-body-empty

Response
--------
200: OK

**Body**
--------
.. include:: descriptions/desc-response-body-empty

Errors
------
If any error is the token given is not invalidated.

=== ==================================================================
405 Method not allowed, if anything other then DELETE is used.
=== ==================================================================
