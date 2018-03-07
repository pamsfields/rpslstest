"""Pam Fields
1150-91
11/14/2015
"""
# The key idea of this program is to equate the strings
# "rock", "paper", "scissors", "lizard", "Spock" to numbers
# as follows:

# 0 - rock
# 1 - Spock
# 2 - paper
# 3 - lizard
# 4 - scissors

#imports
import random #needed for calculating the comp choice

# helper functions

#converts number to a name
def number_to_name(comp_number):
    if comp_number == 0:
        return 'rock'
    elif comp_number == 1:
        return 'Spock'
    elif comp_number == 2:
        return 'paper'
    elif comp_number == 3:
        return 'lizard'
    else:
        return 'scissors'
   
# converts name to number
def name_to_number(player_choice):
    if player_choice == 'rock':
        return 0
    elif player_choice == 'Spock':
        return 1
    elif player_choice == 'paper':
        return 2
    elif player_choice == 'lizard':
        return 3
    elif player_choice == 'scissors':
        return 4
    else:
        print("Error, invalid response, please choose 'rock', 'paper', 'scissors', 'lizard' or 'Spock' by typing that word ")

def rpsls(player_choice): 
 
     
    # print a blank line to separate consecutive games
    print ("\n")
     
    # print out the message for the player's choice
    print ("Player chooses ", player_choice)
     
    # convert the player's choice to player_number using the function name_to_number()
    player_number = name_to_number( player_choice )
     
    # compute random guess for comp_number using random.randrange()
    comp_number = random.randrange( 0, 4 )
    
    # convert comp_number to comp_choice using the function number_to_name()
    comp_choice = number_to_name( comp_number );
     
    # print out the message for computer's choice
    print ("Computer chooses ", comp_choice)
     
    # compute difference of comp_number and player_number modulo five
    difference = (comp_number - player_number) % 5
     
    # use if/elif/else to determine winner, print winner message
    if( difference == 1 or difference == 2 ):
        return "Computer wins!"
    elif ( difference == 4 or difference == 3 ):
        return "Player wins!"
    elif( difference == 0 ):
        return "Player and computer tie!"

print("Let's play 'Rock, Paper, Scissors, Lizard, Spock'!")
player_choice = input("Choose 'rock', 'paper', 'scissors', 'lizard' or 'Spock' by typing that word. ")
winner=rpsls(player_choice)
print(winner)

def restart(answer):
    #if/elif statement
    if answer == 'y':
        rpsls(player_choice)
    elif answer == 'n':
        print("Goodbye!")
    else:
        print("Please enter only 'y' or 'n'!")
        #call restart

answer = input("Would you like to play again? Enter 'y' for yes or 'n' for no: ")
play_again=restart(answer)
