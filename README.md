# Description

Welcome to politics! Your goal is to maintain your power by balancing the interests of the different factions.

If your Money, the Public's Opinion of you, Rich People's Opinion of you, or your Health fall to 0, then you lose!

This is a game written in Professor Ian Horswill's [STEP](https://ianhorswill.github.io/DPGD/The_Step_language.html) language.

# How to Play

Open the game with StepRepl.
Start the game with `look`.

There are hidden numbers for Money, Public Opinion, Rich People's Opinion, and Health. If any of these drop to zero due to your actions, you lose!

Pick numbered actions to respond to situations.
`look` prints some of the starting text.
`poll money`, `poll rich`, `poll public`, and `poll health` give you estimates for those quantities. `poll rich` and `poll public` are random, qualitative, and cost you Money.

# How it uses Declarative Programming

STEP is an inherently declarative language. Rather than `if` statements, there are multiple methods, and if one fails STEP tries the other. This made writing all of the SituationActions (in `Situations.step`) much easier than it otherwise would have been. I could easily describe what declarative facts change when an action is taken, for example which actions increment the turn counter.

# New Code for This Project

## New files

`GameFlow.step`: Initializes global variables, stats, and has a function for printing the current situation's text.

`Situations.step`: Has code for changing the Situation and responding to situations with actions.

`Losing.step`: Has a method for checking if you lost and printing accordingly.

`TurnTexts.csv`: A big, easily-extendable `csv` of situations a player can find themselves in. Actions the player can take are defined separately, in `Situations.step`.

## Edited Files:

`Parser.step`: changed how the game loop works. It now first checks if the player lost, then it prints the user's options and allow the user to input numbers as actions.

`Actions.step`: Added an ActionDescription method for each action so the user can be informed of their actions. Added the new action `poll` which gives the user an estimate of their stats. `OpinionText` translates numerical values into qualitative descriptions.

`Ontology.step`: Some tagged methods and objects.

`World.step`: Defined Campaign and Debate as settings (though there is no implemented way to get to the Debate).

# Ideas for Future Development

The number-based actions makes sense for this simple demo, but the possible action space could be huge! For example, we could allow the player to put items in inventory, stab other characters, or generally play in a more creative manner. It is a shame that `eat baby` doesn't work.

# Credits

This game was built on top of Professor Horswill's TextAdventure example game.
Thank you to Mom for suggesting the Keynote Speaker Situation and Dad for playtesting :)

# Todo:

[SetSituation] should be associated with each SituationAction. Right now, it always changes unless there `MyTurn` is associated with a specific Situation. `ParseAction [?word]`.
