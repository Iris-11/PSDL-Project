<h1>Productive Jump!</h1>
<br>
Our project aims to combine the idea of productivity and task management with the concept of
gamification. We tried to create a reward based system which encourages users to finish their
tasks and as a break and motivation , play a fun runner game.<br>
The application starts with a main menu, which includes buttons to the task list, the game and
an option to exit it.<br>
The task list is built using the user-friendly interface tools provided by the tkinter library in
Python. Upon completion of a task the user gets coins. These coins can be used to play the fun
runner game. This game serves the purpose of motivating the users to complete their tasks and
also is a good break from work.<br>
The game is built using the pygame library. We have also used the importlib library to handle the
circular imports in the application. The sys library is also used to exit the application.
Apart from that, to store the high score and number of coins we have used the file handling
concept to read and write updated values into text files in the backend. We have used the
openpyxl library to store the tasklist in a .xlsx file in the backend.<br>

This was made as a group project for a Programming skills Development Lab(Python)

<h2>Componenets of the project - </h2>
<h3>Module 1 : The main menu-</h3>
Libraries used - Pygame, importlib

User defined modules imported- button class, coins class, demo(game), doing(task list)<br>
Methods created -<br>
● get_font() : used to set the font style and size<br>
● play(): to call the demo module and play the game<br>
● tasks() : to call the doing module and use the tasklist<br>

Description - Importlib is used to call other modules during runtime. It has been used to
call the main functions of demo and doing(which is the task list module). The pygame library is
used to create the interface involving the text displayed and the buttons.<br>

<h3>Module 2 : The to-do list-</h3>
Libraries used - Tkinter , messagebox from tkinter, importlib, openpyxl<br>

User defined modules imported - coins class<br>
Methods created -<br>
● doing_main()-creates a window and all its components and contains the main loop<br>
● new_task() - add a task<br>
● deleteTask() - used to remove a task from the list after its completion. Will also display
total coins earned upon completion of a task.<br>
● goBack() - go back to the main menu<br>
Description - This module is used to create an interface between the user and their to-do
list. The to-do list is stored in an Excel file in the back-end, and using this interface, the user can
add and remove tasks. When the user wishes to close the tasklist, they can click on the “Return
to menu” button, which will destroy the tasklist window.<br>

<h3>Module 3 : The game-</h3>
Libraries used - Pygame, importlib<br>

Methods created - game_main() - contains entire game , load_high_score(), save_high_score(),
display_score(), obstacle_movement(), player_animation(), collisions()<br>

Description - The game is primarily built by making surfaces and rectangles of the images of-
the background, foreground, the player, the obstacles(snail and fly).<br> The score is incremented

by using a simple counter variable and the high score is stored in a text file. After each play the
score is compared with the file and stored if greater than the high score.<br> Every time we press
the game button in the main class, we check if the player has 100 or more coins. Only then the
game starts. After completion of the game, 100 coins are deducted from the coins text file. The
collisions are detected using the inbuilt functions of the library.<br>

<h3>Module 4: The Button class-</h3>
Methods created:<br>

● __init__(): to initialise all variables of the class<br>
● update(): to apply underlying image to button<br>
● checkforInput: to check if the coordinates of the mouse are within the bounds of the
button’s rectangle. If it is, then it returns the boolean value “True”.<br>
● changeColour(): to change the colour of the text on the button when the mouse hovers
over it<br>
The Button class is stored in a user defined button.py module. It’s __init__() function is used to
initialise all the requisite variables. The button is created such that it has an underlying image,
and the text written on top of it. If no underlying image is provided, the text is displayed atop a
transparent surface. On hovering the mouse over a button object of this class, the text changes
colour to show that it has been detected.<br>

<h3>Module 5: The coins Tracker-</h3>
In this module, we have 2 methods- coins_increase() and coins_decrease()<br>

● coins_increase() gets activated once we finish a task in the task-list module.The user
gets 100 coins and this also gets written in a text file in the backend.<br>
● Similarly, the coins_decrease() method gets activated once we click on play game and
the user has 100 or more coins. The coins are decremented by 100 and this also gets
stored in the backend.<br>
In both these cases, a message box made by using the tkinter library informs the user of the
changes in their coins.<br>
