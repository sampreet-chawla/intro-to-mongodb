# Starting with Mongo - Lab Answers

### A. Create a Classroom Database 
```
use classroom_seir_831
```

### Bulk Insert of Documents into students collection
```
db.students.insert([
	{
		"name": "Jake Nguyen",
		"favFoods": "Mac N Cheese",
		"age": 26,
		"os": "Mac",
		"hobbies": ["Video Games", "Watch Movies"]
	},
	{
		"name": "Gore Auluck",
		"favFoods": "Tacos",
		"age": 31,
		"os": "Win",
		"hobbies": ["Video Games", "Drinking wine"]
	},
	{
		"name": "Allisyn Abrams",
		"favFoods": "Tacos",
		"age": 30,
		"os": "Mac",
		"hobbies": ["Yoga", "Light music concerts"]
	},
	{
		"name": "Sampreet Chawla",
		"favFoods": "Pizza",
		"age": 30,
		"os": "Win",
		"hobbies": ["Music", "Dance", "Watch Movies"]
	}
])
```
### B. Find to get - 

1. A list of everyone in the  class.
```
db.students.find({})
```
2. An entry for a single person.
```
db.students.findOne()
```
### C. Create a collection name instructors

1. Create a single document that can hold the following instructors Joe, Alex, Kenneth, Nathaniel and Aegean; field name should be instructor_list

```
db.instructors.insertOne({"instructor_list": ["Joe", "Alex", "Kenneth", "Nathaniel", "Aegean"]})
```

2. Remove Nathaniel from the instructors list
```
db.instructors.update({}, {$set: {"instructor_list": ["Joe", "Alex", "Kenneth", "Aegean"]}})
```

### BONUS

##### Check out the MongoDB documentation and figure out how to find users by an entry in an array. 
```
db.students.find({"hobbies": {$in: ["Video Games"]}})
```
OR 
```
 db.students.find({hobbies: "Video Games"})
```
##### Searching an Array with Multiple values
```
db.students.find({"hobbies": {$in: ["Video Games", "Watch Movies"]}})
```

