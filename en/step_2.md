## Building Blocks of the Game

--- task ---
If you have never used the Wolfram Language before, follow this guide to get started and learn to use the tool. Look at the sections **Starting Mathematica** and **Programming in Mathematica**.
--- /task ---

In Rock-Paper-Scissors, two players (in this case, the user and the computer) each select one of the three play options: "Rock", "Paper", or "Scissors".

"Rock" wins against "Scissors", "Scissors" wins against "Paper", and "Paper" wins against "Rock". If both players play the same option, then it's a tie.

First, you will create three buttons for the user to press in order to choose their play option. You will set the computer's play option to be a random choice between the three options, each time the user chooses their option.

---task---
Copy and paste these images into your notebook, and give them the variable names `rock`, `paper`, and `scissors`.

![rock symbol](images/rock.png)
![paper symbol](images/paper.png)
![scissors symbol](images/scissors.png)

Your code should look like this:

![imported images](images/variables.png)
---/task---

The computer needs to randomly select one of the three options each time it plays. You can use `RandomChoice` to set this up. `RandomChoice` takes one argument: a list of the possible choices.

---task---
Create a variable, `robot`, which is a random choice of the three options.

```
robot = RandomChoice[{rock, paper, scissors}]
```

Run this code a few times to check that you get a random result each time.
---/task---

---task---
Create a variable, `human`, which at the moment will be `rock`, but will be updated to be the user's choice later.

```
human = rock
```
---/task---

The user needs to be able to use buttons to select their play option.

Each time the user presses the button, the variable `human` needs to update with their choice, and the variable `robot` needs to update with another random selection.

---task---
Use the code below to create buttons for `rock`, `paper`, and `scissors`. Each button should update the `human` variable to the value of the button, and should update the `robot` variable to another random selection.

You can make a button do multiple actions by separating the actions with a `;`.

```
Button[rock, human = rock; robot = RandomChoice[{rock, paper, scissors}]]
Button[paper, human = paper; robot = RandomChoice[{rock, paper, scissors}]]
Button[scissors, human = scissors; robot = RandomChoice[{rock, paper, scissors}]]
```

--- /task ---

You will notice that when you press the button, there is no output. This is because the variables `human` and `robot` need to be evaluated again each time you press the button in order to show the result. It would be better to have the new output show automatically when you press the button.

You can use `Dynamic` to do this. `Dynamic` displays the updated value, so each time the user reevaluates the code by pressing the button, `Dynamic` will update to the new value.

---task---
Add `Dynamic` results for the variables `human` and `robot` to show the new outputs each time the user presses the buttons.

```
Button[rock, human = rock; robot = RandomChoice[{rock, paper, scissors}]]
Button[paper, human = paper; robot = RandomChoice[{rock, paper, scissors}]]
Button[scissors, human = scissors; robot = RandomChoice[{rock, paper, scissors}]]
Dynamic[human]
Dynamic[robot]
```
---/task---
