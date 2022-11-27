<h2>AirBnB clone - The console</h2>

![Airbnb1](https://user-images.githubusercontent.com/65285730/204097713-cdbd6221-3905-4b58-8055-3c006ac8185f.png)

<h1>Project Description</h1>
<p>This is the first part of the AirBnB clone project where we worked on the backend of the project whiles interfacing it with a console application with the help of the cmd module in python.

Data (python objects) generated are stored in a json file and can be accessed with the help of the json module in python.</p>

<h1>Description of the command interpreter:</h1>
<p>The interface of the application is just like the Bash shell except that this has a limited number of accepted commands that were solely defined for the purposes of the usage of the AirBnB website.

This command line interpreter serves as the frontend of the web app where users can interact with the backend which was developed with python OOP programming.</p>

Some of the commands available are:
<ul>
<li>show</li>
<li>create</li>
<li>update</li>
<li>destroy</li>
<li>count</li>
</ul>
<p>And as part of the implementation of the command line interpreter coupled with the backend and file storage system, the folowing actions can be performed:
<ul>
<li>Creating new objects (ex: a new User or a new Place)</li>
<li>Retrieving an object from a file, a database etc</li>
<li>Doing operations on objects (count, compute stats, etc…)</li>
<li>Updating attributes of an object</li>
<li>Destroying an object</li>
<ul>

<h1>Installing</h1>
<p>You will need to clone the repository of the project from Github. This will contain the simple shell program and all of its dependencies.</p>

<pre>git clone https://github.com/jzamora5/AirBnB_clone.git</pre>
<p>After cloning the repository you will have a folder called AirBnB_clone. In here there will be several files that allow the program to work.</p>
<pre>
/console.py : The main executable of the project, the command interpreter.

models/engine/file_storage.py: Class that serializes instances to a JSON file and deserializes JSON file to instances

models/__ init __.py: A unique FileStorage instance for the application

models/base_model.py: Class that defines all common attributes/methods for other classes.

models/user.py: User class that inherits from BaseModel

models/state.py: State class that inherits from BaseModel

models/city.py: City class that inherits from BaseModel

models/amenity.py: Amenity class that inherits from BaseModel

models/place.py: Place class that inherits from BaseModel

models/review.py: Review class that inherits from BaseModel
</pre>

<h1>How to use it</h1>
<p>It can work in two different modes:

Interactive and Non-interactive.</p>

<p>In Interactive mode, the console will display a prompt (hbnb) indicating that the user can write and execute a command. After the command is run, the prompt will appear again a wait for a new command. This can go indefinitely as long as the user does not exit the program.</p>

<pre>
<code>
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
</pre>
</code>

<p>In <b>Non-interactive mode</b>, the shell will need to be run with a command input piped into its execution so that the command is run as soon as the Shell starts. In this mode no prompt will appear, and no further input will be expected from the user.</p>

<pre>
<code>
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
</pre>
</code>

<h1>Format of Command Input</h1>
<p>In order to give commands to the console, these will need to be piped through an echo in case of Non-interactive mode.

In Interactive Mode the commands will need to be written with a keyboard when the prompt appears and will be recognized when an enter key is pressed (new line). As soon as this happens, the console will attempt to execute the command through several means or will show an error message if the command didn't run successfully. In this mode, the console can be exited using the CTRL + D combination, CTRL + C, or the command quit or EOF.</p>

<h1>Arguments</h1>
<p>Most commands have several options or arguments that can be used when executing the program. In order for the Shell to recognize those parameters, the user must separate everything with spaces.</p>

Example:

<pre>
<code>
user@ubuntu:~/AirBnB$ ./console.py
(hbnb) create BaseModel
49faff9a-6318-451f-87b6-910505c55907
user@ubuntu:~/AirBnB$ ./console.py
</pre>
</code>

or

<pre>
<code>
user@ubuntu:~/AirBnB$ ./console.py $ echo "create BaseModel" | ./console.py
(hbnb)
e37ebcd3-f8e1-4c1f-8095-7a019070b1fa
(hbnb)
user@ubuntu:~/AirBnB$ ./console.py
</pre>
</code>

<h1>Available commands and what they do</h1>
<p>The recognizable commands by the interpreter are the following:</p>

<table>
<thead>
<tr><th>Command</th><th>Description</th></tr>
</thead>
<tr><td>quit or EOF</td>
<td>Exits the program</td></tr>
<tr><td>Usage</td>
<td>By itself</td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>help</td>
<td>Provides a text describing how to use a command.</td></tr>
<tr><td>Usage</td>	
<td>By itself --or-- help <command></td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>create</td>	
<td>Creates a new instance of a valid Class, saves it (to the JSON file) and prints the id. Valid classes are: BaseModel, User, State, City, Amenity, Place, Review.</td></tr>
<tr><td>Usage</td>	
<td>create <class name></td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>show</td>
<td>Prints the string representation of an instance based on the class name and id</td></tr>
<tr><td>Usage</td>
<td>show <class name> <id> --or-- <class name>.show(<id>)</td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>destroy</td>
<td>Deletes an instance based on the class name and id (saves the change into a JSON file).</td></tr>
<tr><td>Usage</td>
<td>destroy <class name> <id> --or-- .destroy()</td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>all</td>
<td>Prints all string representation of all instances based or not on the class name.</td></tr>
<tr><td>Usage</td>
<td>By itself or all <class name> --or-- <class name>.all()</td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>update</td>
<td>Updates an instance based on the class name and id by adding or updating attribute (saves the changes into a JSON file).</td></tr>
<tr><td>Usage</td>
<td>update <class name> <id> <attribute name> "<attribute value>" ---or--- <class name>.update(<id>, <attribute name>, <attribute value>) --or-- <class name>.update(<id>, <dictionary representation>)</td></tr>
<tr><td>-----</td>	<td>-----</td></tr>
<tr><td>count</td>
<td>Retrieve the number of instances of a class.</td></tr>
<tr><td>Usage</td>
<td><class name> count()</td></tr>
</table>

<h1>Authors:</h1>
Solomon Okpako - avispro.web@gmail.com
