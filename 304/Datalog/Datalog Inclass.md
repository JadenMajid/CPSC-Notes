Here are some relations that exist in a database for a symphony.  
[[Datalog]]
Person(email, name, age)  
	• This relation stores anyone who has signed up for our mailing list. Tuples in this relation  
	may not be listed in Purchase.  
Show(id, year, month, date, showing, attendanceNumber)  
	• Showing describes whether a show was during morning, afternoon, or evening  
Song(composer, title)  
SongsPerformed(showID, composer, title)  
	• showID is a foreign key referring to Show  
	• composer and title are foreign keys referring to attributes of the same name in Song  
Purchase(email, showID, price)  
	• email is a foreign key referring to the email attribute in Person  
	• showID is a foreign key referring to Show  
Musician(id, name, instrument, position, nationality)  
PerformedIn(id, showID)  
	• id refers to the attribute of the same name in Musician  
	• showID is a foreign key referring to Show  


Write Datalog statements to answer the following questions:  
1. Find the year, month, date, and attendance numbers of all shows that had a Canadian  
musician perform in it.  

Ans1(y,m,d,n):-Show(id,y,m,d,_,n), PerformedIn(Pid, id), Musician(Pid, _, _, _ "canadian")

2. Find the showIDs of shows where the symphony performed songs by Mozart and  
Beethoven.  

Ans2(Sid):- Show(Sid, _, _, _, _), SongsPerformed(Sid, "Mozart", _), SongsPerformed(Sid, "Beethoven", _)

3. Find the showIDs of shows where the symphony performed at least one song by Mozart  
or Beethoven.  

Ans3(Sid):- Show(Sid, _, _, _, _), SongsPerformed(Sid, "Mozart", _)
Ans3(Sid):- Show(Sid, _, _, _, _), SongsPerformed(Sid, "Beethoven", _)

4. Find the songs that have been performed by every violinist in the orchestra. You can  
safely assume that if a musician is performing in a show, they will play every song in that  
show.

Ans4(s):- Musician(i, _, "violin", _, _), PerformedIn(i, ) ?????

I really don't think we covered this in class...
#304
#304
#304
#304