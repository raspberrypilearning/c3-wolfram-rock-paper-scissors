## Keeping Score

It's not a very entertaining game unless we keep score. Each time `human` wins (so the `results` variable is set to "Win"), we add 1 to the `human` score, and each time `robot` wins, (so the `results` variable is set to "Lose") we add 1 to the `robot` score.

---task---
Set up two more variables: `humanScore`, and `robotScore`.

They should start at `0`.

```
humanScore = 0
robotScore = 0

```
---/task---

We can add to the score using `+=`.

The `Which` statement we created in the previous step currently sets `results` to "Win", "Lose", or "Tie". We can use the `;` to add multiple tasks in the `Which` statement if that condition is met.

---task---
In each `Which` statement, use a `;` to add a point to `humanScore` if `results == "Win"`, and add a point to `robotScore` if `reslts == lose`.

You will need to put the `humanScore` or `robotScore` update variable before the `results` update variable, so that the `results` variable will still update properly.

For example, the `Which` statement for `rock` should now be:

```
Which[
 robot == rock, "Tie",
 robot == paper, robotScore += 1; "Lose",
 robot == scissors, humanScore += 1; "Win"] 
 ```
---/task---