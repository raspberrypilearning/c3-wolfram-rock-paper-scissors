## Create an interface

If you want to, you can remove the frames on the buttons. The button will do the same thing, but it will not have a frame around it.

```Button[rock, Appearance -> None]```

![rock symbol](images/rock.png)

--- task ---

Add `Appearance -> None` to each `Button`.

For example, the code for the `rock` button should now be:

```
Button[rock,
 human = rock;
 robot = RandomChoice[{rock, paper, scissors}];
 results =
  Which[
   robot == rock, "Tie",
   robot == paper, robotScore += 1; "Lose",
   robot == scissors, humanScore += 1; "Win"], Appearance -> None
 ]
 
 ```
 Do this for all three of your buttons.
 
 --- /task ---

You can also use `Grid` to make a nice interface.

Here is an example of `Grid`:

```
Grid[{{"hello", "goodbye"}, {"bye", "hi"}}]
```

![basicgrid](images/basicgrid.png)

As you can see, a `Grid` is a list of lists, where each list becomes a row in the `Grid`.

You can use `SpanFromLeft` to span elements across the grid, like in the example below:

```
Grid[{{"hello", SpanFromLeft}, {"bye", "hi"}}]
```
![span from left](images/basicgridspan.png)

You can use `Frame -> True` to draw a frame around the outside, and you can use `FrameStyle -> Thick` to make the frame thick.

```
Grid[{{"hello", SpanFromLeft}, {"bye", "hi"}}, Frame -> True, FrameStyle -> Thick]
```
![frame grid](images/basicgridframe.png)

You can also use `Spacings` to add extra space inside the `Grid`.`Spacings` takes two dimensions, horizontal and vertical, in a list. The horizontal number makes each column in the grid a certain width. The vertical number makes each row in the grid a certain height.

```
Grid[{{"hello", SpanFromLeft}, {"bye", "hi"}}, Frame -> True, 
 FrameStyle -> Thick, Spacings -> {4, 2}]
 ```
![spacings frame grid](images/basicgridspacing.png)
 
 
You will now make two `Grid`s. The first `Grid` will have:
+ a title
+ the three buttons, `rock`, `paper`, and `scissors`, for the user to choose their move
+ the `human` choice, the result, and the `robot` choice

The second `Grid` will have:
+ the `humanScore`
+ the `robotScore`
 
 ---task ---
 
 Build a `Grid` with three rows.
 
 + The first row should contain a title. You can use `Style[Text["title"]]` to customise the title. The second and third row have three elements, so you can use `SpanFromLeft` twice to centre the title.
 + The second row should be the three buttons.
 + The third row should be `Dynamic[human]`, `Dynamic[result]`, and `Dynamic[robot]`.
 
 Use `Frame -> True` to add a `Frame`, and use `FrameStyle -> Thick` to make the `Frame` thick.
 Use `Spacings` to add extra space inside the `Grid`. This `Grid` should have `Spacings -> {2, 1.5}`, so that it matches the second `Grid`.
 
 ```
 Grid[{
  {Style[Text["Your Play!"], 23], SpanFromLeft, SpanFromLeft},
  {Button[rock,
    human = rock;
    robot = RandomChoice[{rock, paper, scissors}];
    results =
     Which[
      robot == rock, "Tie",
      robot == paper, robotScore += 1; "Lose",
      robot == scissors, humanScore += 1; "Win"], Appearance -> None
    ],
   Button[paper,
    human = paper;
    robot = RandomChoice[{rock, paper, scissors}];
    results =
     Which[
      robot == paper, "Tie",
       robot == scissors, robotScore += 1; "Lose",
       robot == rock, humanScore += 1; "Win"], Appearance -> None
    ],
   Button[scissors,
    human = scissors;
    robot = RandomChoice[{rock, paper, scissors}];
    results =
     Which[
      robot == scissors, "Tie",
      robot == rock, robotScore += 1; "Lose",
      robot == paper, humanScore += 1; "Win"], Appearance -> None
    ]},
  {Dynamic[human], Dynamic[Style[Text[results], 20]], Dynamic[robot]}
  }, Frame -> True, FrameStyle -> Thick, Spacings -> {2, 1.5}]
  ```
  
![grid with buttons and play choices](images/gridone.png)
 
 ---/task---
 
 --- task---
 Build a second `Grid` with two rows to show the scores.
 
 + The first row should contain the text "Your Score", and the `humanScore`
 + The second row should contain the text "Robot Score", and the `robotScore`
 
 Use `Frame -> True` to add a `Frame`, and use `FrameStyle -> Thick` to make the `Frame` thick.
 Use `Spacings` to add extra space inside the `Grid`. This `Grid` should have `Spacings -> {3.85, 1.5}`, so that it matches the first `Grid`. The `Spacings` for this `Grid` are larger because the items in this `Grid` are smaller.

--- hints ---
--- hint ---
The code for the second `Grid` is as follows:
 ```
Grid[{
  {Style[Text["Your Score:"], 20],Dynamic[Style[Text[humanScore], 20]]},
  {Style[Text["Robot Score:"], 20], Dynamic[Style[Text[robotScore], 20]]}
  }, Frame -> True, FrameStyle -> Thick, Spacings -> {3.85, 1.5}]
  
  ```
--- /hint ---
--- /hints ---

 ---/task---
 
Now you have a play interface, and a results section - your game works! Play the game, and see if you can beat the computer!
 
 
