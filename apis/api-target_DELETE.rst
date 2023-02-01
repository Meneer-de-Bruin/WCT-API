Delete Target (DELETE)
======================
Deletes a specific target. This is only possible if there are no attached target instances. 

If one wishes to set the target to 'Rejected' then one must use the update target API :doc:`TEST<api-target_PUT>`

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target/<targetID>

Header
------
Authorization: Bearer <token>

Body
----
============ ====== ========
**DELETE**
---------------------------- 
============ ====== ========

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
============ ====== ========

Errors
------
If any error is raised no output is returned.

=== ===============================================
400 Bad request, if non-existing targetID is given.
403 Not authorized, with given token.
405 Method not allowed, if anything other then GET, POST, PUT, DELETE is used.
=== ===============================================
