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
.. include:: descriptions/desc-request-body-empty

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
400 Bad request, non-existing target-id has been given.
403 Not authorized, user is no longer logged in.
405 Method not allowed, only GET, POST, PUT, DELETE are allowed.
=== ==========================================================================
