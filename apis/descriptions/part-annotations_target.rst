---------------------
**Part: annotations**
---------------------
A list of annotations properties that belong to a target. This contains the following information:

============== ====== ========
**annotations**
------------------------------ 
evaluationNote String Optional
harvestType    String Optional
annotations    List   Optional
selection      List   Required
============== ====== ========

| **harvestType**
| Contains one of the following: Event, Subject, Team

| ** annotations**
| A list of annotations containing the following information:

===== ======= ========
**annotations**
---------------------- 
date  Date    Required
note  String  Required
user  String  Required
alert Boolean Required
===== ======= ========

| **date**
.. include:: descriptions/desc-formatDate.rst

.. include:: descriptions/desc-user.rst	
			
---------------------
**Part: selection**
---------------------
Contains the following information:

==== ====== ========
**selection**
--------------------
date Date   Required
type String Optional
note String Optional
==== ====== ========

| **date**
.. include:: descriptions/desc-formatDate.rst

| **type**
| Contains one of the following: Area, Collection, Other collections, Producer type, Publication type.


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