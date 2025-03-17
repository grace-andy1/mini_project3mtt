import random

def number_guessing_game():
    # Step 1: Generate a random number between 1 and 100
    number_to_guess = random.randint(1, 100)
    guess = None
    attempts = 0

    print("Welcome to the Number Guessing Game!")
    print("I have selected a number between 1 and 100. Can you guess it?")

    # Step 4: Loop until the user guesses the correct number
    while guess != number_to_guess:
        try:
            # Step 2: Prompt the user to enter their guess
            guess = int(input("Enter your guess: "))
            attempts += 1

            # Step 3: Conditional statements to provide feedback
            if guess < number_to_guess:
                print("Too low! Try again.")
            elif guess > number_to_guess:
                print("Too high! Try again.")
            else:
                print(f"Congratulations! You've guessed the number in {attempts} attempts.")
        except ValueError:
            print("Please enter a valid number.")

if __name__ == "__main__":
    number_guessing_game()
