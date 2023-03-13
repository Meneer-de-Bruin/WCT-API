Retrieve Target (GET)
=====================
Returns all information for a specific target.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target/{target-id}  <https://--WCT_base--/api/v1/target/{target-id}>`_

Header
------
Authorization: Bearer <token>

To get a token the user must login via the API :doc:`api-authentication_PUT`.

Body
----
The body of the request is empty. No additional information is required.

Response
--------
200: OK

============ ======= ========
**Body**
-----------------------------
target-id    Number  Required
creationDate Date    Required 
name         Text    Required
agency       Text    Required
owner-id     Number  Required
state        Number  Required
description  String  Optional
refNumber    String  Optional
automatedQA  Boolean Required
autoPrune    Boolean Required
refCrawl     Boolean Required
request      String  Optional
seeds        List    Required
profile      List    Required
schedule     List    Required
annotations  List    Optional
description  List    Optional
groups       List    Optional
access       List    Required
============ ======= ========

| **creationDate**
| This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

.. include:: descriptions/desc-state_target.rst

| **seeds**
| A list of seeds containing the following information:

======= ======= ========
**seeds**
------------------------
seed	URL	    Required
primary Boolean	Required
======= ======= ========

| **primary**
| This indicates if a seed is the primary seed, or not. There can only be one primary seed.

| **profile**
| **schedule**
| **annotations**
| **description**
| **groups**
| **access**

Errors
------
If any error is raised no output is returned.

=== ==========================================================================
400 Bad request, if non-existing targetID is given.
403 Not authorized, with given token.
405 Method not allowed, if anything other then GET, POST, PUT, DELETE is used.
=== ==========================================================================
