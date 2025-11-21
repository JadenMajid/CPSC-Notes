- Understanding
	- What does it mean for a system to be secure?
	- 4 Security requirements
		1. Confidentiality
			- Preventing unauthorized parties from accessing information
		2. Integrity
			1. Only authorized parties can manipulate information
			2. Data should be correct
		3. Availability
			1. Resources are available if they are accessible by authorized parties
		4. Accountability
			1. It should be possible to know how subjects interacted with sensitive systems
	- How does this apply to [[REST]]?
		- GETs may be open to the public unless we have some sort of authentication method(confidentiality)
		- POST/PUT/DELETE apply to integrity, can unauthorized parties change sensitive information
		- all verbs apply to accountability(are we keeping track of who accesses our api? do we even know who is accessing our api?)
- Analysis
	- How could our system be compromised?
	- STRIDE
		- Spoofing
			- Pretend to be someone else
		- Tampering
		- Repudiation
			- Deny performing a task
		- Information Disclosure
		- Denial of service
		- Elevation of privilege
			- Gain access and controls you should have
	- 
#310
#310
#310