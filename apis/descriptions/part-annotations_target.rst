---------------------
**Part: annotations**
---------------------
A list of annotations properties that belong to a target. This contains the following information:

============== ====== ========
**annotations**
------------------------------ 
selection      Part   Required
evaluationNote String Optional
harvestType    String Optional
annotations    List   Optional
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
.. include:: descriptions/desc-formatDate.rst

| **type**
| Contains one of the following: Area, Collection, Other collections, Producer type, Publication type.
