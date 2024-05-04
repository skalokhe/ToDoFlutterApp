# flutter_parse_todo
A ToDo App to better understand Parse on Flutter

	                                                                                    Name: Sonal Naresh Kalokhe
                                                                          Bits ID: –2022MT93603
 	                                                                                                             Email: 2022mt93603@wilp.bits-pilani.ac.in
                                                                 Git Repository Link 
                                                                    Recorded Demo Link

Cross Platform Application Development (Merged - SEZG585/SSZG585) Assignment: 1

Synopsis:  
 
We have implemented the CRUD operations for a ToDo App to better understand Parse on Flutter. The application has a simple interface, with a text field to register a task and a list of registered tasks. We can update each task as completed or even delete the task.
We have built a Todo App that stores the tasks in the Back4App Database.
We have performed below high-level tasks to complete the assignment.
	Create a Back4App account and create a Backend-as-a-Service to manage tasks.
	Create a Flutter app that connects to Back4App.
	Implement the necessary functionality to create, read, update, and delete the tasks.
	
Prerequisites:

1.	Flutter version 2.2.x or later
2.	Android Studio or VS Code installed (with Plugins Dart and Flutter)
3.	An app created on Back4App.
Note: Follow the New Parse App Tutorial to learn how to create a Parse App on Back4App.
4.	A Flutter app connected to Back4app.
Note: Follow the Install Parse SDK on Flutter project to create a Flutter Project connected to Back4App.
5.	A device (or virtual device) running Android or iOS.

 

Step1: Create and Setup Back4App:

Create your Back4app account. 
           

 

Step 2: Create a new App. 

        


At this moment our application backend structure is under construction and then will be loaded
 

Steps 3: Navigating on the Back4App Dashboard 

After creating the TODO App, you will see the Dashboard. Here we can find the Database browser, cloud functions, Push Notifications, and the other features available at Back4App. Create a todo class with task (string data type) and done (boolean data type) columns/member variables.

 



		
Steps 4: App Keys 

Go to the App Settings to check the App Keys which will be necessary to connect to our TODO App’s frontend to Back4App.

 

Steps 5: Creating TODO flutter project

Now as part of our pre-requisite we have all things in place now need to follow following steps:
Step 1 - Creating a TODO Flutter project
flutter create flutter_parse_todo

Step 2 - Installing Flutter plugin for Parse Server
Add the Parse to the project dependencies. Go to pubspec.yaml and add the following
dependencies:
  parse_server_sdk_flutter: ^7.0.0
Run the flutter pub get command to install the dependencies in the project.

 

Step 3 - Create Todo App
Refer our main. Dart file here, this file contains all the code required to create, read, update and delete the tasks from our TODO list.

 
 


Step 4 - Connect Todo App to Back4app Project
Find an Application Id and Client Key credentials by navigating to our app Dashboard at Back4App Website.
Update code in main.dart with the values of our project’s ApplicationId and ClientKey in Back4app

 
Step 5 - Creating TODO flutter project.

Run the project, and the app will load as shown in the image.
	Todo front-end app will make a call to Back4App and get the list of tasks.
	If a task is marked as done, it will be shown with a green tick mark.
	If the task is pending, it will be shown as a todo mark.
	User can mark a task as done by clicking the checkbox true.
	The user can remove the task from the list by deleting it.
	User can add a new task by adding text in the “New Todo” text box and clicking the “Add” button.

 

Step 6: code for create Object: 
Code for Create Object
	The create function will create a new Task with the title and done status equal to false.
	Make a new instance of the Parse Todo class with the command ParseObject('Todo’).
	Use the set function to set the parameters for this object.
	Call the save function, which will effectively register the task to your database in the Parse Dashboard.

 

Steps 7: Code for Read Object 
	The read function is responsible for querying the database and returning the list of objects
	Create an instance of Parse’s Query class.
	Do a Query search method using the query() method.
	If the operations succeed, a list of Todo objects will be returned. If no object is found, the success property is false, and the results are null.
 

Steps 7: Code for Update Object

	The update function is responsible for updating a task as completed or not.
	Make a new instance of the Parse Todo class with the command ParseObject('Todo’).
	Use the objectId property to set objectId of ParseObject that must be updated.
	Use the set function to modify the parameters done your Task.
	Call the save function, which will push the changes on the task to your database in the Parse Dashboard.

 

Steps 7: Code for Delete Object

	The delete function is responsible for removing a task from the database. It is an irreversible action, which means that you should be careful while using it.
	Make a new instance of the Parse Todo class with the command ParseObject('Todo’).
	Use the objectId property to set the objectId of ParseObject that must be removed.
	Call the delete function, which will remove the task from the database in the Parse Dashboard.
 

Steps 8: Code for creating listview.builder function :
//Get Parse Object Values
	final varTodo = snapshot.data![index];
	final varTitle = varTodo.get<String>('title')!;
	final varDone =  varTodo.get<bool>('done')!;

Step 9 : Demo : refer the link for the demo

Step 10: Additional Features 

1.	Implemented the ability to Edit/Update tasks. This could be on the task detail screen. You would need to update the ParseObject with the new information and save it.
2.	Add functionality to Delete tasks. This involves removing the ParseObject from the database.


Screenshots for all the features 

Edit Task:

To implement the ability to edit/update tasks in your Flutter app with Back4App, particularly changing a task's status from complete to incomplete (True to False).
In ToDo class in Back4App has a boolean field to represent the status of a task. It’s called done (Boolean) Value. This field should be a boolean where true represents a completed task and false an incomplete one.

 


Currently done (Boolean) status is False.
 
On the task detail screen, want to display a checkbox or a toggle switch that shows the current status of the task. The user can change this status by interacting with the checkbox or switch.
When the user updates the status of the task (like unchecking a completed task), you need to capture this event and update the task's is Completed field in Flutter app with Status “True” or “False”.
 
To save this updated status back to Back4App, you would use the Parse SDK. (As mentioned above).
After successfully updating the task in Back4App, make sure to update your local state as well so that the UI reflects this change. If you're using a state management solution (like Provider, Bloc, etc.), you would update the state accordingly. (Please refer below screenshot).

Currently done (Boolean) status is True. 

Delete Task:

And this could be a button or an icon that, when tapped, triggers the deletion process. To delete a task, use the task's object ID to remove it from the database.

 
 
 


Git Repo Link: https://github.com/skalokhe/ToDoFlutterApp.git


Recoded Demo Link: https://github.com/skalokhe/ToDoFlutterApp/blob/master/Sonal2022mt93603_Flutterback4appDemo.mp4


