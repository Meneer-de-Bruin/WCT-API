Update Target (PUT)
===================
Update a specific target or part therof.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/targets/{target-id} <https://wct-api.readthedocs.io/en/latest/apis/api-target_PUT.html>`_

Also the following parts can be updated separately by adding the part name to the request query, e.g.
`https://--WCT_base--/api/v1/target/{target-id}/{part}  <https://wct-api.readthedocs.io/en/latest/apis/api-target_PUT.html>`_

+-------------+
| **part**    |
+=============+
| general     | 
+-------------+
| seeds       |
+-------------+
| profile     |
+-------------+
| schedule    |
+-------------+
| annotations |
+-------------+
| description |
+-------------+
| groups      |
+-------------+
| access      |
+-------------+

target-id and creationdate can never be updated. These are system generated.

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
All required values, except for target-id and creationDate, must be given. If target-id or creationDate are given then these are ignored.

.. include:: descriptions/desc-target.rst

Response
--------
200: OK

The updated target (or part therof) is returned as if the API :doc:`api-target_GET` had been used.

Errors
------
If any error is raised no output is returned. Nor is the target created.

=== =======================================================================================
400	Bad request, required value <element> has not been given.
403 Not authorized, user is no longer logged in.
405 Method not allowed, only POST, GET, PUT, DELETE are allowed.
=== =======================================================================================
