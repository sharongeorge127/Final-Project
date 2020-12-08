Final-Project

# importing the time module
import time

# importing the random module
import random

# word list for guessing
wordList = ["Temple"]
hidden = [] 
for character in wordList: 
  hidden.append ("_")

attempts = 0
max_attempts = 6

# welcoming the user
name = input("What is your name?\t")

print("Hi, " + name, "!", "Let's play a game of hangman!")

print()

# loop until player has won or lost the game 
isGameOver = False
while not isGameOver: 
# display the current board, guessed ,letters, and remaining attempts 

  print(f"You have {max_attempts - attempts} attempts remaining") 

  # hiddenString = 
  print(f"The current word is: {''.join(hidden)}") 
  
  print('     ------')
  print('     |     |')
  print('     |     ' + ('0' if attempts > 0 else ''))
  print('     |     ' + ('/\\' if attempts > 1 else ''))
  print('     |     ' + ('|' if attempts > 2 else ''))
  print('     |     ' + ('/\\' if attempts > 3 else '')) 
  print('-----------') 

  break 
  
# wait for 1 second
time.sleep(1)  

print("Guess a letter!\n")

# wait for 1 second
time.sleep(0.5)

# here we set the secret
secretWord = random.choice(wordList)

# creates a string type variable which is empty
guesses = ''

# creating an empty list
guessList = []

# determine the number of turns
turns = 10

# Create a while loop that checks if the turns are more than zero
while turns > 0:

    #make a counter that starts with zero
    failed = 0

    # for every letter in secret_word
    for word in secretWord:

        #see if the letter is in the players guess
        if word in guesses:

            #print then out the letter
            print (word,end = '')

        else:

            # if not found, print a dash
            print ("_ ", end = '')

            # and increase the failed counter with one
            failed += 1

    # if failed is equal to zero
    # print You Won
    if failed == 0:
        print("\n\nCongratulations, You Won!",secretWord,"is the correct answer!")

        #exit the script
        break

    print()

    # ask the user go guess a word
    guess = input("Guess a letter!:")
    print()

    if guess not in guessList:

        # adding the guessed letter to the list
        guessList.append(guess)

        # set the players guess to guesses
        guesses += guess

        # if the guess is not found in the secret word
        if guess not in secretWord:

            # turns counter decreases with 1 (now 9)
            turns -= 1

            # print wrong
            print("Sorry, wrong guess. This letter is NOT part of the word!")
            

            if turns != 0:

                # how many turns are left
                print ("You have", + turns, "more guesses")
                print()

            # i f the turns are equal to zero
            if turns == 0:
                print("You have no more turns left")

                # print "You Loose"
                print ("\nSorry, You Lose. Better Luck Next Time!")
                print("The correct word was:",secretWord)

    # if user has already guessed that letter
    else:
        print("You already guessed this letter, try another one")
        continue


                  
