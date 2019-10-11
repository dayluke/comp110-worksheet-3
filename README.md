# COMP110 Worksheet 3: Flowcharts and pseudocode

This is the base repository for COMP110 Worksheet 3.

The flowchart for the flow of the game is in this repository. It is named "[terminal_guessing_minigame_flowchart.png](https://github.com/dayluke/comp110-worksheet-3/blob/master/terminal_guessing_minigame_flowchart.png)".
Below is the psudeocode for the terminal hacking minigame:

```
import random

def setup():
    word_list = ["TEXT", "TENT", "BENT", "BEAR", "TEAR", "TART", "CART"] ## These words would be randomly generated (e.g. from a dictionary, with a letter count restraint)

    for word in word_list:
        print(word)
    
    rand_word_index = random.randint(0, len(word_list) - 1)
    secret_word = word_list[rand_word_index]

    guess(secret_word)


def guess(secret_word):
    guesses_left = 3

    while guesses_left > 0:
        player_word = input("Enter word to guess: ").upper()

        if player_word == secret_word:
            end("win")
        else:
            guesses_left -= 1
            calculate_likeness(secret_word, player_word)

    end("lose")



def calculate_likeness(s_word, p_word):
    score = 0

    for i in range(len(s_word)):
        if s_word[i] == p_word[i]:
            score += 1

    print("LIKNESS SCORE: %s" % score)



def end(game_end_state):
    if game_end_state == win":
        print("You win, congratulations!")
    elif game_end_state == "lose":
        print("You lose, unlucky")
    else:
        print("Error")

    exit()


setup()

```
