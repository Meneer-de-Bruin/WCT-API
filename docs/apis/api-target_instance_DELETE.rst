Delete Target instance (DELETE)
===============================
Deletes a specific target instance. This is only possible if the status of the target instance is 'Scheduled', 'Aborted' or 'Rejected'. After a delete the target instance will have been completly removed from the WCT database.

If the target instance must be set to 'Rejected' the API :doc:`api-target_instance_PUT` must be used.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target_instances/{target_instance-id} <https://wct-api.readthedocs.io/en/latest/apis/api-target_instance_DELETE.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-request-body-empty.rst

Response
--------
200: OK

.. include:: descriptions/desc-response-body-empty.rst

Errors
------
If any error is raised no output is returned. Nor is the target removed.

=== =======================================================================================
400 Bad request, non-existing target_instnace-id has been given.
400	Bad request, cannot delete as target instance is not scheduled, aborted or rejected. 
403 Not authorized, user is no longer logged in.
405 Method not allowed, only GET, PUT, DELETE are allowed.
=== =======================================================================================

Example
-------
.. code-block:: linux

  <TODO>