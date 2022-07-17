C. for student Collections 

1. Count of all the female students
     ----> db.students_marks.find({gender : "Female"}).count()

2. Count of all male students who scored more that 85 in maths, science and english
    -----> db.students_marks.find({gender : "Male" , $and : [{maths : {$gt : 85}} , {science : {$gt : 85}} , {english : {$gt : 85}}]}).count()

3. Count of all students who scored between 50 and 75 marks in maths and english
      ------> db.students_marks.find({maths : {$gt : 50 , $lt : 75} , english : {$gt : 50 , $lt : 75}}).count();

4. Count of students from class I to class V who score more that 50 in all subjects
     -----> db.students_marks.find({ $or : [{class : "II"} , {class : "III"} , {class : "IV"}], maths : {$gt : 50} , english : {$gt : 50} , science : {$gt : 50}}).count()

5. Find all the female students from grade X section A who scored less that 25 in all subjects
   --------> db.students_marks.find({gender : "Female" , class : "X" , section : "A" , maths : {$lt : 25} , english : {$lt : 25} , science : {$lt : 25}}).count();

6. Top 3 students in grade V based on maths score
   -----> db.students_marks.find({class : "V"}).sort({maths : -1}).limit(3)

7. Bottom 5 students in grade I based on science score
    -----> db.students_marks.find({class : "I"}).sort({science : 1}).limit(5)

8. Students from section A who scored less than 50 in all the subjects
     -----> db.students_marks.find({section : "A" , maths : {$lt : 50} , science : {$lt : 50} , english : {$lt : 50}})

9. Students from section C who scored more that 75 in all the subjects
   ------> db.students_marks.find({section : "C" , maths : {$gt : 75} , science : {$gt : 75} , english : {$gt : 75}})

10. Students who will fall in page 3 if ordered by increasing order of maths scores (Assume 10 results per page)
   ------>  db.students_marks.find().sort({maths : 1}).skip(200).limit(10)

11. Students who will fall in page 5 if ordered by descreasing order of science scores (Assume 20 results per page)
   ------> db.students_marks.find().sort({science :-1}).skip(200).limit(20)

12. Female Students who will fall in page 4 if ordered by increasing order of science scores and maths scores (Assume 5 results per page)
       ------> db.students_marks.find({gender : "Female"}).sort({maths : 1 , science : 1}).skip(384).limit(5)

13. Male Students who will fall in page 3 if ordered by decreasing order of science, maths and english scores (Assume 15 results per page)
  ----> db.students_marks.find({gender : "Male"}).sort({maths : -1 , science : -1 ,english : -1}).skip(68).limit(15)    