==================
API Authentication
==================

Create token (POST)
===================
Takes username and password as input and returns a token that is valid until <x> minutes of inactivity. The time 
of inactivity (<x>) is configurable in WCT.

If the user cannot be authenticated an error is returned.

Version
-------
1.0.0

Request
-------
https://<WCT_base>/api/1.0.0/create_token

======== ====== ========
POST
username String Required
password String Required
======== ====== ========

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
==== ===============================================
403: Not authorized with given username and password
405: Invalid input
==== ===============================================
