# Set-covering with A* Algorithm assignment
This is my version of set-covering problem solved with the A* algorithm.
I used the code developed by the professor as base for my solution but I used a different heuristic and some ideas to increment the performances.
I created an heuristic based on the number of best possible untaken sets necessary to cover all the state. The best untaken sets are the not taken sets which have less overlapping and less distance to the goal. Then I used this heuristic with the number of taken sets in the state as cost in the priority queue. I also implemented some preprocessings step: I order the SETS with the number of false (their distance from the goal) and I find the sets which are the only ones to cover some positions with True to force the state to not consider solutions without these.


Code developed jointly with [LeoDardanello](https://github.com/LeoDardanello)
