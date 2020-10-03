# DataStax_Cassandra_Intro_workout
Used Cassandra for the first time, and here is what i made out of it - Student Marks DB<br />
I have always had the difficulty of searching my marks through the list provided by my Institute<br />
So i got an idea of using the DataBase provided by Cassandra after attending my first ever DBMS session with DataStax<br />

Thanks A Lot for Giving the Opportunity DataStax!!! :)<br />

Here's What I made
-------------------------------------------------------------
### Creating a Table named "student_marks"<br />
```
CREATE TABLE IF NOT EXISTS student_marks(
   ... studentid int,
   ... student_name text,
   ... math_marks decimal,
   ... science_marks decimal,
   ... PRIMARY KEY ((studentid),student_name));
```
* ![](https://your-copied-image-address)
### Lets Insert some Data<br />
```
INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
   ... VALUES (110,'Sam',86.3,75.6);
INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
   ... VALUES (112,'Sharan',88.5,87.6);
INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
   ... VALUES (113,'Shravan',92.8,98.6);
INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
   ... VALUES (114,'SriChakraRaj',93,98.9);
INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
   ... VALUES (117,'Sumanth',98.9,97.6);
```
