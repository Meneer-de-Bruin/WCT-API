Retrieve Profiles (GET)
============================

Returns all profiles with a subset of the available information based upon given filter.

Version
-------
1.0.0

Request
-------
`https://--WCT_base--/api/v1/profiles <https://wct-api.readthedocs.io/en/latest/apis/api-profiles_GET.html>`_

Header
------
.. include:: descriptions/desc-header-authentication.rst

Body
----
.. include:: descriptions/desc-query-method.rst

====== ====== ========
filter String Optional
====== ====== ========

| **filter**
| Name of field upon which the result set must be filtered. Only filterable fields maybe given, others are ignored. Filterable fields are:

* status [Boolean]
* agency [contains text]
* profileType [contains text]

| Multiple filter fields may be given, but each field only once. If a filter field is given multiple times this will result in an error.
|
| With each field (key) a value must be given which is used to filter. The filter only shows those results that match or contains the given value in the given field. All given characters are used, there are no wild cards.

| **profileType**
| There are only two types:

* HERITRIX1
* HERITRIX3 (default)

Response
--------
200: OK

========== ====== ========
**Body**
--------------------------
filter     String Required
profiles   List   Optional
========== ====== ========

| **profiles**
| This is a list of found profiles. It could be that no profiles are present. In that case an empty list is returned.
 
The following information is returned per found profile:

============ ======= ========
**Body**
----------------------------
name         String  Required
default      Boolean Required
description  String  Optional
profileType  String  Required
status       Boolean Required
agency       String  Required
============ ====== ========

| **default**
| Per profileType only 1 profile with default=True is allowed.

| **profileType**
| There are only two types:

* HERITRIX1
* HERITRIX3 (default)

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

  TODO
 
 
 