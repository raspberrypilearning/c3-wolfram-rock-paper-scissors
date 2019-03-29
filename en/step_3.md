## Set up the rules of the game

You now have three buttons, which update the play options for the `human` and the `robot` player. Now, you need to set up rules, so that you know whether the `human` or the `robot` has won a round.

These are the rules of Rock-Paper-Scissors: "Rock" wins against "Scissors", "Scissors" wins against "Paper", and "Paper" wins against "Rock". If both players play the same option, then it's a tie.

For each possible `human` play, we need to set up the conditions for a win, lose, and tie.

For example, if `human` chooses `rock`:

+ `human` will win if `robot` selects `scissors`
+ `human` will lose if `robot` selects `paper`
+ `human` and `robot` will tie if `robot` selects `rock`.

---task---

Create a new variable: `results`. At the moment, this variable should be equal to "Win". The variable will update with each play as you set up the rules.

```
results = "Win"
```
---/task---

The best way to check if one of multiple conditions is true, and return a specific output if the condition is true, is a `Which` statement. `Which` checks multiple conditions for whether they are `True`, and returns a specific output depending on which is the `True` condition. If the first condition is `True`, `Which` returns the output for that condition. If the second condition is `True`, `Which` returns the output for that condition, and so on, until `Which` has checked all conditions.

--- task ---
Add a `Which` statement to your `rock` button, which updates the `results` variable depending on if the player wins, ties, or loses.

The three conditions the `Which` statement will be checking are:

+ If `robot` is equal to `rock`
+ If `robot` is equal to `paper`
+ If `robot` is equal to `scissors`

The `Which` statement will then update `results` depending on which condition is true.

Remember to use a `;` to add a new task to the `Button`.

Your code should look like this:

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

You can update your buttons for `scissors` and `paper` in the same way.

---task---
Add a `Which` statement to your `scissors` button, and your `paper` button.

--- hints ---
--- hint ---
Look at the code for the `Which` statement you used for `rock` and make copies that include the rules for `paper` and `scissors`, as part of their buttons.
--- /hint ---
--- hint ---
The code for the updated buttons should look like this:

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
--- /hint ---
--- /hints ---
---/task---
