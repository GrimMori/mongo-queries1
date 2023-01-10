## Independent Practice

Solutions:

- Find the restaurant with id `30112340`.

db.restaurants.find( { "restaurant_id": "30112340" } )



- Find `May May Kitchen`.

db.restaurants.find( { "name": "May May Kitchen" } )



- Find the restaurants where their cuisine is `Tapas`.

db.restaurants.find( { "cuisine": "Tapas" } )



- Find the restaurants in postal code `11208`.

db.restaurants.find( { "zipcode": "11208" } )



- Find all restaurants that have a score greater or equal than `70`.

db.restaurants.find( { "grades.score": { $gte: 70 } } )



- Find all restaurants in `Brooklyn`that have a score greater than `80`

db.restaurants.find({ "borough": "Brooklyn", "grades.score": { $gte: 70 } }, {"_id":0,"name":1})



- All restaurants with `Chilean` or `Czech` cuisine.

db.restaurants.find({ $or: [ {"cuisine": "Chilean"}, {"cuisine": "Czech"} ] }, {"_id":0,"name":1})



- All restaurants with grade `A` in **second** position of the array.

db.restaurants.find( { "grades.1.grade": "A" } )



- All restaurants with grades `A` or `B`.

db.restaurants.find({ $or: [ {"grades.grade": "A"}, {"grades.grade": "B"} ] }, {"_id":0,"name":1})



- All restaurants that have a review made in `2014-09-16`.

db.restaurants.find( { "grades.date": ISODate("2014-09-16T00:00:00.000Z") })



- All restaurant their cuisine is `Tapas` ordered by `name` in ascending (normal) order.

db.restaurants.find({"cuisine":"Tapas"}).sort({"name":1})



- How many restaurants have been graded after `2015-01-01`.

db.restaurants.find( { "grades.date": { "$gt" : ISODate("2015-01-01") } }).count

