
import random

# NUMBER GUESSING GAME
def number_guessing_game():

    print("\n--- NUMBER GUESSING GAME ---")

    secret_number = random.randint(1, 100)
    attempts = 0

    while True:
        guess = int(input("Guess a number (1-100): "))
        attempts += 1

        if guess < secret_number:
            print("Too low! Try again.")

        elif guess > secret_number:
            print("Too high! Try again.")

        else:
            print("Congratulations! You won!")
            print("Attempts:", attempts)
            break


# WORD COUNTER
def word_counter():

    print("\n--- WORD COUNTER ---")

    filename = input("Enter file name: ")

    try:
        with open(filename, "r") as file:
            content = file.read()

        words = content.split()

        print("Total words:", len(words))

    except FileNotFoundError:
        print("File not found!")


# MAIN MENU
while True:

    print("\n===== PROJECT 02 =====")
    print("1. Number Guessing Game")
    print("2. Word Counter")
    print("3. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        number_guessing_game()

    elif choice == "2":
        word_counter()

    elif choice == "3":
        print("Thank you for using Project 02!")
        break

    else:
        print("Invalid choice! Please try again.")
