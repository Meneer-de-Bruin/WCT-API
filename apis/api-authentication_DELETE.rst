Delete token (DELETE)
=====================
Takes token as input and invalidates the specified token. This essentially menas the user logs out.

If the token is unknown no error is given. This could happen if the token already has been invalidated due to inactivity. 

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/token/{token} <https://wct-api.readthedocs.io/en/latest/apis/api-authentication_DELETE.html>`_

.. include:: descriptions/desc-token.rst

Header
------
There are no specific header fields for this API.

Body
----
.. include:: descriptions/desc-request-body-empty.rst

Response
--------
200: OK

**Body**
--------
.. include:: descriptions/desc-response-body-empty.rst

Errors
------
If any error is raised then the token given is not invalidated.

=== ==================================================================
405 Method not allowed, only DELETE is allowed.
=== ==================================================================
