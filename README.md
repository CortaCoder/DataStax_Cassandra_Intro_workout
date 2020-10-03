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
![](https://github.com/CortaCoder/DataStax_Cassandra_Intro_workout/blob/master/Create.JPG)

### Lets Insert some Data<br />
I have some data of my classmates which i will be inserting,
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
We have to check whether the data has been inserted or not. Head to the next section.

### Read the Table<br />
```
SELECT * FROM student_marks;
```
![The Insertion was successful !!!](https://github.com/CortaCoder/DataStax_Cassandra_Intro_workout/blob/master/Read%20Entire%20Data.JPG)

### Reading the marks of a particular student
Here i want to read the marks of "Sharan" from the table.
So i use the unique partition key named `studentid` to extract the desired row.
```
SELECT * FROM student_marks WHERE studentid = 112
```
![Displaying the record with studentid = 112](https://github.com/CortaCoder/DataStax_Cassandra_Intro_workout/blob/master/Read%20a%20record.JPG)

### Delete a particular Record from Table
* Before deleting ,i want to insert a data row
   ```
   INSERT INTO student_marks (studentid,student_name,math_marks,science_marks)
      ... VALUES (110,'Sampath',86.3,75.6);
   ```
* Once I read the entire table, i find two rows with the same `studentid` So to delete one of them, i have to make use of the clustering column i.e. `student_name` which is a part of `PRIMARY KEY`
   ![](https://your-copied-image-address)
* Deleting the duplicate row
   ```
   DELETE FROM student_marks
      ... WHERE studentid = 110 AND student_name = "Sampath";
   ```
   ![You can see that the record was deleted](https://your-copied-image-address)
   
### Update a particular record
I wish to update the `science_marks` of `studentid = 110`.
```
UPDATE student_marks SET science_marks = 85.8 WHERE studentid = 110 AND student_name = 'Sam' 
```
   ![The Record Got Updated Yay!!](https://your-copied-image-address)

# Once again Thanks DataStax !!! loved your Session :)
