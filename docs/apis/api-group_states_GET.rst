Retrieve Group states (GET)
============================

Returns a list of all the states that a group can have, including the description of each specific state.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/groups/states <https://wct-api.readthedocs.io/en/latest/apis/api-group_states_GET.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-request-body-empty.rst

Response
--------
200: OK

====== ==== ========
**Body**
--------------------
states List Required
====== ==== ========

| **states**
| Is a list of all the states that a target can have, including the description of each specific state.

.. include:: descriptions/desc-state_group.rst

Errors
------
If any error is raised no output is returned.

=== ========================================================================================
400 Bad Request, including reason why e.g. Unsupported or malformed sort spec <sortBy field>
403 Not authorized, user is no longer logged in.
405 Method not allowed, only GET is allowed.
=== ========================================================================================

Example
-------
<TODO> 