# Python Techdegree Project 1
import random

def start_game() :
    print("This is a game where you pick a number 1 through 10")

def play_game() :
    # I found this line of code at pythonspot.com was not really sure how to generate random numbers
    random_number = random.randint(1 , 10)
    attempts = 0
    while True :
        try:
            guess_number = int(input("\nEnter a number 1 through 10: "))
        except ValueError :
            print("Sorry. Only number numbers 1 through 10 are appropriate. Please try again.")
        else :
            if guess_number == random_number :
                attempts += 1
                print("Congradulations {} is the right number! It took you {} times to figure it out.".format(random_number , attempts))
                break
            elif guess_number < random_number and guess_number >= 1:
                attempts += 1
                print("Sorry {} is lower than the right number. Please try again.\n".format(guess_number))
                continue
            elif guess_number > random_number and guess_number <= 10:
                attempts += 1
                print("Sorry {} is higher than the right number. Please try again.\n".format(guess_number))
                continue
            else :
                print("Your guess of {} was outside of the range. We are playing from 1 to 10. Please try again. We will not count this attempt.\n".format(guess_number))
                continue
    print("\nYou have finished the game.")

def another_game() :
    while True :
        play_again = input("\nWould you like to play again? (yes or no) ")
        if play_again.lower() == "yes" :
            play_game()
        elif play_again.lower() == "no" :
            print("Thanks for playing. Hope to see you soon.")
            break
        else :
            print("\nInvalid Input. Please Try Again.")


start_game()
while True :
    want_to_play = input("\nWould you like to play the game? (yes or no) ")
    if want_to_play.lower() == "yes" :
        play_game()
        another_game()
        break
        print("Thanks for playing the game. Hope to see you soon!")
    elif want_to_play.lower() == "no" :
        print("Hope to see you again.")
        break
    else :
        print("Sorry Invalid Input.")
        continue
