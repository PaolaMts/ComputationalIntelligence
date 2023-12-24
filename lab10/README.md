# LAB10 ASSIGNMENT

The purpose of the lab was to write a reinforcement learning algorithm able to device a tic-tac-toe player.

### APPROACH

`MyPlayer` is a player trained with a Q-learning algorithm. This player employs a Q-table initialized through the training function to determine the optimal move in a given game state. The Q-table is structured as a dictionary, with game states serving as keys, and each corresponding value consisting of another dictionary. The secondary dictionary associates possible moves for the respective state as keys, and their associated point values as values.
The training function involves playing a specified number of matches against another player. The player who starts each match is chosen randomly. If `MyPlayer` is the first to play, the initial state is an empty board; otherwise, it is the board state after the other player's move. For each move made by `MyPlayer`, the function accomplishes the following:
- reward of +5 if it wins;
- penalty of -10 if, immediately following this move, the opposing player secures a victory;
- reward of +0.1 in the other cases.

I used the Q-learning formula to compute the points for that move in that state.
During training, `MyPlayer` selects a random move 40% of the time or if the current state is not present in the Q-table, otherwise it selects the best move from the actual Q-table.

### RESULTS

I have considered two possible players as opponent for the training: 
- `RandomPlayer`: a player that generates only random moves.
- `RandomPlayerTwo`: a player that generates moves randomly, yet when presented with the opportunity to secure a victory, it executes the winning move.

Initially I trained `MyPlayer` against `RandomPlayer`, achieving a win rate of approximately 60%, then I used the `RandomPlayerTwo` for the training, enabling me to elevate my victories to 80% thanks to a faster convergence. 