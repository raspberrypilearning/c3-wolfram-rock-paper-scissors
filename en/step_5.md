## Cleaning your Code

You should now have five variables: `human`, `robot`, `results`, `humanScore`, and `robotScore`.

You should have three buttons, each representing one of the options `rock`, `paper`, and `scissors`. When the user presses one of the buttons, the `human` variable should update to match the button, the `robot` variable should update to a new random choice, and the `Which` statement should decide if the play is a "Win, "Lose" or "Tie", and assign a point to either the `humanScore` or the `robotScore`.

At the end of your code, you should have `Dynamic[variable_name]`, to show the newly updated value of the variable.

--- task ---

Check that your code does everything you need it to do.
You can supress the output of a line of code using the `;`, for example when you set up your variables, you don't want them to print their original output.

```
results = "tie";
robot = rock;
human = rock;
humanScore = 0;
robotScore = 0;

Button[rock,
 human = rock;
 robot = RandomChoice[{rock, paper, scissors}];
 results =
  Which[
   robot == rock, "Tie",
   robot == paper, robotScore += 1; "Lose",
   robot == scissors, humanScore += 1; "Win"]
 ]
Button[paper,
 human = paper;
 robot = RandomChoice[{rock, paper, scissors}];
 results =
  Which[
   robot == paper, "Tie",
    robot == scissors, robotScore += 1; "Lose",
    robot == rock, humanScore += 1; "Win"]
 ]
Button[scissors,
 human = scissors;
 robot = RandomChoice[{rock, paper, scissors}];
 results =
  Which[
   robot == scissors, "Tie",
   robot == rock, robotScore += 1; "Lose",
   robot == paper, humanScore += 1; "Win"]
 ]
Dynamic[human]
Dynamic[robot]
Dynamic[results]
Dynamic[humanScore]
Dynamic[robotScore]

```

--- /task ---

