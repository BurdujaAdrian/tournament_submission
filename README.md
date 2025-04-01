### Impermanent retaliation

#### State management
My algorithm operates in 2 states: cooperation and retaliation.

Cooperation is the default mode, in this state my algorithm always cooperates.

Retaliation is triggered when my opponent defects. Since there is no way to have persistent memory besides the history of moves, my last choice serves as indicator of state:
0 = cooperated -> cooperation mode
1 = defected   -> retaliation mode

To have a chance to break out of retaliation loops, I'va also added a small chance to forgive the opponent while retaliating.


#### Pseudo random number generator
To obtain pseudo random numbers I used a linear congruential generator with the history as seed (converted from binary to decimal).
