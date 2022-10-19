# Hangman
#

### About Hangman
Hangman is a guessing game in which the objective of the player is to find out the hidden word. Every incorrect guess leads to the decrement of the chances left for the player.

The chances left are represented in the form of a hanging man. And the job of every hero is to save lives.

### Designing Hangman
Before we move on to the section of creating the game logic, we first need to figure out how the game will look for any player. There are two particular design components in this game:

🠖 The Hangman – We need to provide a visual aid to the player in the context of the hanging man.
🠖 Word Display – At the start of the game, the word must be displayed as blanks, instead of letters.

### Hangman Design
As we know, after every incorrect move, a new part of the hanging man’s body is displayed. To implement this, we store the body parts in a list.

<img src="assets/images/screenshot1.png" width="400">

The function that handles these hangman values is presented below:

<img src="assets/images/screenshot2.png" width="400">

The image below displays all the hangman states possible in the game. Each incorrect mistake adds a body part until the body is complete and the player loses.

<img src="assets/images/screenshot3.png" width="400">

The state displayed in the image below represents the hangman escaping the gallows after the player guesses the complete word.

<img src="assets/images/screenshot4.png" width="400">

The function below, 'print_hangman_win()' takes care of printing the escaped hangman when the player wins.

<img src="assets/images/screenshot5.png" width="400">

### Word display
The 'clear()' function is responsible for clearing the terminal. It makes use of inbuilt 'os' library of Python.

<img src="assets/images/screenshot0.png" width="400">

At the start of the game, only the blanks must be visible. After each player input, we must manipulate what needs to be displayed.

<img src="assets/images/screenshot6.png" width="400">

Initially, the list 'word_display' contains underscores for every alphabet in the hidden word. The following function is used to display this list.

<img src="assets/images/screenshot7.png" width="400">

### Data-set for words
In this part of creating the game, we can let our imagination run wild. There can be multiple ways to access the list words like importing from a .csv file, extracting from a database, etc.
To keep this project simple, I have hard-coded some categories and words.

<img src="assets/images/screenshot8.png" width="400">

Let us understand the data-structures used here:
🠖 'topics'– This Python dictionary provides, each category with a numeric value. This will further be used to implement a category-based menu.
🠖 'dataset' – This Python dictionary contains a list of words in each category. After the player chooses a category, we are supposed to pick words from here itself.

### Game Loop
Every game which depends upon a series of moves from the player requires a game loop. This loop is responsible for managing the player input, displaying game design, and other essential parts of game-logic.

<img src="assets/images/screenshot9.png" width="400">

Inside this game loop, we will take care of the following things:

- Game Menu
The game menu is responsible for providing the notion of game-control to the player. The player decides the category on the basis of his/her interests.

<img src="assets/images/screenshot10.png" width="400">

It is advisable to always provide an option of quitting the game, whenever a game menu is created.

- Handling the player’s category choice
A game developer no matter what level of skill, must always handle player input with great attention. The game must not crash on some erroneous player input.

<img src="assets/images/screenshot11.png" width="400">

After doing some sanity checks, we are ready to pick the word for the game-play.

### Pick the game-play word
We use the inbuilt Python library, 'random' for picking a random word from the specific category list.

<img src="assets/images/screenshot13.png" width="400">

After picking the word, comes the game-logic section.

### Game-Logic for Hangman
The function 'hangman()' contains the entire game functioning. It includes storing incorrect guesses, reducing the number of chances left, and printing the specific state of hangman.

<img src="assets/images/screenshot14.png" width="400">

The above code snippet contains all the elementary data structures and variables required for smooth functioning of our hangman game.

### Initialize necessary components
One of the most important aspects of creating a game is the initial state of the game components.

<img src="assets/images/screenshot15.png" width="400">

We are required to initialize the structure of word display as it will vary for every other word for the game. For our convenience, we initialize the container for storing the correct letters, in the same loop.

Note: This version of the hangman game only supports the guessing of the alphabets. If the reader wants to add the functionality of guessing other elements like numbers or special characters, the changes have to be made here.

### Inner game loop
This inner game loop is responsible for controlling the flow of single gameplay of the hangman game. It includes showing proper display, handling character input, updating the necessary data structures, and other key aspects of the game.

<img src="assets/images/screenshot16.png" width="400">

### Player’s move input
This part of our game deals with the player’s interaction with our game. The input must be checking for few scenarios before implementing it in the game logic:

🠖 Valid length – Since we are accepting a single character, we need to check in case the player mischievously enters multiple characters.
🠖 An alphabet? – As told before, our version of the hangman game only supports guessing of alphabets.
🠖 Already tried – Being a considerate programmer, we have to notify if the player enters an incorrect and already tried alphabet.

<img src="assets/images/screenshot17.png" width="400">

### Manage the player’s move
It is quite obvious that we will come across only two situations while managing the player’s move.

🠖 Incorrect Alphabet – For an incorrect move, we update the list of incorrect letters and the hangman display (adding body-parts).

<img src="assets/images/screenshot18.png" width="400">

🠖 Correct Alphabet – In case, a capable player enters a correct alphabet, we update our word display.

<img src="assets/images/screenshot19.png" width="400">
