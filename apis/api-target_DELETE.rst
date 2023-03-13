Delete Target (DELETE)
======================
Deletes a specific target. This is only possible if there are no attached target instances. After a delete the target will have been completly removed from the WCT database.

If the target must be set to 'Rejected' then the API :doc:`api-target_PUT` must be used.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target/{target-id} <https://--WCT_base--/api/v1/target/{target-id}>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-request-body-empty

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
target-id    Number Required
============ ====== ========

Errors
------
If any error is raised no output is returned. Nor is the target removed.

=== ==========================================================================
400 Bad request, if non-existing targetID is given.
403 Not authorized, with given token.
405 Method not allowed, if anything other then GET, POST, PUT, DELETE is used.
=== ==========================================================================
