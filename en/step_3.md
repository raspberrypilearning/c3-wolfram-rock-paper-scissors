## Setting up Game Rules

We now have three buttons, which update the play options for the `human` and the `robot` player. Now we need to set up rules, so that we can tell if the `human` or the `robot` wins that round.

Remember the rules of Rock, Paper, Scissors? "Rock" wins against "Scissors", "Scissors" wins against "Paper", and "Paper" wins against "Rock". If both players play the same option, then it's a tie.

For each possible `human` play, we need to set up the conditions for a win, lose, and tie.

For example, if `human` chooses `rock`:

+ `human` will win if `robot` randomly selects `scissors`
+ `human` will lose if `robot` selects `paper`
+ `human` and `robot` will tie if `robot` selects `rock`.

---task---

Create a new variable: `results`. At the moment, this variable should be equal to "Win". The variable will update with each play as we set up the rules.

```
results = "Win"
```
---/task---

The best way to check if one of multiple conditions is true, and return a specific output if the condition is true, is a `Which` statement.

Our `Which` statement will check a list of conditions. Each condition will have an action associated with it. If the condition is true, then the code will do that action. If the condition is not true, it will move on to the next condition in the `Which` statement, until it finds a condition which is true. In this case, one of the three conditions has to be true. 

--- task ---
Add a `Which` statement to your `rock` button, which updates the `results` variable depending on if the player wins, ties, or loses.

The three conditions the `Which` statement will be checking are:

+ If `robot` is equal to `rock`
+ If `robot` is equal to `paper`
+ If `robot` is equal to `scissors`

The `Which` statement will then update `results` depending on which condition is true.

Remember to use a `;` to add a new task to the `Button`.

```
Button[rock,
 human = rock;
 robot = RandomChoice[{rock, paper, scissors}];
 Which[
  robot == rock, results = "Tie",
  robot == paper, results = "Lose",
  robot == scissors, results = "Win"]
 ] 
 
 Dynamic[human]
 Dynamic[robot]
 Dynamic[results]
 ```
--- /task ---

You can update your `Button`s for `scissors` and `paper` in the same way.

---task---
Add a `Which` statement to your `scissors` `Button`, and your `paper` `Button`.

```
Button[paper,
 human = paper;
 robot = RandomChoice[{rock, paper, scissors}];
 Which[
  robot == paper, results = "Tie",
  robot == scissors, results = "Lose",
  robot == rock, results = "Win"]
 ] 
```
```
Button[scissors,
 human = scissors;
 robot = RandomChoice[{rock, paper, scissors}];
 Which[
  robot == scissors, results = "Tie",
  robot == rock, results = "Lose",
  robot == paper, results = "Win"]
 ] 
 ```
---/task---
