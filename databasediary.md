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