

B. for cars collections

1.  Men who own a Pink car
      -----> db.cars.find({gender : "Male" , car_color : "Pink"}).count()

2. Women who own a Red or a Blue Car
      ------> db.cars.find({gender : "Female" , $or : [{car_color :"Red" } , {car_color : "Blue"}]})

3. Men who purchased the car in the year 1998
       ------> db.cars.find({gender : "Male" , purchase_year : "1998"})

4. Women who purchased a Yellow car in the year 1985
     -----> db.cars.find({gender : "Female" , car_color: "Yellow" , purchase_year : "1985"})

5. Men who either have a Red or Green car and either live in Germany or Kenya
    -----> db.cars.find({gender : "Male" , $or : [{car_color : "Red"} , {car_color : "Green"}] , $or : [{country : "Germany"} , {country : "Kenya"}]})

6. People from India who purchased cars in the year 2001
     -----> db.cars.find({country : "India" , purchase_year : "2001"})

7. People from Germany or Egypt who purchased cars in the year 1998 or 1992
      -----> db.cars.find({$or : [{country : "Germany"} , {country : "Egypt"}] , $or : [{purchase_year : "1998"} , {purchase_year : "1992"}]})

8. Women from India who own a Blue car
    -----> db.cars.find({gender : "Female" ,country : "India" , car_color : "Blue"})

9. Men from Germany who purchased cars in 1998 and Men from Egypt who purchased cars in 1992
     ------> db.cars.find({$or : [{gender : "Male" , country : "Germany" ,purchase_year : "1998"} , {gender : "Men" , country : "Egypt" , purchase_year : "1992"}]})

10. Women who own a Green car and are not from Pakistan
    ----> db.cars.find({gender : "Female" , car_color : "Green" , country : {$nin : ["Pakistan"]}})