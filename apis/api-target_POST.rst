Create Target (POST)
======================
<TODO>

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target

============ ====== ========
**POST**
---------------------------- 
name		 Text	Required
agency		 Text	Required
owner		 Text	Required
status		 Number Required
seeds		 List   Required
...          ...    ...
============ ====== ========

**seeds**

A list of seeds containing the following information:


======= ======= ========
**seeds**
------------------------
seed	URL	    Required
primary Boolean	Required
======= ======= ========

**primary**

This indicates if a seed is the primary seed, or not. There can only be one primary seed.

Response
--------
200: OK

All the input given is returned with the following additional information:

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
creationDate Date 	Required 
============ ====== ========


**creationDate**

This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

Errors
------
If any error is raised no output is returned.

=== ===============================================
400
403 Not authorized with given token
405 Method not allowed
=== ===============================================

Retrieve Target (GET)
=====================
<TODO>

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target/<targetID>

============ ====== ========
**GET**
---------------------------- 
============ ====== ========

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
creationDate Date 	Required
...          ...    ...
============ ====== ========

**creationDate**

This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

Errors
------
If any error is raised no output is returned.

=== ===============================================
403 Not authorized with given token
405 Invalid input
=== ===============================================

Update Target (PUT)
===================
<TODO>

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target/<targetID>

============ ====== ========
**PUT**
---------------------------- 
============ ====== ========

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
creationDate Date 	Required
...          ...    ...
============ ====== ========

**creationDate**

This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

Errors
------
If any error is raised no output is returned.

=== ===============================================
403 Not authorized with given token
405 Invalid input
=== ===============================================

Delete Target (DELETE)
======================
<TODO>

Version
-------
1.0.0

Request
-------
https://--WCT_base--/api/v1/target/<targetID>

============ ====== ========
**DELETE**
---------------------------- 
============ ====== ========

Response
--------
200: OK

============ ====== ========
**Body**
----------------------------
targetId 	 Number Required
creationDate Date 	Required
...          ...    ...
============ ====== ========

**creationDate**

This field has the format: YYYY-MM-DDTHH:MM:SS.S+HH:MM, E.g. 2020-09-24T10:31:33.000+00:00.

Errors
------
If any error is raised no output is returned.

=== ===============================================
403 Not authorized with given token
405 Invalid input
=== ===============================================
