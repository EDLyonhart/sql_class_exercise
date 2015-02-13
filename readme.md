# In class exercise - Apartment lab

- Create a database called apartmentlab 
- Using this database, create two tables, one for owners and one for properties
- Keep this relationship in mind when designing your schema:
	+ **One owner can have many properties**

###Tables

- The owners table should consist of: 
	+ owner_id (this should be the primary key as well as a unique number that increments automatically)
	+ name
	+ age
- The properties table should consist of:
	+ property_id (this should be the primary key as well as a unique number that increments automatically)
	+ name
	+ number of units
	+ owner_id (this should have the constraint NOT NULL)
		+ There should be also be a foreign key that references the owners table

###Questions
Write down the following sql statements that are required to solve the following tasks.

```
1. Show all the tables                                                /dt
2. Show all the users                                                 /du
3. Show all the data in the owners table                              SELECT * FROM owners
4. Show the names of all owners                                       SELECT names FROM owners
5. Show the ages of all of the owners in ascending order.             SELECT ages FROM owners ASC
6. Show the name of an owner whose name is Mary.                      SELECT mary FROM owners
7. Show the age of all owners who are older than 30.                  SELECT * FROM owners WHERE age > 30
8. Show the name of all owners whose name starts with an E.           SELECT * FROM owners WHERE name LIKE 'E%'
9. Add an owner named John who is 33 years old to the owners table.   INSERT INTO owners (name, age) VALUES('John', 33)
10. Add an owner named Jane who is 43 years old to the owners table.  INSERT INTO owners (name, age) VALUES('Jane', 43)
11. Change Jane's age to 30.                                          UPDATE owners SET age=30 WHERE name='Jane'
12. Change Jane's name to Janet.                                      UPDATE owners SET name='Janet' WHERE name='Jane'
13. Add a property named Archstone that has 20 units.                 INSERT INTO properties (name, number_of_unit) VALUES ('Archstone', 20)
14. Delete the owner named Janet.                                     DELETE FROM owners WHERE name='Janet'
15. Show all of the properties in alphabetical order that are not named Archstone and do not have an id of 3 or 5. 
                                                                      ?? SELECT * FROM properties EXCEPT name='Archstone' __&&__ id=3 __&&__ id=5
16. Count the total number of rows in the properties table.           ?? ______
17. Show the highest age of all owners.                               SELECT age FROM owners ASC limit 1
18. Show the names of the first three owners in your owners table.    SELECT name FROM owners ASC limit 3
19. Create a foreign key that references the owner_id in the owners table and forces the constraint ON DELETE NO ACTION. 
                                                                      INSERT TABLE owners ADD CONSTRAINT owner_fk FOREIGN KEY REFERENCES owner_id ON DELETE NO ACTION
20. Show all of the information from the owners table and the properties table in one joined table.
                                                                      ?? SELECT owners *, porperties * JOIN __on owner id__
```
Bonus (this might require you to look up documentation online)

```
1. In the properties table change the name of the column "name" to "property_name". 
2. Count the total number of properties where the owner_id is between 1 and 3.
3. Delete the owners table - what happens? why?
```


















