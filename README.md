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

## Release Notes

### 1.0.0
 
* Confirmed hubot-hangman script is not available as NPM package
* Migrated hubot-hangman script into NPM package format
* Changed unguessed character identifier from `_` to `-` to improve client formatting
* Published npmjs.com

### 1.0.1

* Updated tags for npmjs.com search

### 1.1.0

* Bugfix: Changed unguessed character identifier from `-` to `?`. Some words in the WORDNIK api include dashes, this can confuse the game leaving you stuck in an eternal loop. Changing the character to a question mark to prevent this from happening in the future. `*`'s and `_`'s have been avoided due to markdown formatting used by many chat client apps.

