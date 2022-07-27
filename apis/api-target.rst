==========
API Target
==========

Retrieve Targets (GET)
======================
Returns all targets with a subset of the available information based upon given filter and sorting.

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/targets

====== ====== ========
**GET**
----------------------
filter String Optional
sortBy String Optional
offset Number Optional
limit  Number Optional
====== ====== ========

**filter**

Name of field upon which the result set must be filtered. Only filterable fields maybe given, others are ignored. Filterable fields are:

* targetId [exact match only]
* name [contains text]
* seed [contains text]
* agency [exact match only]
* userId [exact match only]
* description [contains text]
* groupName [contains text]
* states [List of integers, exact match only]

Multiple filter fields may be given, but each field only once. If a filter field is given multiple times this will result in an error.

With each field (key) a value must be given which is used to filter. The filter only shows those results that match or contains the given value in the given field. All given characters are used, there are no wild cards.

The state of a target is an integer with the following values:
========= =======================
**state** **Human readable text**
--------- -----------------------
1         Pending
2         Reinstated
3         Nominated
4         Rejected
5         Approved
6         Cancelled
7         Completed
========= =======================
  
**sortBy**

Name of field upon which the result set must be sorted. The field name must be followed by an indication if the sorting must be ascending (asc) or descending (desc).

Only sortable fields maybe given, others are ignored. Sortable fields are:

* name (default)
* creationDate

Only one sort field may be given as input. If multiple sort fields are given then this will result in an error.

Example:
Sortby=Name,asc

**offset**

Specifies the number of rows in the result set to skip before limiting starts. 
Default: 0
Minimum: 0

The results page shown is equal to:
TRUNC(**offset** / **limit**) + 1

So the if the **offset** value is not a multiple of the **limit** value then the results page shown is the page upon which the offset row is present.

E.g. If **limit** is 10 and **offset** is 19 then the page shown is TRUNC(19/10) + 1 = 2.

**limit**

Number of records returned from the offset.
Default: 10
Minimum: 10
Maximum: 100

This is the amount of rows shown on a results page.

Response
--------
200: OK

======= ====== ========
**Body**
-----------------------
filter  String Required
sortBy  String Required
offset  Number Required
limit   Number Required
targets List   Optional
======= ====== ========

**targets**
This is a list of found targets. It could be that no targets are returned.

The following information is returned per found target:
======= ====== ========
**Body**
-----------------------
targetId Number Required
======== ====== ========

Errors
------
If any error is raised no output is returned.

=== ===============================================
403 Not authorized with given token
405 Invalid input
=== ===============================================