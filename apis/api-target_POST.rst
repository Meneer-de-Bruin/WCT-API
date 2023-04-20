Create Target (POST)
====================
Create a target.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/targets <https://wct-api.readthedocs.io/en/latest/apis/api-target_POST.html>`_

target-id and creationdate can never be created. These are system generated. 

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
All required values, except for target-id and creationDate, must be given.

.. include:: descriptions/desc-target.rst

Response
--------
200: OK

The inserted target is returned as if the API :doc:`api-target_PUT` had been used.

Errors
------
If any error is raised no output is returned. Nor is the target created.

=== =======================================================================================
400	Bad request, required value <element> has not been given.
403 Not authorized, user is no longer logged in.
405 Method not allowed, only POST, GET, PUT, DELETE are allowed.
=== =======================================================================================
