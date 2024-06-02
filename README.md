HBNB - The Console
This repository includes the initial phase of a student project aimed at creating an AirBnB website clone. This phase features a backend interface, or console, for managing program data. Users can use console commands to create, update, and delete objects, as well as manage file storage. Data persistence across sessions is achieved through JSON serialization and deserialization.

General Use
First, clone this repository.

After cloning, locate the "console.py" file and run it with:


/AirBnB_clone$ ./console.py
Upon running this command, you should see the following prompt:

(hbnb)
This prompt indicates that you are in the "HBnB" console, which offers various commands.

Commands
create: Creates an instance based on a given class
destroy: Deletes an object based on class and UUID
show: Displays an object based on class and UUID
all: Displays all objects the program can access, or all objects of a specific class
update: Modifies attributes of an object based on class name and UUID
quit: Exits the program (EOF also works)
Alternative Syntax
Commands can also be issued using an alternative syntax:

Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
The advanced syntax applies to the following commands:

all: Displays all objects the program can access, or all objects of a specific class
count: Returns the number of instances by class
show: Displays an object based on class and UUID
destroy: Deletes an object based on class and UUID
update: Modifies attributes of an object based on class name and UUID
Examples
Primary Command Syntax
Example 0: Create an object

Usage: create <class_name>

(hbnb) create BaseModel
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)
Example 1: Show an object

Usage: show <class_name> <_id>

(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)
Example 2: Destroy an object

Usage: destroy <class_name> <_id>

(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)
Example 3: Update an object

Usage: update <class_name> <_id>

(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
(hbnb)
Alternative Syntax
Example 0: Show all User objects

Usage: <class_name>.all()

(hbnb) User.all()
["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
Example 1: Destroy a User

Usage: <class_name>.destroy(<_id>)

(hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
Example 2: Update User (by attribute)

Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)

(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Todd the Toad', 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
Example 3: Update User (by dictionary)

Usage: <class_name>.update(<_id>, )

(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]





