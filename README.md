# WordleGame
A different version of the popular World game. Play as long as you want, with words of various lengths as you wish.

Clovis Hatungimana

hatungclovis@gmail.com

The Wordle game --> another version

For this project, I wrote a code that simulates the Wordle game but with new functionalities. Below are the things my code is expected to do:

At the start of the game, the code checks if the database (files that contain English words) exists in the main directory. If the files exist, it reads and extracts all the English words (370,105 words) and the common English words ((2,992 words). If not, the code goes on the internet and scrapes (fetches) all English words and the common English words and saves them as two separate files in the main directory where the code is running from.
The user chooses the difficulty level of the game:
Easy: the user gets 7 retries
Medium: the user gets 5 retries
Hard: the user gets 3 retries
The user also chooses the length (number of letters) of the word that will be the secret word that the user will try to guess.
After taking some user inputs, the code will randomly select (from the common English words) a word that the user will try to guess based on the retries they have. The code accesses all English words to check against the user’s input to make sure they are typing English words that exist (in the database).
The code compares the characters (letters) of the user-guessed word against those in the secret word. It returns a string of letters with coloured backgrounds:
Green: letters in the secret word that are in the right position
Yellow: letters in the secret word but in the wrong position
Black or White by default: letters not in the secret word
The user can choose to get hints: the code can reveal a letter that is in the secret word that the user’s guess does not contain.
The code then calculates the score at the end of the game (either the user ran out of the number of retries or they correctly guessed the secret word).
The code gives a quick statistical overview of the groupings of words in the common English words based on their first letters or their length (number of letters in the words). This part of the game has some plots too. This is meant to give the user a sense of what words (in terms of length and first letters) have higher chances of being randomly selected by my code.
Where the code can run: The code is self-contained and uses built-in Python libraries or libraries that easily come with most IDEs: e.g. Jupyter, Google Colaboratory, etc.

Modules: Below are the modules used for my code:

import os.path (used to check if the English words exist in the directory)
import random (for random selection of the secret word)
import pandas as pd (for providing some statistics on the common English words)
import requests (for accessing the internet to fetch English words)
from bs4 import BeautifulSoup (for readability of the information on the webpage).
Structure of the game: To make the game work as expected, I have leveraged a wide range of pythonic techniques and concepts such as iteration, string and list manipulation, lists, clones, recursion, dictionaries comprehensions, and exceptions. The whole game uses classes, self-contained functions, and the main code for putting it all together.

ScrapeCommonWords class: This class contains methods that access the website, read the information from the webpage, extract the information, clean and format the information, and save the common English words (2,992 words) in a text file (in a directory on which the Python code is running).
ScrapeAllWords class: This class does a similar job as the one above, except that this one looks for all English words (370,105 words) from the internet.
Library class: This class contains methods that read and get English words from the files stored in the directory. This makes it easier and way faster to make data queries as the game runs.
UserInput class: This class contains methods that take the user inputs (number of guesses, length of words, user guess) and checks these inputs against sets of constraints to avoid the program to crash.
WordMatching class checks the similarities between the guessed word and secret word's’ characters and colours backgrounds of the letters depending on how correct they are.
Self-contained functions: These functions complete/supplement the above classes by doing tasks such as generation of the secret word, displaying the hint letter, calculating the score, etc.
Miscellaneous functions: These functions deal with the data analysis side of the game. They provide information about the words (in terms of frequency) based on the length and first letters of the common words.
What’s next? So far, I am happy with the game. It runs smoothly and does the job as expected. However, I would love to incorporate the time constraint as the user plays the game. I haven’t figured out how to incorporate the timing of the game (this involves multiprocessing, which Python doesn’t naturally do because Python reads one line at a time. So, processing the time constraint while processing the user’s interactions with the game is not second nature for Python). I am also interested in making this game playable on mobile phones. I realized it would be a great way for me or any other person to grow and or sharpen their English vocabulary.
