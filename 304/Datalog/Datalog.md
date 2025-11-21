---
tags:
  - "CPSC304"
---
- Rules
	- Multiple rules of the same name correspond to a Union
	- Variable names in different rules can be the same or different
	- Anonymous variables: _
		- Every _  is a fresh new variable, like in python or Rust
- Examples
	- Product(__pid__, name, price, category, maker-cid)
	- Purchase(buyer-sin, seller-sin, store, pid)
	- Company(<u>cid</u> , name, stock price, country)
	- Person(<u>sin</u>, name, phone number,  city)
	- Find names of people that are either buyers or sellers
		- A(N):-Person(S,N,A,B), Purchase(S,C,D,E)
		- A(N):-Person(S,N,A,B), Purchase(C,S,D,E)
	- Find the sins of people who bought stuff from a person named joe or bought products from a company whose stock prices is more than $50
		- Ans(Sin):-Purchase(Sin,Ssin,\_,\_), Person(Ssin,"Joe",\__,\__)
		- Ans(Sin):-
	- Write a query in [[Relational Algebra]] to find SINs of people who have not made a purchase at the bay
		- VancouverAntiBay(buyer,seller,product,store):-
		  Person(buyer,name,phone,"Vancouver"),
		  Purchase(buyer,seller,store,product),
		  not Purchase(buyer,seller,"The Bay", product)
	- Sind the sins of people who are not named 'Joe'
		- Ans(s):-Person(s,n,p,c), NOT Person(s,'Joe',p,c)
		- We need npc to NOT be anonymous variables is that datalog can get stuck into an infinite loop
- [[Datalog Rule Safety]]
- [[Datalog Views]]
- 
#304
#304
#304
#304