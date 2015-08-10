hubot-plusplus-hangman
==============

A coffee-script based chat add-on for playing Hangman. The script originated in the hubot-scripts repo. The hubot-scripts repo was later deprecated in favor of using stand alone node_modules for each hubot add-on. Seeing as the hangman.coffee script had not been touched or modified in several years and the originator of the script did not have a repo with anything related to hangman, I opted to port this and maintained the MIT license.

The script requires a Wordnik API key which you will need to request and setup as a CONFIG_VAR on Heroku. The API keys are free to request. http://developer.wordnik.com/

API
---

* `hubot hangman` - Display state of current game or start new game.
* `hubot hangman {x}` - Make a single character guess.
* `hubot hangman {word}` - Make a guess to solve the puzzle.

## Installation

Run the following command 

    $ npm install hubot-hangman

Then to make sure the dependencies are installed:

    $ npm install

To enable the script, add a `hubot-hangman` entry to the `external-scripts.json`
file (you may need to create this file).

    ["hubot-hangman"]
