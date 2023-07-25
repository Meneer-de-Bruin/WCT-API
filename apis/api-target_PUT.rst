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

Example
-------
.. code-block:: linux

  curl \
  --location 'http://localhost/wct/api/v1/targets/<target-id>' \
  --header 'Authorization: Bearer <token>' \ 
  --header 'Content-Type: application/json' \
  --data-raw '{"general": { \
    "owner": "demo", \
    "state": 2, \
    "name" : "TEST - TARGET 2023-07-06T09:43:09.816Z" \
 } \
}'

.. code-block:: linux

  curl --location 'http://localhost/wct/api/v1/targets' \
  --header 'Authorization: Bearer <token>' \
  --header 'Content-Type: application/json' \
  --data-raw '{
    "general": {
        "owner": "demo",
        "state": 5,
        "name": "TEST - TARGET 2023-07-12T11:35:21.376Z - IJsselbiënale",
        "description": "info@ijsselbiennale.nl"
    },

    "profile": {
        "id": "1",
        "imported": false,
        "harvesterType": "HERITIRX3",
        "name": "Default - KB",
        "overrides": [
            {
                "id": "ignoreRobots",
                "value": true,
                "enabled": true
            }
        ]
    },

    "groups": [{"id": 70, "name": "testgroep"}],

    "description": {
        "description": "Test target",
        "type": "01 - Algemeen"
    },

    "access": {
        "displayTarget": true,
        "accessZone": "0",
        "accessZoneText": "Public"
    },

    "annotations": { 
        "selection": {
            "date": "2023-05-17T13:37:13.919+00:00",
            "note": null,
            "type": "Producer type"
        },
        "annotations": [
            {
            "date": "2023-05-17T13:37:13.919+00:00",
            "note": "Testannotatie no.1",
            "user": "demo",
            "alert": false
            },
            {
            "date": "2023-06-17T13:37:13.919+00:00",
            "note": "Testannotatie no.2",
            "user": "demo",
            "alert": true
            }
        ],
        "evalutionNote": null,
        "harvestType": "Subject"
    },

    "seeds": [
        {
            "seed": "https://ijsselbiennale.nl/",
            "primary": true,
            "authorisations": [98304]
        }
    ],
    
    "schedule": {
        "harvestOptimization": false,
        "schedules": [
            {
                "cron": "00 23 25 7,8,9 ? *",
                "startDate": "2019-12-03T15:55:22.000+00:00",
                "type": -3,
                "nextExecutionDate": "2024-12-03T15:55:22.000+00:00",
                "owner": "demo"
            }
        ]
    }
}'