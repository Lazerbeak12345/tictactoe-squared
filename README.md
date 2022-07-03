# tictactoe-squared
Hopefully an actually viable tictactoe game but in svelte this time....

## Gameplay

Imagine a standard game of Tic-Tac-Toe.
Good.

Now I'm going to assume you know of Ultimate Tic-Tac-Toe. Imagine one such board.

In each square of the Ultimate Tic-Tac-Toe board, place a standard Tic-Tac-Toe
board.
That is to say, **this is Tic-Tac-Toe inside of Tic-Tac-Toe inside of
Tic-Tac-Toe.**

Add a bit of rule balancing, and there you go.

I've found it to be a simmilar level of complexity to play as chess.

### Rules

Keep track of the last two moves by both players.

Just as in Ultimate Tic-Tac-Toe, when you move within your limited area, the
square you selected determines a limitation to the other player.
Unlike Ultimate, it also directly determines a limitation to your next move.

- The box selected in the innermost determines which square within a middle
grid (IE: which innermost grid) your opponent may place within in their next
turn.
- The box selected in your last turn determines which middle grid (IE which
square within the topmost grid) you will be limited to in this turn.
- When you win a board of Tic-Tac-Toe, you may mark the whole board with your
symbol, and consider the board won.
- If a player is limited to place in a board that has been won, or is completly
full, then they may place everywhere within the next region upwards.
  - Ex: An innermost board has been won or filled, and you are restricted to
  play only within that board. You may now play anwhere within the holding
  middle board.
  - Ex: A middle board has been won or filled, and you are restricted to this
  board. You may now place _anywhere in the entire game_.

## Structure

Uses parcel to build a svelte project.
This allows me to use the best of both toolkits.
No bugs so far 😈.

> ![
> Anakin: Is it possible to learn this power?
> Palpatine: Not from a Jedi.
> ](https://i.kym-cdn.com/photos/images/original/001/491/587/0c5.png)
>
> \- Anakin and Chancellor Palpatine in _Star Wars, Revenge of the Sith_
>
> Script source imsdb.com, image source KnowYourMeme

Parcel is told how to ~~ab~~use a svelte project via
`parcel-transformer-svelte`.
