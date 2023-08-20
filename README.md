import random

# List of possible colors
colors = ["red", "blue", "green", "yellow", "black", "white"]

# Game variables
score = 0
time_left = 30

# Function to choose the next color
def next_color():
    global color
    color = random.choice(colors)

# Function to update the score
def update_score(correct):
    global score
    if correct:
        score += 1

# Function to display the game
def display_game():
    global color, time_left
    print("Current color:", color)
    print("Time left:", time_left)

# Main game loop
while time_left > 0:
    # Choose the next color
    next_color()

    # Get the user's guess
    guess = input("What is the color? ")

    # Check if the guess is correct
    correct = guess.lower() == color.lower()

    # Update the score
    update_score(correct)

    # Display the game
    display_game()

    # Decrement the time left
    time_left -= 1

# Print the final score
print("Your final score is:", score)
