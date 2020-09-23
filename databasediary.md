23.09

Today we made presentations about Database management systems. I presented the Network DBMS. I did not retain any usefull information from the other presentations.
Afterwords we took the rest of the day to write the Database-Test. Luckily for me, it was the same test i took at the beginning of the year and my answers were still there. But for the purpose of this excercise i deleted the answers and wrote again what i knew. The Cod-Rules i left in place cause them i did not know any more.


16.09.
Today, as 3 members of our group were missing, instead of going ahead in the curriculum, we had the task to create a small presentation about DataBaseManagingSystems. And, in between, we reflected the cinema- and the airways-erm with Stefan and he gave us pointers. 
But here is what i have for presentation so far:

Network DataBaseManagementSystem
The Network DatabaseManagementsystem was introduced by IBM in late 1960s & early 70s, to solve some of the problems the Hirachical DatabaseManagementsystem had, especially the lack of flexibility. It was adapted and improved by the CODASYL Data Base Task Group and is therefore sometimes called the CODASYL model. CODASYL stands for Conference/Committee on Data Systems Languages.
To understand the system (or more accurate it's improvements), we first have to take a look at the Hirachical system:
The hirachical system is basically the same way, businesses organiced their data for ages, but on computer. Before that, people phisically wrote down stuff on paper and stored them in a convenient place (like a shoebox). To get to the data, you litterally had to moove your ass and go to the shoebox and look inside, to check if the data you were looking for was in there. If it wasn't in there you probably had to go to another shoebox.
The hirachical system basically did the same, but on Computers. If you searched for a file, the system had to check folder by folder. This is calle a Top-down-system. It was inefficent and also had other problems. For example people tendet do be blocked by the search queries from other people. So some of them copied some files, so they had easier access. But that led to bloated data and anomalies (which file was the accurate one?).
The Network DataBaseManagementSystem was invented to fix some of these problems. The basic difference was, that records could have more than one owner:
 
children "members" and the parents "owners"

Advantages of NetworkDBMS: 
- Still relatively easy to understand
	- Similar conceptually to hirachical DBMS
- Able to adapt to business processes
	- Able to capture more complex relationships
- You can manage m to n relationships
- More flexibel than hirachical DBMS, although it still lacks fexibility

Disadvantages:
- Did not eliminate hirachical DB- problems
	- Slow to adapt or modify
	- heavily relied on experts
	- Bloated data and/or anomalies
	- Expensive

Some of the popular network databases are,

 -   Integrated Data Store (IDS)
-    IDMS (Integrated Database Management System)
	- CA IDMS (IUA EIUA) Global User Community
	- AID - Anwendervereinigung IDMS Deutschland
	- Australian IDMS User Group
	 etc
-    Raima Database Manager
	- Mitsubishi Electric—iQ Platform C Controller PLC
	- Boeing—"AWACS"– Airborne Warning and Control System's radar electronics system
	- Siemens—RapidPoint 400 medical fluid test equipment
	- IBM—ClearCase source code control system
-    TurboIMAGE
-    Univac DMS-1100

The Network DataBaseManagementSystem was eventually replaced by the relational model.




09.09.
Today Stefan showed us on the excercise "hotel" how he identifies Entities and how he sets relationships. (He thought he gave us this as homework, but we all can't remember him saying so. Acording to him, this has never happened to him (Speaking of Stefan: I realy doubt, that he reeds our diaries. At least not right away. Stefan: if you are reading this before 16.09.2020, come to me and tell me "I read it", and then i will by you a sixpac of Freistädter Bier)). 
After that we made ERDs and RMs of the excercises "E-learning" and "Cinema". 
I learned, that when you have a 1-n relationship, the entity which has the n gets a foreign key of the entity which has the 1.
Also if an entity has a foreign key, it absolutely has to have a relation to the entity of which the foreign key is located. 
Another little detail is, that we do not care about "smallint". We use int for everything.


03.09.
Today we talked about normalization. 
The first problem to tackle is redundancy. You want every value saved just once. Otherwise, if you change one value, the same key can point to different values and it is impossible to know, wich is the true value. 
There are three anomalies, you neet to keep an eye on:
- Update-Anomaly: Basically watch out, that if you update something, it needs to be updated everywere. Every entry that takes reference to the updated feel needs to be effected. But not more. 
  In short: The nessesary things need to be changed. Not more, not less.
- Insert-Anomaly: If you create a new entry, you need to fill every key-feeld. If a new employee will be inserted, but she has no employee# yet, you cannot create her. 
  In short: The nessesary things need to be created. Not more, not less.
- Delete-Anomaly: If you delete the last of something (e.g. the last student who takes the class), make sure that this action does not delete things that references to that (e.g. the Class gets deleted).
  In short: The nessesary things need to be deleted. Not more, not less.

1. Normal form:
Every field can only have one value. If you have, for example, several children, each child gets it own row (=tupel).
Problem of the 1.NF: You can insert logically wrong rows(tupel). E.g. In one row the employee works on project 2 with the projectname "Finances", and in the next row, he works in project 2 with the projectname "Planing" -> The same project must not have tow differnt names. Therefor:
2. Normal form:
If the same value is in several rows AND is directly depended on the primary key (or keys), you can take them out and put them in an extra tabel. After that, the value in the original tabel exists once at most, and the different values, that created that many rows (throu the 1. NF) in the first place, will be referenced in an extra tabel. 
Problem of the 2.NF: There are still values double, wich reference to each other, but are not directly linked to the primary key. If you change one of them, the other stays the same and that leeds to inconsistencies. Therefor:
3. Normal form:
Dependencies of non-key Atributes are not allowed and need to be outsourced to an extra tabel  (e.g. Department#, Department_name)

We skipped the rest of the Normal forms for now.



Recap of yesterday:

There are a few Rules, that help you draw a "correct" ERD:
- If lines cross, draw a bridge. That makes it easier to differentiate from a line, that connects more than 2 things (entities, atributes, etc)
- Entities are to be writtn in singular. (You can write them with a Capital letter, to make them visually prominent, but in the software, everything will be lower case). They are nouns. Avoid abreviations. Be consistant (for example same language, colloquial or scientiffic names, etc), and 

We also went throu the "9 Codd'schen Anforderungen"

- Integration: create uniformly and not redundant
- Operation: save, search, change, insert
- Catalog: access to data-description (Data Dictionary)
- Userfew: different fewing options for different users
- integrity-insurance: make sure your data stays uniformly and not redundant
- Access-control: Denial of unauthorized access
- Transaction: several DB-operations as funtional unit
- Synchornisation: coordinate the parallel transactions of several users
- Data backup: restore lost data after system crash


02.09.

Regeln:
- Bei Kreuzenden Linien: Brücken machen
- Entitäten sind in Einzahl anzugeben

Fachbegriffe:
-Integrität: 



Für Praktikum: An 11. bis 22 Jänner
Karriere.at
devjobs.at



26.08.2020

Today i was only able to start my first database-day at 13:00, because i had to go to a doctor in Freistadt before. 

In the afternoon i started (and finished) the "CodersBay-ERM". We were also instructed to make the "School-ERM" and the "Library-ERM". And what we can't finish today will be homework until next wednesday. I didn't have enough time to even start one of the two, so they will both be my homework. Fortunatly for me, I already made both back in Jannuary. I do plan on remaking them both because it will be good practise, but hey. It is good to have a backup plan. And lets be honest, do you really think Stefan would notice if i would hand in my previous work? Well lets see... 

Today I (re)learned, that you write entities with a capital first letter. Also that not only entities but also relationships can have atributes. And if you want to make a list as an atrubute, you instead make a new entity with the name of the list and where you wanted to put the list as an entitiy you write "(name of the list).id" instead.