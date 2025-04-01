### Impermanent retaliation

#### State management
My algorithm operates in 2 states: cooperation and retaliation.

Cooperation is the default mode, in this state my algorithm always cooperates.

---

Retaliation is triggered when my opponent defects. Since there is no way to have persistent memory besides the history of moves, my last choice serves as indicator of state:
0 = cooperated -> cooperation mode
1 = defected   -> retaliation mode

To have a chance to break out of retaliation loops, I'va also added a small chance to forgive the opponent while retaliating.

---

#### Pseudo random number generator
To obtain pseudo random numbers I used a linear congruential generator with the history as seed (converted from binary to decimal).

--- 

#### Round 3 modification

For round 3 I had to addapt the implementation of the algorithm to the new enviroment.
First, I had to get the histories from the dicts and write an algorithm to find the next opponent.
This algorithm is as simple as it is efficient: find the opponet with the least ammount of defections.

To simulate the last round betrayal from the original algorithm I exploited the condition that any player can only play with a certain opponent a maximum of 200 times, meaning that I have the number of maximum round. When it's the 200th round, I defect.
