# Makefile to generate README.md file

README.md: guessinggame.sh
    echo "# Guessing Game" > README.md
    echo "This is a simple guessing game written in Bash." >> README.md
    echo "## Information" >> README.md
    echo "Date and Time: $(date)" >> README.md
    echo "Lines of Code: $(wc -l < guessinggame.sh)" >> README.md
