#!/usr/bin/env bash

# Function to count the number of files in the current directory
count_files() {
  echo $(ls -1 | wc -l)
}

# Get the correct number of files
file_count=$(count_files)

# Start the guessing game
echo "Welcome to the guessing game!"
echo "Guess the number of files in the current directory."

# Loop until the user guesses correctly
while true; do
  # Prompt for the user's guess
  echo -n "Enter your guess: "
  read guess

  # Check if the guess is a number
  if [[ ! "$guess" =~ ^[0-9]+$ ]]; then
    echo "Please enter a valid number."
  elif [ "$guess" -lt "$file_count" ]; then
    echo "Your guess is too low. Try again."
  elif [ "$guess" -gt "$file_count" ]; then
    echo "Your guess is too high. Try again."
  else
    echo "Congratulations! You guessed the correct number of files: $file_count."
    break  # Exit the loop once the correct guess is made
  fi
done
