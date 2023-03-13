Retrieve Target (GET)
=====================
Returns all information for a specific target.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target/{target-id}  <https://wct-api.readthedocs.io/en/latest/apis/api-target_GET.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

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

.. include:: descriptions/desc-creationDate.rst
.. include:: descriptions/desc-state_target.rst
.. include:: descriptions/desc-seeds.rst

Errors
------
If any error is raised no output is returned.

=== ==========================================================================
400 Bad request, if non-existing targetID is given.
403 Not authorized, with given token.
405 Method not allowed, if anything other then GET, POST, PUT, DELETE is used.
=== ==========================================================================
