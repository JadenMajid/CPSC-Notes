---
tags:
  - "CPSC310"
---
- built on HTTP
- A type of HTTP [[APIs]]
- Maps to [[CRUD]] One to One
- methods should be as decoupled as possible
- responses should be CONNECTED
	- When you call a method, it should link any related and affected resources
- all methods should be STATELESS
	- Method calls should contain everything needed to process request
- consists of URL/plural_noun with a VERB
- [[Versioning]]
	- APIs are assets and liabilities
	- after something is provided, it can't be removed(without a fuss)
	- API Version is encoded in the URL
		- GET /2017-01-01/customers/{id}/history
			- date of API version in req
		- GET /2/customers/{id}/history
			- version in request
		- GET /v2/customers/{id}/history
			- version in request
		- GET /customers/{id}/history/?v=2
			- version in param
		- APIVersion: 2
			- version in header
- Idempotency
	- Performing an identical action multiple times should produce the same result as performing it once
	- POST is NOT idempotent, always makes new resources
	- other VERBS ARE idempotent, they should have identical behaviour
		- if we delete something twice, then an initial response of 2XX, then followups of 4XX ARE idempotent  because the state of the server is identical
- Structure
	- NOUNS/{id0}/NOUNS/{id1}?parameter={id2}&parameter={id3}
- VERB
	- GET: Query
	- POST: Update
	- PUT: New Noun
	- DELETE: Remove Noun
- NOUN
	- anything

#310
#310
#310