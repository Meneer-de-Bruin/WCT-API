Retrieve Target (GET)
=====================
Returns all information for a specific target.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target/{target-id}  <https://wct-api.readthedocs.io/en/latest/apis/api-target_GET.html>`_

Also the following parts can be retrieved seperatly by adding the part name to the request query, e.g.
`https://--WCT_base--/api/v1/target/{target-id}/{part}  <https://wct-api.readthedocs.io/en/latest/apis/api-target_GET.html>`_

===========
**part**
-----------
general
seeds
profile
schedule
annotations
description
groups
access
===========

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-request-body-empty.rst

Response
--------
200: OK

.. include:: descriptions/desc-target.rst

Errors
------
If any error is raised no output is returned.

=== ==========================================================================
400 Bad request, non-existing target-id has been given.
400 Bad request, non-existing part has been given.
403 Not authorized, user is no longer logged in.
405 Method not allowed, only GET, POST, PUT, DELETE are allowed.
=== ==========================================================================
