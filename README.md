# Game_Guess-the-Number-by-AI
# The code implements a "Guess the Number" game where the AI guesses a number within a range based on feedback from the player, aiming to minimize attempts.
import random

# Function to get AI's guess based on learned strategy
def get_ai_guess(strategy, min_num, max_num):
    if not strategy:
        return random.randint(min_num, max_num)
    valid_guesses = [(key, value) for key, value in strategy.items() if min_num <= key <= max_num]
    if valid_guesses:
        return max(valid_guesses, key=lambda x: x[1])[0]
    return random.randint(min_num, max_num)

# Function to update AI's strategy based on the player's feedback
def update_strategy(strategy, guess, feedback):
    strategy[guess] = feedback

# Function to play the game
def play_game():
    min_num = 1
    max_num = 100
    target_number = random.randint(min_num, max_num)
    strategy = {}

    print("Welcome to Guess the Number!")
    print(f"I'm thinking of a number between {min_num} and {max_num}.")

    while True:
        ai_guess = get_ai_guess(strategy, min_num, max_num)
        print(f"My guess is: {ai_guess}")

        feedback = input("Is my guess too high (H), too low (L), or correct (C)? ").upper()

        if feedback == "C":
            print("I guessed it right! Thanks for playing.")
            break
        elif feedback == "H":
            max_num = ai_guess - 1
        elif feedback == "L":
            min_num = ai_guess + 1

        update_strategy(strategy, ai_guess, feedback)

        # Adjusting AI's knowledge based on the feedback
        if feedback == "C":
            # If the guess was correct, we don't need to adjust the strategy
            pass
        elif feedback == "H":
            # If the guess was too high, update strategy to avoid higher numbers
            for guess in list(strategy.keys()):
                if guess > ai_guess:
                    del strategy[guess]
        elif feedback == "L":
            # If the guess was too low, update strategy to avoid lower numbers
            for guess in list(strategy.keys()):
                if guess < ai_guess:
                    del strategy[guess]

# Main function
def main():
    play_game()

if __name__ == "__main__":
    main()
import random

# Function to get AI's guess based on learned strategy
def get_ai_guess(strategy, min_num, max_num):
    if not strategy:
        return random.randint(min_num, max_num)
    valid_guesses = [(key, value) for key, value in strategy.items() if min_num <= key <= max_num]
    if valid_guesses:
        return max(valid_guesses, key=lambda x: x[1])[0]
    return random.randint(min_num, max_num)

# Function to update AI's strategy based on the player's feedback
def update_strategy(strategy, guess, feedback):
    strategy[guess] = feedback

# Function to play the game
def play_game():
    min_num = 1
    max_num = 100
    target_number = random.randint(min_num, max_num)
    strategy = {}

    print("Welcome to Guess the Number!")
    print(f"I'm thinking of a number between {min_num} and {max_num}.")

    while True:
        ai_guess = get_ai_guess(strategy, min_num, max_num)
        print(f"My guess is: {ai_guess}")

        feedback = input("Is my guess too high (H), too low (L), or correct (C)? ").upper()

        if feedback == "C":
            print("I guessed it right! Thanks for playing.")
            break
        elif feedback == "H":
            max_num = ai_guess - 1
        elif feedback == "L":
            min_num = ai_guess + 1

        update_strategy(strategy, ai_guess, feedback)

        # Adjusting AI's knowledge based on the feedback
        if feedback == "C":
            # If the guess was correct, we don't need to adjust the strategy
            pass
        elif feedback == "H":
            # If the guess was too high, update strategy to avoid higher numbers
            for guess in list(strategy.keys()):
                if guess > ai_guess:
                    del strategy[guess]
        elif feedback == "L":
            # If the guess was too low, update strategy to avoid lower numbers
            for guess in list(strategy.keys()):
                if guess < ai_guess:
                    del strategy[guess]

# Main function
def main():
    play_game()

if __name__ == "__main__":
    main()
