Play Hangman using Wordnik and Hubot!

[![NPM](https://nodei.co/npm/hubot-hangman.png?downloads=true&&downloadRank=true&stars=true)](https://nodei.co/npm/hubot-hangman/) [![NPM](https://nodei.co/npm-dl/hubot-hangman.png?months=3&height=3)](https://nodei.co/npm/hubot-hangman/)

A coffee-script based chat add-on for playing Hangman. The script originated in the hubot-scripts repo. The hubot-scripts repo was later deprecated in favor of using stand alone node_modules for each hubot add-on. Seeing as the hangman.coffee script had not been touched or modified in several years and the originator of the script did not have a repo with anything related to hangman, I opted to port this and keep it maintained with the MIT license.

Please feel free to leave any feedback on the github project.

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

### 1.3.1

* Added `'` as a default guess. Now spaces, dashes, and apostrophes will not require guessing and will be shown in the word printout.
* If you notice any other special characters causing problems please create an issue on the github project for me to address. 

### 1.3.0

* Fixed: [Issue #1](https://github.com/kwandrews7/hubot-hangman/issues/1)
* Thanks to cpradio for finding another special character bug.
* Updated the special characters to be defined as an array that we can expand in the future if necessary.
* Now both spaces and dashes will be shown in the word. 
* Example: `This-is a-game` would now be shown as `? ? ? ? - ? ?   ? - ? ? ? ?`.
* Happy guessing!


### 1.2.1

* 1.2.0 bug fix. 
* Dashes were considered guessed, but weren't shown as guessed characters.
* Now dashes are shown in word. `The 8 letter word is: ? ? ? ? - ? ? ?`

### 1.2.0

* Added `-` as a default guess. Many users don't expect a dash to appear in the word and hence never guess special characters. 
* Dash will be given for free.
* If you guess a `-` it will be treated as a previously guessed letter and will not count against you.
* If the word contains a dash, it will be shown automatically.

### 1.1.0

* Bugfix: Changed unguessed character identifier from `-` to `?`. Some words in the WORDNIK api include dashes, this can confuse the game leaving you stuck in an eternal loop. Changing the character to a question mark to prevent this from happening in the future. `*`'s and `_`'s have been avoided due to markdown formatting used by many chat client apps.

### 1.0.1

* Updated tags for npmjs.com search

### 1.0.0
 
* Confirmed hubot-hangman script is not available as NPM package
* Migrated hubot-hangman script into NPM package format
* Changed unguessed character identifier from `_` to `-` to improve client formatting
* Published npmjs.com
