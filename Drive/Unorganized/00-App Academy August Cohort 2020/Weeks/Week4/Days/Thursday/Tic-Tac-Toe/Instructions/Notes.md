

Rules & Considerations:


The first click results in an "X". After that, the symbols "O" and "X" alternate with each click per the rules of tic-tac-toe.

When the player clicks an empty square, then it is filled with that player's symbol.


When the player clicks a square that already contains a symbol, the game does nothing.

 get around to checking if one of the players won or if there is a tie. 
 
 Plan ahead for how you track the grid clicks because you'll need to know the "value" of each square to calculate wins.

NEW GAME BUTTON:
-Accessibility
    *Enabled only when game is won or tied.
-Actions
    * clear game status
    * clear header
    * clear board
    * next click is "X"
    * disable "New Game" button

GIVE UP BUTTON:
-Accessibility
    *Enabled only when game is ongoing.
-Action
    *Winner = other player (if "X" gives up, "O" wins, vice-versa)
    *Shows winner status as won by the "other" player
    *disable "Give Up" button
    *enable "New Game" button

SAVE GAME:
-When game is refreshed, game status is not affected.





## -------------------------------------------------------------------------------- ##
Brain Storm:










Game Plan:
1       embed images
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100