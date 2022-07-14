==========
Principles
==========

Maturity
========
We want to strive to a fully mature RESTful services as defined by the Richardson maturity model (<link>). 
Important here is that we not only adhere to the REST principals (<link>), but also implement Hypertext As 
The Engine Of Application State (HATEOAS).

Request
=======
All REST API calls make use of HTTPS.
 
The format of exchanged data is JSON. This applies to both requests and responses.


Versioning
==========
There are a number of ways to implement versioning. The easiest is using a version specifier in the URI.
The most complex way is using content negation <links>. As the API’s will be primarily used in the WCT 
project itself it is advised to use the most simple way possible. So using version specifier (e.g. number) in the URI.
 
Authentication
==============
To use an REST API the user must be authenticated. The proposal is to authenticate once and return a token 
that can then be used in all REST API calls. 

Data format
===========
Although all kind of data formats can be supported it is advised to keep this simple and choose one, e.g. JSON (preferred) or XML.
