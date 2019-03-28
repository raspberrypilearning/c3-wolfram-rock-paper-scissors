## Set up scorekeeping

The game is more fun if you keep score. If you follow these steps, each time `human` wins (so the `results` variable is set to "Win"), the code will add 1 to the `human` score, and each time `robot` wins, (so the `results` variable is set to "Lose") the code will add 1 to the `robot` score.

---task---
Set up two more variables: `humanScore`, and `robotScore`.

They should start at `0`:

```
humanScore = 0
robotScore = 0

```
---/task---

You can use `+=` to add to the score.

The `Which` statement you created in the previous step currently sets `results` to "Win", "Lose", or "Tie". You can use the `;` to add multiple actions in the `Which` statement if a condition is met.

---task---
In each `Which` statement, use a `;` to add 1 point to `humanScore` if `results == "Win"`, and to add 1 point to `robotScore` if `results == "Lose"`.

You need to put the `humanScore` or `robotScore` update variable before the `results` update variable, so that the `results` variable will still update properly.

For example, the `Which` statement for `rock` should now be:

```
Which[
 robot == rock, "Tie",
 robot == paper, robotScore += 1; "Lose",
 robot == scissors, humanScore += 1; "Win"] 
 ```

Update the `paper` and `scissors` statements to adjust the score as it changes.
---/task---
