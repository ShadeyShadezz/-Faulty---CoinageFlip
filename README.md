# -Faulty-CoinageFlip
Purpose/Problem Statement - Ever need to make a choice? Unsure of which side you'd want to take part in? Use a coin flip app with a vacation function to give a random city you could travel to if thats what you're trying to decide on!

Who is this for? Generally anybody, but specifically people who'd want to tweak a coin toss to more specific coin toss game

Solution + Limitations - While you CAN add more than one coin, it won't print. I wasnt sure how id go about adding multiple instances of different coins that the user could add AND remove.

Key Features / Key Components - Flip one (or two) coin(s), edit coins, vacationary decider as an added bonus

Technical Challenges + Future Plans - If I could i'd add it so you could add as many coins as you could, that way you could technically make it a vote decider

Project Timeline - First Week, Concept. Second Week, Set up. Third Week, Finalization.

Tools and Resources Used - https://publicapis.io/teleport-api 

## - Imports - ##

import random
import math
import requests

## - Starting Program Text - ##

present_coins = 0

def get_random_city():
    # Fake list of cities:
    cities = ["Tokyo", "Paris", "New York", "Cape Town", "Sydney", "Oslo", "Buenos Aires"]
    return random.choice(cities)

print("Welcome to, Ultimate Coin Flip!")
print()

answer = input("Would you like to play? yes/no: ") 

if answer == "yes":
    print("Great! let's get started by telling you the commands!")

else:
    print("Sorry to hear that! This Program will now end...")
## - Prompt to continue the program if an answer that affirms the continuation of the dialogue corresponds correctly advancing the program - ## 
## - Prompt for Loop if answer corresponds to yes - ##
if answer == "yes":
    print("\n")
    print("\n")
    print("There are FIVE commands to remember!")
    print("add-coin, remove-coin, flip-coin, check-coin, end-game, and vacation-game Anything else won't be accepted as it will end the program, Enjoy! ")
    print("\n")
## - Text based commands meant to respond to the following loop in order for the program to function - ##
  ## - Coin Command Loop to maintain and eliminate duplicate text - ##
    command = ""
  ## - Stored variable to allow the text based commands to be used - ##
    while command != "end-game":
  ## - Text based command that ends the loop thus ending the program - ##
        command = input("What is your command? ")
        if command == "remove-coin" and present_coins == 0:
            print("There are no coins to remove! ")
            print()
        ## - Interaction IF no coins are present, can't remove something when nothing is there - ##
        elif command == "remove-coin" and present_coins <= 1:
            present_coins -= 1
            print("coin removed!")
            print()
        ## - Interacting command that will remove a coin when input by the user - ##
        elif command == "add-coin":
            present_coins += 1
            print("coin added!")
            print()
        ## - Interaction to add a coin to flip. Mainly here for one coin only - ##
        elif command == "flip-coin" and present_coins == 0:
            print("no coins to flip!")
            print()
        ## - Interating when there are no coins present and the command is unable to follow through - ##
        elif command == "check-coin":
            print("Currently there are " + str (present_coins) + " coin(s)")
            print()
        ## - Interaction to check any amount of coins added or that presently exist within the variable - ##
        elif command == "flip-coin" and present_coins >= 1:
            print("flipping coin..")
        ## - Interaction to present a loop to flip a coin which leads to another line of code - ##
        elif present_coins <= 0:
            continue
        ## - Interaction for vacation game - ##    
        elif command == "vacation-game" and present_coins >= 1:
            city = get_random_city()
            print("How about going on vacation to: " + get_random_city())
            print()
        ## Loop Variable to keep the loop running even without coins, the program will end if anything else is input - ##
        else:
            
            print("Ending program. . . ") 
            break
       ## - Command Loop for Coin Flipping - ##
        if command == "flip-coin" and present_coins >= 1:
                random.choice = random.randint(1,2)
                if random.choice == 1:
                    print("Heads!")
                if random.choice == 2:
                    print("Tails!")
      ## - Command to flip one coin, primarily just for one coin - ##  
      ## - Command Loop for Multiple Coins to be flipped - ##
        if command == "flip-coin" and present_coins > 1:
            random.choice2 = random.randint(1,2)
            if random.choice2 == 1:
                    print("Heads!")
            else:
                    print("Tails!")
