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

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-target_request.rst

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

Example
-------
.. code-block:: linux

  curl \
  --location 'http://localhost/wct/api/v1/targets/<target-id>' 
  --header 'Authorization: Bearer <token>'  
  --header 'Content-Type: application/json' 
  --data-raw '{ 
    "general": { 
      "owner": "demo", 
      "state": 2, 
      "name" : "TEST - TARGET 2023-07-06T09:43:09.816Z" 
    } 
  }'