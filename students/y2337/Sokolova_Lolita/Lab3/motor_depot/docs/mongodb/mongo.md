## Mongodb: процесс реализации модели

```
db.drivers.insert([
{'name': 'Mike Vazovsky', 'exp': 2},
{'name': 'Kile Fire', 'exp': 1},
{ 'name':'Kira Yellow', 'exp':	5}, 
{'name': 'Mary Enn', 'exp':	4}, 
{'name': 'Ewan Mogilevsky', 'exp':	4}])



db.refuellers.insert([
{'name': 'Jhon Jhonovich', 'exp':	3}, 
{'name': 'Carl Mikovich', 'exp':	2},
{'name': 'Kris Walker', 'exp':	9}, 
{ 'name': 'Sally Mirgu', 'exp':	4},
{ 'name':'Karter Mayower', 'exp':	3},
{'name': 'Kira Yellow', 'exp':	1}
])

db.car.insert([
{"model": "volvo", "reg_num": "a666aaa", "garage": "Honey street 48", "motor_depot": 1},
{"model": "VAZ", "reg_num": "k972jui", "garage": "Sunday street 10", "motor_depot": 1},
{"model": "volvo", "reg_num": "o876pou", "garage": "Honey street 48", "motor_depot": 1},
{"model": "audi", "reg_num": "m725ytr", "garage": "Mansh street 89", "motor_depot": 2}, 
{"model": "audi", "reg_num": "b788ffd", "garage": "Contary street 4", "motor_depot": 3}
])


var car_id = db.car.findOne({"reg_num": "k972jui"})._id
var driver_id = db.drivers.findOne({"name": 'Mike Vazovsky'})._id
var refueller_id = db.refuellers.findOne({"name": 'Kris Walker'})._id
db.waybill.insert(
{
"trip_date": new Date("2020-09-09"), 
"point_of_loading": "Garbage st. 27", 
"point_of_unloading": "Clean square", 
"mileage_total": 70, 
"mileage_cargo": 25,
"consignor": "Mr. Hopkins", 
"consignee": "Mr. Ulala", 
"order_time": 8,
"fuel": {
	"liter": 20, 
	"kilogram": 21
},
"car": new DBRef("car", car_id), 
"driver": new DBRef("drivers", driver_id), 
"refueller": new DBRef("refuellers", refueller_id)
}
)

var car_id = db.car.findOne({"reg_num": "o876pou"})._id
var driver_id = db.drivers.findOne({"name": 'Mike Vazovsky'})._id
var refueller_id = db.refuellers.findOne({"name": 'Karter Mayower'})._id
db.waybill.insert(
{
"trip_date": new Date("2020-20-10"), 
"point_of_loading": "Suda street 27", 
"point_of_unloading": "Tuda street 95", 
"mileage_total": 150, 
"mileage_cargo": 70,
"consignor": "Mr. Howdy", 
"consignee": "Ms. Amafine", 
"order_time": 10,
"fuel": {
	"liter": 35, 
	"kilogram": 40
},
"car": new DBRef("car", car_id), 
"driver": new DBRef("drivers", driver_id), 
"refueller": new DBRef("refuellers", refueller_id)
}
)


var car_id = db.car.findOne({"reg_num": "b788ffd"})._id
var driver_id = db.drivers.findOne({"name": 'Kira Yellow'})._id
var refueller_id = db.refuellers.findOne({"name": ' 'Jhon Jhonovich'})._id
db.waybill.insert(
{
"trip_date": new Date("2020-20-10"), 
"point_of_loading": "Cold street 30", 
"point_of_unloading": "Hot street 15", 
"mileage_total": 250, 
"mileage_cargo": 170,
"consignor": "Air Company", 
"consignee": "Ms. Ratata", 
"order_time": 15,
"fuel": {
	"liter": 87, 
	"kilogram": 100
},
"car": new DBRef("car", car_id), 
"driver": new DBRef("drivers", driver_id), 
"refueller": new DBRef("refuellers", refueller_id)
}
)
```

