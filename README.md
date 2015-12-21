# Connect-Four
INTRODUCTION:
In this assignment, I have implemented various game search algorithms for "Connect Four" game to make the game run more efficiently. 
The default game option is:

run_game(human_player, basic_player)

One need to uncomment lines to run other player games, like to play new player vs basic player,
please uncomment line number 164 in lab3.py

run_game(new_player, basic_player)

Similarly all other options for play are given in lab3.py.

1.  Minimax Search Algorithm:
Minimax search algorithm has been implemented for Connect Four game. For
each move other player makes, one with maximum value is used by minimax player.
This procedure is repeated until the game is over (win, lose or tie) or the tree depth has been explored.

Depending upon the basic evaluation function or new evaluation function we are calculating the nodes expanded
by our minimax search algorithm and time has been calculated of the game.


2.  Better Evaluation Function:
Basic computer player was using simple basic evaluation function to check its chance of winning or losing. 
I have written a new player which is much better than basic player and to calculate its winning or losing chance,
it uses new_evaluate function which calculates winning position by checking for every cell of board in a current 
state where it can make continuous four X’s in all possible  directions  and  it  also  checks  for  every  cell
of  the  board  for  the opponents winning chance (which will be losing chance for it). In our evaluation function
we are also checking the position whether it is in middle of board as there is maximum chance of winning there.

  
3.  Alpha Beta Pruning:
In our minimax search algorithm  it was calculating the  winning or losing chance of it by expanding the nodes and
using the maximum value of evaluation function to  run  its  move.   But  the  major  drawback of  minimax  algorithm
is  that  it  will expand all the nodes and  which will increase the time to make  the next move  of the  computer
player also the  number of nodes expanded will be  very much.  In order    to   make    the    minimax   search 
algorithm   more    efficient,   we   have implemented alpha beta  pruning algorithm. So to increase efficiency,
In this algorithm, we  will not  expand the  nodes which have  less value than  maximum value  returned by other
nodes at  the  same level.  These nodes will get  pruned and the efficiency of our search algorithm increase many fold.

 
4.  Connect-K Problem:
We have  generalized the connect-four game to connect-k game. Now, it can  take the k value (e.g.  3, 4, 5…) and 
instead of checking for 4 continuous tokens, it will check  for k continuous tokens.
E.g. Connect-5 game: K=5
run_game(alphabeta_player, basic_player, ConnectFourBoard(K))


5.  Longest Streak to Win:
In the longest streak to win the game will not stop at any fixed number k. Now the game will stop  after 20 rounds
i.e. each player will play 10 moves and  after 20 rounds  the  player  with  longest  streak  in  any  direction 
horizontal,  vertical  or diagonal  is  the  winner.  And  if  both  players  have   same maximum  number of continuous
tokens then the game is tie.

Note: Please uncomment the lines from 535 to 546 in connectfour.py to play longest streak to win game.

