Retrieve Target Instances (GET)
===============================
Returns all target instances with a subset of the available information based upon given filter and sorting.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/target_instances <https://wct-api.readthedocs.io/en/latest/apis/api-target_instances_GET.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
The body of the request contains the parameters voor the retrieval of the target instances. This has been done to ensure that the length of the GET URL does not exceed the maximum length. 

The body of the request is empty as this is a GET request. All information must be passed on to the API via query parameters.

====== ====== ========
filter String Optional
sortBy String Optional
offset Number Optional
limit  Number Optional
====== ====== ========

| **filter**
| Name of field upon which the result set must be filtered. Only filterable fields maybe given, others are ignored. Filterable fields are:

* targetInstanceId [exact match only]
* from [harvestDate is larger or equal to this date]
* to [harvestDate is smaller or equal to this date]
* agency [exact match only]
* userId [exact match only]
* name [contains text]
* flag [exact match only]
* nonDisplayOnly [Boolean]
* state [List of integers, exact match only]
* QARecommendation [List of integers, exact match only]

| Multiple filter fields may be given, but each field only once. If a filter field is given multiple times this will result in an error.
|
| With each field (key) a value must be given which is used to filter. The filter only shows those results that match or contains the given value in the given field. All given characters are used, there are no wild cards.

.. include:: descriptions/desc-userId.rst

.. include:: descriptions/desc-state_target_instance.rst

| **sortBy**
| Name of field upon which the result set must be sorted. The field name must be followed by an indication if the sorting must be ascending (asc) or descending (desc).

| Only sortable fields maybe given, others are ignored. Sortable fields are:
| * name (default)
| * harvestDate

Only one sort field may be given as input. If multiple sort fields are given then this will result in an error. Example: sortBy=Name,asc

.. include:: descriptions/desc-request-offset.rst

.. include:: descriptions/desc-request-limit.rst

Response
--------
200: OK

========== ====== ========
**Body**
--------------------------
filter     String Required
sortBy     String Required
offset     Number Required
limit	   Number Required
amount 	   Number Required
instances  List   Optional
========== ====== ========

| **amount**
| Number of total targets in the search result.  

| **instances**
| This is a list of found target instances. It could be that no target instances are returned.
 
The following information is returned per found target instance:

================ ====== ========
**Body**
--------------------------------
instanceId       Number Required
thumbnail        Image  Optional
harvestDate      Date   Required 
name             String Required
owner            String Required
state            Number Required
runtime          Time   Optional
dataDownloaded   Number Optional
AmountURLs       Number Optional
pFailed          Number Optional
AmountCrawls     Number Optional
QARecommendation Number Optional
flag             Number Optional
================ ====== ========

.. include:: descriptions/desc-harvestDate.rst

.. include:: descriptions/desc-state_target_instance.rst

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