# My Portfolio

## Stupid Superpowers

[Repository Link](https://github.com/joshualiu555/Stupid-Superpowers "Repository")

[Website Link](https://stupid-superpowers.herokuapp.com "Stupid Superpowers Web Version")

This is the web version of a card game I made with two friends called "Stupid Superpowers." It is an "Apples to Apples" or "Cards Against Humanity" remake with only stupid superpowers.
My web stack consisted of HTML, CSS, React, Node.js, Express.js, and Socket.io, multiple npm packages (profanity checker, random name generator, countdown). The website was deployed on Heroku. 

There is no account creation, as the game is meant to be played casually without any need for progress. 

<img width="826" alt="Screen Shot 2023-01-02 at 7 56 30 PM" src="https://user-images.githubusercontent.com/53412192/210291081-1c95b494-d7e0-493e-bafb-f499ae43dc2d.png">

### How The Code Works

##### Layout
I used flexbox to format the homescreen, lobby, and result screen in columns and rows. 
I used grid to format the game screen. This made separating the prompt, cards, scoreboard, and chat very simple.

##### Frontend and Backend
Whenever a user clicks something on the frontend, socket.io emits certain parameters such as player id to the backend "database." The backend then works through the array and does its magic, as I will describe below. 

##### Joining a Game
Here's how the temporary "database" is formatted.

- Array of Games
  - Game Attributes: Color, Code, Prompts, etc.
  - Chat
  - Array of Players
    - Player Attributes: Score, Powers, etc.
    
When a player joins a game, whether randomly or by code, the program searches for a valid room and allows them to join the lobby. Otherwise, an error message shows up. 

##### Playing the Game
There is a countdown that works by resetting the React state every second. When a player chooses a card, they can submit and that changes their player attribute. When every player has selectd, the game attribute changes to "voting." The voting system works similar to the selecting system. When everyone votes, the highest scoring players get an extra point to their score. If someone has reached 7, the winning screen occurs. Otherwise, the game chooses the next prompt card in the deck. Each player then discards a power from their array and randomly picks a new one.

##### Chat
Each game has an array of chats. When a player enters a chat, the program finds the game code, and registers it into its chat array. Socket.io then sends the text back to the frontend.

## Stress Tester

This Java application is designed to facilitate stress testing for coding solutions by comparing the output of a user-written solution against a brute-force solution using generated test cases. The application leverages JavaFX for a graphical user interface, allowing users to input their code directly into text areas.

### Features

- **Test Case Generation:** Automatically generates test cases using user-provided code.
- **Solution Testing:** Runs both the user's solution and a brute-force solution on the generated test cases.
- **Output Comparison:** Compares the outputs of the two solutions to verify correctness.
- **User Interface:** Simple and interactive UI to input code and view results.

### How It Works

#### Components

- **Text Areas:** Users input their test case generator, solution, and brute-force solution code into the corresponding `TextArea` fields.
- **Compilation:** The provided code is compiled at runtime using the Java Compiler API.
- **Execution:** The test case generator code is executed to produce input data, which is then fed into both the solution and brute-force solution for comparison.
- **Output:** The application displays whether the solution passed or failed the test case. In the event of a failure, it shows the test case input, the user's solution output, and the expected output.

#### Detailed Flow

1. **Input Handling:** 
   - The application captures the code from the `TextArea` fields for the test case generator, solution, and brute-force solution.

2. **File Writing:**
   - The input code is written to corresponding `.java` files: `Generator.java`, `Solution.java`, and `BruteForce.java`.

3. **Compilation:**
   - The Java files are compiled using the `JavaCompiler` class.

4. **Execution:**
   - A separate thread is created to handle the execution and comparison process.
   - The test case generator (`Generator.java`) is executed, and its output is captured.
   - This output is then fed into both the solution (`Solution.java`) and brute-force solution (`BruteForce.java`).
   - The outputs of both solutions are compared:
     - If they match, the test case is marked as passed.
     - If they differ, the application stops and displays the failed test case details, including the input and both outputs.

5. **Output Display:**
   - The result of each test case is displayed in the `outputTextArea` field.

#### Thread Management

- The application uses a separate thread (`runningThread`) to manage the execution of test cases, allowing it to handle multiple cases in sequence without freezing the UI.
- The thread is set as a daemon, ensuring it doesn't prevent the application from shutting down.

### How to Use

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/stress-tester.git
   ```
2. **Open the Project:**
   - Open the project in your preferred Java IDE.
3. **Run the Application:**
   - Run the main application and input your test case generator, solution, and brute-force solution in the respective text areas.
4. **Start Testing:**
   - Click the "Start" button to begin the stress testing process.
   - View the results in the output area.

### Requirements

- Java 8 or higher
- JavaFX library

### Contributing

Feel free to submit issues or pull requests to contribute to this project.

### License

This project is licensed under the MIT License.

<img width="757" alt="Screenshot 2024-08-11 at 11 55 29 AM" src="https://github.com/user-attachments/assets/c6551fa4-771e-4551-aafc-fb42d67403f5">

## Find-A-Swim
Allows users to search public workouts based on stroke and distance. Also allows them to register / login and create their own workouts.

[Website Link](https://find-a-swim-1b209de32774.herokuapp.com)

#### Public Workouts
Has two dropdowns that allows users to search workouts based on stroke and distance.

<img width="324" alt="Screen Shot 2023-12-03 at 7 00 02 PM" src="https://github.com/joshualiu555/Find-A-Swim/assets/53412192/63c10f4e-9e3a-4ae5-933a-534ea4bba7c1">

#### Create Workout
If logged in, a user can create a workout. This is prevented if you are just a guest user. 

<img width="407" alt="Screen Shot 2023-12-03 at 7 01 03 PM" src="https://github.com/joshualiu555/Find-A-Swim/assets/53412192/8792305a-1fc8-40a1-9d5f-382d1a917e86">

#### My Workouts
If logged in, a user can view their own workouts. They can also edit or delete each workout. 

<img width="325" alt="Screen Shot 2023-12-03 at 7 01 40 PM" src="https://github.com/joshualiu555/Find-A-Swim/assets/53412192/715c2df5-1dbd-40a4-ba31-a8620401fcd1">

#### Login / Register
Allows user to register or login to their account. 

<img width="307" alt="Screen Shot 2023-12-03 at 7 02 05 PM" src="https://github.com/joshualiu555/Find-A-Swim/assets/53412192/1986ef85-e179-466c-86f3-5831feab1879">

#### See For Yourself
1) Download this repo as a zip and uncompress
2) Run npm install on both the client and server directories
3) Run `npm run dev` in the server directory
4) Run `npm start` in the client directory

#### Deploy to Heroku
1) Add Procfile and write `web src/index.js`
2) Run `npm build` in the client directory
3) Copy that content and put it in a folder called "public" in the server directory
4) Deploy with Heroku CLI instructions


## Pixel Art Maker

[Repository Link](https://github.com/joshualiu555/Pixel-Art-Maker "Repository")

[Link to Project](https://replit.com/@joshualiu555/Pixel-Art-Maker#main.py "Link To Project")

Program Purpose: Allows the user to make pixel art 

Features: 16 colors, pencil, eraser, trashcan, square, line, bucket, undo / redo, export, different mouse size

Language: Python and Pygame

[Inspired by pixilart](https://www.pixilart.com)

![14:31:58](https://user-images.githubusercontent.com/53412192/120903395-8435f280-c60b-11eb-951d-b96d30303164.png)

### Class Overview
###### Pixel
Attributes: Color, position

Methods: Change color

###### Icon - Pencil, eraser, trashcan, etc.
Attributes: Image name, tool / icon name, position

Methods: Draw border

###### Mouse
Attributes: Size, color

Methods: Update - Highlights current pixel, becomes transparent if it is not on the board, changes cursor to diamond if it is on the board

###### Mouse Box - Boxes that show the size of the mouse
Attributes: Position

Methods: Update - Sets to visible or transparent depending on mouse size

###### Color Box - 16 of these that each represent a color presented in a grid
Attributes: Color, position

Methods: Draw circle - draws a circle in the box if it is selected

###### Tool - Each icons individual function when called
Trashcan: Erases the whole board and resets the alternating gray and white grid

Export: Takes a picture of the canvas and saves it to a screenshot folder

Bucket: Fills the surrounding area with a color

Pencil: Changes a pixel's color

Eraser: Resets a pixel's color to its original gray or white

Square: Creates a square based on 2 selected points (Bugs - Sometimes doesn't respond, when undoing, the second point is erased too)

Line: Creates a line based on 2 selected points (Bugs - same as square)

Undo: Reverses the board to the previous state (Bugs - takes 2 clicks for the first undo)

Redo: Restores the board to the state you just had (Bugs - same as undo)

### How the program works - main.py
###### new() - initializing everything
The board and current selections (tool, mouse size, color) are created using a text file that allows for saving previous work.

Each class has its own sprite group and list containing instance

###### run() - performs every essential part of the game loop

###### events() - checks for mouse or keyboard events
Checks for escape key to exit. If it is, the program saves the current board and selections.

Checks if the mouse is being clicked. Everytime the mouse is released, a new board state is pushed to the undo stack

Checks for arrow keys to change the mouse size

###### update() - hanges the board and current selection
Checks if there the mouse and pixel collide. If they do, they perform the necessary function based on the current tool.

Checks if a color box or tool has been selected. 

Updates the amount of mouse boxes to be shown.

Updates every sprite (polymorphism)

###### draw() - fills the screen, draws the sprites and borders, updates the display

###### program instance - creates the program

### Install as an executable file
Open the terminal / command line

pip install pyinstaller

Open up a terminal / command line inside the directory

pyinstaller --add-data "board.txt:." --add-data "reset.txt:." --add-data "selections.txt:." --add-data "icons:icons" --add-data "screenshots:screenshots" main.py

Go to dist and select main.exe

## Maze Generator And Solver
Program Purpose: Generates a maze that then solves itself

Language: Python and Pygame

Algorithm: Randomized DFS / Floodfill / Recursive Backtracking

[Link to Project](https://replit.com/@joshualiu555/Maze-Generator-and-Solver#main.py)

[Wikipedia Algorithm Pseudocode](https://en.wikipedia.org/wiki/Maze_generation_algorithm)

[Inspired by The Coding Train](https://www.youtube.com/watch?v=HyK_Q5rrcr4rl)

[Demo](https://user-images.githubusercontent.com/53412192/120880638-39779480-c591-11eb-914e-c4ae03ddb413.mov)


### How the program works
###### Generation
1) Maintain a matrix that keeps track of visited cells
2) Maintain a stack that keeps track of cells on the current path
3) Start at the top left cell
4) Randomly choose one of the available neighbor cells
5) If there are none, go to previous cell in the stack
6) Color visited cells blue, current cell blue, and remove the white wall
7) Will eventually return to the top left cell and guarantees a maze
###### Solving
1) Maintain a matrix that keeps track of visited cells
2) Maintain a stack that keeps track of cells on the current path
3) Start at the top left cell
4) Randomly choose one of the available neighbor cells without a wall
5) If there are none, go to previous cell in the stack
6) Color visited cells green and current cell red
7) Will eventually reach the bottom right cell, at which point the program restarts

### Code Overview
1) A matrix of cell classes: each cell instance maintains properties such as a wall array, visited / current booleans, and methods to draw to the screen
2) Simulation Function 
   1) Generation - Find next cell, check if it is inbounds and unvisited, remove the wall, move to that cell 
   2) Solving - Find next cell, check if it is inbounds and unvisited, move to that cell

### Install as executable file
Open the terminal / command line

`pip install pyinstaller`

Put `maze.py` inside of a folder called `main` (or whatever name you want)

Open up a terminal / command line inside the folder

`pyinstaller --onefile -w maze.py`

Go to `dist` and select `main.exe`


## Strategy Steps
[Repository Link](https://github.com/joshualiu555/Strategy-Steps "Repository)

A recreation of the Wii Party Minigame, "Strategy Steps" Allows unlimited players (preferably 4) Each round, players select a number: 1, 3, 5 After each round, if a player is the only number to select that number, they move up that number of steps. First to 10 wins

The program uses the discord API and discord buttoms library. The entire game is asynchronous as it relies on user inputs. 

It cannot support multiple games being played.
When an request to start the game is entered, an array of players is made in this format.

- Player array
  - Score, Number Chosen
  
<img width="288" alt="Screen Shot 2023-01-02 at 4 05 32 PM" src="https://user-images.githubusercontent.com/53412192/210280920-39aaec86-9456-4edf-b857-54af5af875e3.png">

#### How To Play
1) Begin The Game

> .start @player1 @player2

<img width="258" alt="Screen Shot 2023-01-02 at 4 06 31 PM" src="https://user-images.githubusercontent.com/53412192/210280969-2fc89ef2-c4fd-4ed8-943b-7644f1ed1e8f.png">

2) Start The Round

> .next

<img width="197" alt="Screen Shot 2023-01-02 at 4 08 29 PM" src="https://user-images.githubusercontent.com/53412192/210281068-51fd3ee9-ccd6-46c2-b8e1-f91c6069bde4.png">

3) Choose Your Number

> Simply click a button. The results will appear once everyone has chosen a number

<img width="290" alt="Screen Shot 2023-01-02 at 4 10 19 PM" src="https://user-images.githubusercontent.com/53412192/210281152-30847a53-6e50-473b-83af-a3838a6323ac.png">

4) End The Game

> .end

<img width="259" alt="Screen Shot 2023-01-02 at 4 11 13 PM" src="https://user-images.githubusercontent.com/53412192/210281188-c822c9b2-4411-4ad7-b77d-6470b72ce39f.png">

## Conway's Game of Life
[Repository Link](https://github.com/joshualiu555/Game-Of-Life "Repository)

A Python / Pygame simulation of Conway's Game of Life

The entire simulation runs on a Program Class. Once an instance is initialized, the program creates a new board. Each cell is its own class and is able to change states. 
Once initialized, the program object begins an infinite while loop until the user exits the program.

There is a 2D Grid of cells. Each cell checks its 4 neighbors. 

1) Every live cell with 2 or 3 neighbors lives on.
2) Every live cell with 4 neighbors dies due to overpopulation.
3) Every live cell with 1 neighbor dies due to underpopulation.
4) Every dead cell with 3 neighbors is reborn due to reproduction.

<img width="481" alt="Screen Shot 2023-01-02 at 4 25 03 PM" src="https://user-images.githubusercontent.com/53412192/210281828-762512ce-5a9e-40a6-a653-7eef12620b32.png">

## Chaos Game
[Repository Link](https://github.com/joshualiu555/Chaos-Game "Repository)

A Pygame program that simulates the Chaos Game theory to generate a fractal. 

1) Draw three dots in the form of a triangle
2) Start at point 1
3) Randomly choose a point 1-3
4) Draw a dot in the middle of those two points
5) This dot is your new point
6) Repeat from step 3 continuosly

You wil eventually draw the Sierpinski triangle

<img width="378" alt="Screen Shot 2023-01-02 at 4 29 23 PM" src="https://user-images.githubusercontent.com/53412192/210282032-90d7028b-a746-43a1-812a-d0ae69f637a0.png">

## Rock Paper Scissors
[Repository Link](https://github.com/joshualiu555/Rock-Paper-Scissors "Repository)

A Javascript rock paper scissors game that let's you type a username and select how many games to play against the CPU.

#### Main Menu
1) Type Your Username
2) Choose how many rounds someone has to win for the game to end. 
3) Start the Game

<img width="422" alt="Screen Shot 2023-01-02 at 4 15 49 PM" src="https://user-images.githubusercontent.com/53412192/210281394-3dd7aa5a-d0ae-4afc-af03-23d92c0bef09.png">

#### Game Screen
1) Choose your icon
2) Click shoot
<img width="642" alt="Screen Shot 2023-01-02 at 4 17 16 PM" src="https://user-images.githubusercontent.com/53412192/210281457-5bbb6555-aa63-45ee-9a37-23c711f6f989.png">

The result will appear and you keep playing until the game ends. 

