API Authentication
==================
Create token (POST)
===================
Takes username and password as input and returns a token that is valid until <x> minutes of inactivity. The time 
of inactivity (<x>) is configurable in WCT.

If the user cannot be authenticated an error is returned.

Request
-------
* -POST
* -username	
  -String - Required.
* -password	
  -String - Required.

Response
--------
* -200: OK
* -token	

Errors
------
* -403: Not authorized with given username and password
* -405: Invalid input