================ ======= ========
**Body**
---------------------------------
general          List    Optional
harvest results  List    Optional
annotations      List    Optional
display          List    Optional
================ ======= ========

-----------------
**part: general**
-----------------
A list of general properties that belong to a target instance. This contains the following information:

=================== ======= ========
**general**
------------------------------------
owner               String  Optional
flagId              Number  Optional
=================== ======= ========

.. include:: descriptions/desc-owner.rst

.. include:: descriptions/desc-flagId.rst

-------------------------
**part: harvest results**
-------------------------
A list of harvest results that belong to a target instance. This contains the following information:

=============== ====== ========
**harvest results**
-------------------------------
HarvestResultId Number Required
state           Number Required
=============== ====== ========

.. include:: descriptions/desc-state_harvest_result.rst

---------------------
**part: annotations**
---------------------
A list of annotations that belong to a target instance. This contains the following information:

============ ======= ========
**annotations**
-----------------------------
Id           Number  Optional
Annotation   String  Required
Alert        Boolean Required
============ ======= ========

| **Id**
Must be given when updating an existing annotation. If adding an annotaion it can be left empty.

| **creationDate**
.. include:: descriptions/desc-formatDate.rst

.. include:: descriptions/part-display_target_instance.rst
