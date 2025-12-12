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

# Ideas for Future Development

The number-based actions makes sense for this simple demo, but the possible action space could be huge! For example, we could allow the player to put items in inventory, stab other characters, or generally play in a more creative manner.
