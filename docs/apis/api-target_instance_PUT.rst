Update Target Instance (PUT)
===============================
Update a specific target instance or part therof.

Note that not all fields are updatable. If non-updatable fields are given in the request this will lead to an error.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target_instances/{target_instance-id} <https://wct-api.readthedocs.io/en/latest/apis/api-target_instances_PUT.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-target_instance_request.rst

Response
--------
200: OK

.. include:: descriptions/desc-response-body-empty.rst

Errors
------
If any error is raised no output is returned.

=== ========================================================================================
400 Bad Request, including reason why e.g. Unsupported or malformed sort spec <sortBy field>
403 Not authorized, user is no longer logged in.
405 Method not allowed, only GET, PUT, DELETE is allowed.
=== ========================================================================================

Example
-------
.. code-block:: linux

  <TODO>