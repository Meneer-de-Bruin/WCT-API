Retrieve Target Instance (GET)
==============================
Returns all information for a specific target instance.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target_instances/{target-instance-id} <https://wct-api.readthedocs.io/en/latest/apis/api-target_instance_GET.html>`_

Also the following parts can be retrieved separately by adding the part name to the request query, e.g.
`https://--WCT_base--/api/v1/target_instances/{target-instance-id}/{part}  <https://wct-api.readthedocs.io/en/latest/apis/api-target_instance_GET.html>`_

+-----------------+
| **part**        |
+=================+
| general         | 
+-----------------+
| profile         |
+-----------------+
| harvest state   |
+-----------------+
| logs            |
+-----------------+
| harvest results |
+-----------------+
| annotations     |
+-----------------+
| display         |
+-----------------+

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-request-body-empty.rst

Response
--------
200: OK

.. include:: descriptions/desc-target_instance_response.rst

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
.. code-block:: linux

  <TODO>