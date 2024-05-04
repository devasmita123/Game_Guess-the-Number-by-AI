# Group RC_Guess-the-Number-by-AI

The game involved in the provided code is a simple version of the "Guess the Number" game. Here's how it works:

# Initialization: 
The game starts by generating a random target number between 1 and 100. This number is kept secret from the player (or the AI in this case).

# Player's Turn: 
The AI makes a guess by selecting a random number between the specified range (1 to 100). This guess is printed to the console.

# Feedback: 
The player provides feedback on the AI's guess. The feedback can be one of the following:

    # "H" (Too High): 
    If the AI's guess is higher than the target number.
    
    # "L" (Too Low):
    If the AI's guess is lower than the target number.
    
    # "C" (Correct):
    If the AI's guess is correct and matches the target number.
    
# Adjusting Strategy:
Based on the feedback provided by the player, the AI adjusts its strategy for the next guess. If the guess was too high, the AI eliminates all numbers higher than the guess from its potential guesses. Similarly, if the guess was too low, the AI eliminates all numbers lower than the guess.

# Repeating Steps:
Feedback and Adjustment of stratergy are repeated until the AI correctly guesses the target number. Once the correct number is guessed, the game ends and a victory message is displayed.

# Target:
The goal of the game is for the AI to guess the target number within as few attempts as possible by learning from the feedback provided by the player after each guess. The AI's strategy evolves based on the feedback received, allowing it to make more informed guesses as the game progresses.
