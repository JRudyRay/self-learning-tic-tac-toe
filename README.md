# self-learning-tic-tac-toe
This is an unbeatable self learning Tic-Tac-Toe AI game written in python for demonstration of reinforcement learning to non-techies. The AI agent here learns to play tic-tac-toe from thousands of games played by it with itself.

####Approach:

1. First generate all the possible states of the game and possible moves for each of the states. This gives a huge number of states (more than 300000 states)
2. Since tic-tac-toe game board is symmetric so many of states are actually similar states if rotate or taken mirror image of the board. So we remove all the duplicate states that we generated. After this we are left with only around 900 states.
3. Now, the AI agent start playing games (initially with random moves) with itself. after every game, it updates all the moves corresponding to the visited states as follows:
    * If it wins the game then it adds the corresponding move in the possible moves for that states. Shorter the games more will be the addition of the moves. Also, closer the the step to the winning step of the game more will be the adding of the winning moves to the state.
    * If it loses the game, it deletes the corresponding moves that it has played from the states. Shorter the games more will be the deleting of the moves. Also, closer the the step to the winning step of the game more will be the deletion of the winning moves to the state.
4. Now, after thousands of self games, the states have more of the winning moves than the losing moves.
5. The system saves all the states and corresponding moves in a *experience.dat* file

Before playing with human player, the system reads the *experience.dat* file and loads the sates and corresponding moves. Now for every state in the game, the agent plays the maximum occurring moves for that state.
