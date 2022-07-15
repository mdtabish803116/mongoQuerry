DataBase ---- mongoQuerry
There are Four Collections In the mongoQuerry DataBase
1. users
2. cars
3. employee_salary
4. students_marks 

A. For users Collecton -----> 

   1. Find all the female users 
          -----> db.users.find(gender : "Female")


   2. Find all the female users who speak one of the two languages        Kannada,   Hindi   
        ----->  db.users.find({gender : "Female" , $or: [{language :"Kannada"}, {language : "Hindi"}]})


   3. Find all the male users who can speak Hindi and female users who can speak Kannada 
         -------> db.users.find( {$or: [{gender : "Male" ,language : "Hindi"} ,{gender : "Female" , language : "Kannad"}]} )


    4. Find all the users who wear the shirt size S
          ------> db.users.find({shirt_size : {$eq : "S"}})

    5. Find all the female users who wear the shirt size XL 
          ------> db.users.find({$and : [{gender : "Female"} , {shirt_size : "XL"}]})

    6. Find all the English speaking male users and Hindi speaking female users
      
      ------->  db.users.find({$or : [{language : "English" , gender : "Male"} , {language : "Hindi" , gender : "Female"}]})

    7 . Find all the male users who can speak Hindi or English and female users who can speak Kannada or German
        ------> db.users.find({$or : [{gender : "Male" , $or : [{language : "English"} , {language : "hindi"}]} , {gender : "Female" , $or : [{language : "Kannada"} , {language : "German"}]}]})

    8. Find all the female users who can speak Bengali who wear shirt size XL and male users who speak German and wear shirt size either L or M

         ------> db.users.find({$or : [{gender : "Female" , language : "Bengali" , shirt_size : "XL"} , {gender : "Male" , language : "German" , $or :[{shirt_size : "L"} , {shirt_size : "M"}]}]})

    9. Find all the female users who speak any of the Indian languages (Hindi, Punjabi, Bengali, Gujarati, Tamil, Malayalam)
        
         ------>  db.users.find({gender : "Female" , $or :[{language : "Hindi"} , {language : "Punjabi"} , {language : "Bengali"} , {language : "Gujarati"} , {language : "Tamil"} , {language : "Malayalam"}]})

  10. Men who can speak Korean
     
       ------>  db.users.find({gender : "Male" , language : "Korean"}