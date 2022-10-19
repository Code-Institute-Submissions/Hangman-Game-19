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
