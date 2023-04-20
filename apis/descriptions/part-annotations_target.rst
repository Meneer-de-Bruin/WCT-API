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
selection      Part   Required
============== ====== ========

| **harvestType**
| Contains one of the following: Event, Subject, Team

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
| This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

| **type**
| Contains one of the following: Area, Collection, Other collections, Producer type, Publication type
