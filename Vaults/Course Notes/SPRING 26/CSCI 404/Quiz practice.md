## **Question 1** (0.5 points)

Which recurrence has the correct form for applying the master method?

Question 1 options:

|     |                                |
| --- | ------------------------------ |
|     | T(n) = T(n-1) + Θ(n)           |
| x   | T(n) = 4T(n/2) + Θ(n²)         |
|     | T(n) = T(n/3) + T(2n/3) + Θ(n) |
|     | T(n) = 2T(n/2) + Θ(n/lg n)     |
## **Question 2** (0.5 points)

For the recurrence T(n) = 8T(n/2) + Θ(n³) what are the values of a and b?

Question 2 options:

|     |             |
| --- | ----------- |
|     | a = 2 b = 8 |
|     | a = 8 b = 3 |
| x   | a = 8 b = 2 |
|     | a = 3 b = 2 |
## **Question 3** (0.5 points)


For T(n) = 9T(n/3) + Θ(n²) what is the watershed function n^(log_b a)?

Question 3 options:

|     |            |
| --- | ---------- |
|     | n          |
| x   | n²         |
|     | n³         |
|     | n^(log₉ 3) |

## **Question 4** (0.5 points)

 Which recurrence uses Case 1 of the master method?

Question 4 options:

|     |                        |
| --- | ---------------------- |
| x   | T(n) = 8T(n/2) + Θ(n²) |
|     | T(n) = 2T(n/2) + Θ(n)  |
|     | T(n) = 4T(n/2) + Θ(n³) |
|     | T(n) = 9T(n/3) + Θ(n²) |

## **Question 5** (0.5 points)

Which statement correctly describes when Case 2 of the master method applies?

Question 5 options:

|     |                                                                 |
| --- | --------------------------------------------------------------- |
|     | When f(n) is polynomially smaller than n^(log_b a)              |
| x   | When f(n) = Θ(n^(log_b a) lg^k n) for k ≥ 0                     |
|     | When f(n) is polynomially larger than n^(log_b a)               |
|     | When the recurrence doesn't have the form T(n) = aT(n/b) + f(n) |

## **Question 6** (0.5 points)

For T(n) = 4T(n/2) + Θ(n²) which case applies and what is the solution?

Question 6 options:

|     |                             |
| --- | --------------------------- |
|     | Case 1: T(n) = Θ(n²)        |
| x   | Case 2: T(n) = Θ(n² lg n)   |
|     | Case 3: T(n) = Θ(n²)        |
|     | Master method doesn't apply |

## **Question 7** (0.5 points)
For Case 3 of the master method to apply which conditions must be met?

Question 7 options:

|     |                                                           |
| --- | --------------------------------------------------------- |
|     | Only f(n) must be polynomially larger than n^(log_b a)    |
|     | Only the regularity condition af(n/b) ≤ cf(n) must hold   |
| x   | Both polynomial growth AND regularity condition must hold |
|     | Neither condition is required for Case 3                  |

## **Question 8** (0.5 points)
What is the solution to T(n) = 8T(n/4) + Θ(n)?

Question 8 options:

|     |           |
| --- | --------- |
|     | Θ(n)      |
|     | Θ(n lg n) |
| x   | Θ(n^1.5)  |
|     | Θ(n²)     |

## **Question 9** (0.5 points)

What is the solution to T(n) = 2T(n/2) + Θ(n²)?

Question 9 options:

|     |            |
| --- | ---------- |
|     | Θ(n)       |
|     | Θ(n lg n)  |
| x   | Θ(n²)      |
|     | Θ(n² lg n) |
## **Question 10** (0.5 points)


The recurrence for merge sort is T(n) = 2T(n/2) + Θ(n). What is its solution?

Question 10 options:

|     |            |
| --- | ---------- |
|     | Θ(n)       |
| x   | Θ(n lg n)  |
|     | Θ(n²)      |
|     | Θ(n² lg n) |
## **Question 11** (0.5 points)

What does it mean for f(n) to be polynomially smaller than n^(log_b a) in Case 1?

Question 11 options:

|     |                                                   |
| --- | ------------------------------------------------- |
|     | f(n) must be any amount smaller                   |
| x   | f(n) = O(n^(log_b a - ε)) for some constant ε > 0 |
|     | f(n) must be logarithmically smaller              |
|     | f(n) must grow slower by any factor               |

## **Question 12** (0.5 points)
Why doesn't the master method apply to T(n) = 2T(n/2) + Θ(n/lg n)?

Question 12 options:

|     |                                                         |
| --- | ------------------------------------------------------- |
|     | Because it doesn't have the form T(n) = aT(n/b) + f(n)  |
|     | Because a and b are not constants                       |
| x   | Because f(n) falls in the gap between Case 1 and Case 2 |
|     | Because the regularity condition fails                  |

## **Question 13** (0.5 points)
The simple recursive matrix multiplication has recurrence T(n) = 8T(n/2) + Θ(1). What is its solution?

Question 13 options:

|     |            |
| --- | ---------- |
|     | Θ(n²)      |
|     | Θ(n² lg n) |
| x   | Θ(n³)      |
|     | Θ(n⁴)      |

## **Question 14** (0.5 points)
Strassen's algorithm has recurrence T(n) = 7T(n/2) + Θ(n²). What is its solution?

Question 14 options:

|     |             |
| --- | ----------- |
|     | Θ(n²)       |
|     | Θ(n² lg n)  |
| x   | Θ(n^(lg 7)) |
|     | Θ(n³)       |

## **Question 15** (0.5 points)
For T(n) = 4T(n/2) + Θ(n² lg³ n) which case applies?

Question 15 options:

|     |                             |
| --- | --------------------------- |
|     | Case 1                      |
| x   | Case 2 with k=3             |
|     | Case 3                      |
|     | Master method doesn't apply |

## **Question 16** (0.5 points)
For T(n) = 2T(n/2) + Θ(n²) does the regularity condition hold?

Question 16 options:

|     |                                           |
| --- | ----------------------------------------- |
| x   | Yes: 2(n/2)² = n²/2 ≤ cn² for c = 1/2 < 1 |
|     | No: the condition fails                   |
|     | Not needed since this is Case 1           |
|     | Cannot determine without more information |

## **Question 17** (0.5 points)
Can the master method solve T(n) = T(n/3) + T(2n/3) + Θ(n)?

Question 17 options:

|     |                                             |
| --- | ------------------------------------------- |
|     | Yes using Case 2                            |
|     | Yes using Case 3                            |
| x   | No because subproblems have different sizes |
|     | Yes using Akra-Bazzi method extension       |

## **Question 18** (0.5 points)
Binary search has recurrence T(n) = T(n/2) + Θ(1). What is its solution?

Question 18 options:

|     |           |
| --- | --------- |
|     | Θ(1)      |
| x   | Θ(lg n)   |
|     | Θ(n)      |
|     | Θ(n lg n) |

## **Question 19** (0.5 points)
A 3-way merge sort has recurrence T(n) = 3T(n/3) + Θ(n). What is its solution?

Question 19 options:

|     |             |
| --- | ----------- |
|     | Θ(n)        |
| x   | Θ(n lg n)   |
|     | Θ(n²)       |
|     | Θ(n log₃ n) |

## **Question 20** (0.5 points)
For T(n) = 27T(n/3) + Θ(n²) what is the solution?

Question 20 options:

|     |            |
| --- | ---------- |
|     | Θ(n²)      |
|     | Θ(n² lg n) |
| x   | Θ(n³)      |
|     | Θ(n⁴)      |
## Quiz 2
|   |   |   |
|---|---|---|
|**Question 1**||0.5 / 0.5 points|

For T(n) = 4T(n/2) + cn what is the height of the recursion tree?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n/2|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|lg n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n lg n|

|                                                                                                                                      |     |
| ------------------------------------------------------------------------------------------------------------------------------------ | --- |
| Hide question 1 feedback                                                                                                             |     |
|                                                                                                                                      |     |
| ## Feedback<br><br>The height is determined by how many times we divide by 2 until reaching the base case. n/2^h = 1 means h = lg n. |     |

| **Question 2** |     | 0.5 / 0.5 points |
| -------------- | --- | ---------------- |

For T(n) = T(n/3) + T(2n/3) + Θ(n) what can we say about the recursion tree?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It's perfectly balanced|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|It's unbalanced with different path lengths|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|All paths have the same length|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It has no leaves|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Different subproblem sizes (n/3 and 2n/3) create an unbalanced tree. The leftmost path has length log₃ n while the rightmost has length log₃/₂ n.|   |

|   |   |   |
|---|---|---|
|**Question 3**||0.5 / 0.5 points|

Which technique helps generate good guesses for the substitution method?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Always guess O(n²) first|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Draw a recursion tree to see the pattern|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Use trial and error with no strategy|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Guess the same as the driving function|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>Drawing a recursion tree helps you visualize costs at each level and see patterns that suggest the asymptotic solution. This guides your guess for substitution.|   |

|   |   |   |
|---|---|---|
|**Question 4**||0.5 / 0.5 points|

What is the primary purpose of drawing a recursion tree?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|To visualize the structure and generate a good guess for the solution|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|To replace the need for mathematical proof|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|To calculate exact constants|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|To avoid using the master method|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>Recursion trees help build intuition and generate good guesses. You typically verify the guess with substitution or use master method if applicable.|   |

|   |   |   |
|---|---|---|
|**Question 5**||0.5 / 0.5 points|

For T(n) = 2T(n/2) + 3n, if we guess T(n) ≤ cn lg n, what do we substitute for T(n/2)?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|c(n/2)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|c(n/2) lg(n/2)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|cn lg n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|(1/2)cn lg n|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>The inductive hypothesis says T(m) ≤ cm lg m for all m < n. So for m = n/2 we substitute T(n/2) ≤ c(n/2) lg(n/2).|   |

|   |   |   |
|---|---|---|
|**Question 6**||0.5 / 0.5 points|

For T(n) = 3T(n/4) + cn², the level costs form cn², 3cn²/16, 9cn²/256,... What type of series is this?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Arithmetic series|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Geometric series with ratio 3/16|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Harmonic series|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Logarithmic series|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>Each level's cost is (3/16) times the previous level's cost forming a geometric series with ratio r = 3/16 < 1.|   |

|   |   |   |
|---|---|---|
|**Question 7**||0.5 / 0.5 points|

When should you subtract a lower-order term in the substitution method?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Always as a first step|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Never; it's incorrect to do so|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|When your initial guess doesn't quite work due to an additive constant|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Only for Case 3 of the master method|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>If your guess T(n) ≤ cn doesn't work because of an additive constant try T(n) ≤ cn - d. When you have multiple recursive calls subtracting the lower-order term multiple times can make the inequality work.|   |

|   |   |   |
|---|---|---|
|**Question 8**||0.5 / 0.5 points|

What property must an algorithmic recurrence satisfy?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It must use the master method|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It must have exactly 2 recursive calls|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Every recursion path must terminate in finite time|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The driving function must be polynomial|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>An algorithmic recurrence must have the property that every path of recursion terminates in a defined base case within a finite number of recursive invocations.|   |

|   |   |   |
|---|---|---|
|**Question 9**||0.5 / 0.5 points|

Why should you NOT use asymptotic notation (like O or Θ) in your inductive hypothesis?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It makes the proof too complicated|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|The hidden constants can change making the proof invalid|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Asymptotic notation doesn't work with induction|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It's just a style preference|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Using asymptotic notation is error-prone because the constant hidden in the notation might change during the proof. You must use explicit constants to ensure validity.|   |

|   |   |   |
|---|---|---|
|**Question 10**||0.5 / 0.5 points|

When using substitution to prove T(n) = O(n lg n) which is the correct inductive hypothesis?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = O(n lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) ≤ cn lg n for some constant c > 0|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) ≤ O(n lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) < n lg n|

|   |   |
|---|---|
|Hide question 10 feedback|   |
|||
|## Feedback<br><br>You must use explicit constants in your inductive hypothesis not asymptotic notation. The correct form is T(n) ≤ cn lg n where you get to name and choose c.|   |

|   |   |   |
|---|---|---|
|**Question 11**||0.5 / 0.5 points|

A complete binary tree of height h has how many leaves?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|h|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|2h|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|2^h|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|h²|

|   |   |
|---|---|
|Hide question 11 feedback|   |
|||
|## Feedback<br><br>A complete binary tree doubles the number of nodes at each level. At depth h (the leaves) there are 2^h nodes.|   |

|   |   |   |
|---|---|---|
|**Question 12**||0.5 / 0.5 points|

To prove T(n) = O(f(n)) using substitution what inequality do you need to show?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = cf(n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) ≤ cf(n) for some constant c > 0|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) < f(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) ≥ cf(n)|

|   |   |
|---|---|
|Hide question 12 feedback|   |
|||
|## Feedback<br><br>For an upper bound (O-notation) you need to show T(n) ≤ cf(n) for some positive constant c and all sufficiently large n.|   |

|   |   |   |
|---|---|---|
|**Question 13**||0.5 / 0.5 points|

For T(n) = 3T(n/4) + cn² how many leaves does the recursion tree have?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|lg n|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|n^(log₄ 3)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|3^(log₄ n)|

|   |   |
|---|---|
|Hide question 13 feedback|   |
|||
|## Feedback<br><br>At depth i there are 3^i nodes. The depth is log₄ n so there are 3^(log₄ n) = n^(log₄ 3) leaves. Using the identity a^(log_b n) = n^(log_b a).|   |

|   |   |   |
|---|---|---|
|**Question 14**||0.5 / 0.5 points|

What are the two main steps of the substitution method?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Divide the problem then combine solutions|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Guess the solution then prove it by induction|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Draw a tree then sum the levels|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Identify a and b then apply the master theorem|

|   |   |
|---|---|
|Hide question 14 feedback|   |
|||
|## Feedback<br><br>The substitution method has two steps: (1) Guess the form of the solution and (2) Use mathematical induction to prove your guess is correct.|   |

|   |   |   |
|---|---|---|
|**Question 15**||0.5 / 0.5 points|

What is typically assumed for base cases in algorithmic recurrences when using substitution?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(1) = 0 always|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) = Θ(1) for n < n₀ for some threshold n₀|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Base cases don't need to be verified|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(1) = 1 always|

|   |   |
|---|---|
|Hide question 15 feedback|   |
|||
|## Feedback<br><br>For algorithmic recurrences we assume T(n) = Θ(1) for all n below some threshold n₀. We then choose our constants large enough to handle these base cases.|   |

|   |   |   |
|---|---|---|
|**Question 16**||0.5 / 0.5 points|

Why does subtracting a lower-order term work when there are multiple recursive calls?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It doesn't work; you should add instead|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|You subtract it multiple times (once per call) which helps satisfy the inequality|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|It only works for exactly 2 recursive calls|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The lower-order term cancels out completely|

|   |   |
|---|---|
|Hide question 16 feedback|   |
|||
|## Feedback<br><br>With k recursive calls subtracting d gives you -kd total. This can overcome the additive constant in the recurrence. Adding d would make things worse by giving +kd.|   |

|   |   |   |
|---|---|---|
|**Question 17**||0.5 / 0.5 points|

In a recursion tree what does each node represent?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|A single recursive call|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|The cost of a single subproblem|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The total running time|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|A level of recursion|

|   |   |
|---|---|
|Hide question 17 feedback|   |
|||
|## Feedback<br><br>Each node in a recursion tree represents the cost incurred by solving one subproblem at some level of the recursion.|   |

|   |   |   |
|---|---|---|
|**Question 18**||0.5 / 0.5 points|

For T(n) = 4T(n/2) + cn the costs per level are cn cn cn cn... What dominates the total cost?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The root cost|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The leaf cost|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|All levels contribute equally so multiply by number of levels|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|The middle levels|

|   |   |
|---|---|
|Hide question 18 feedback|   |
|||
|## Feedback<br><br>When costs are equal at each level the total is (cost per level) × (number of levels) = cn · lg n = Θ(n lg n). This is Case 2 of master method.|   |

|   |   |   |
|---|---|---|
|**Question 19**||0.5 / 0.5 points|

For T(n) = 2T(n/2) + cn² what is the total cost at depth i?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|cn²|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|2^i · cn|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|cn² / 2^i|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|2^i · cn²|

|   |   |
|---|---|
|Hide question 19 feedback|   |
|||
|## Feedback<br><br>At depth i: 2^i nodes each with cost c(n/2^i)². Total: 2^i · c(n²/4^i) = cn² · (2/4)^i = cn² / 2^i.|   |

|   |   |   |
|---|---|---|
|**Question 20**||0.5 / 0.5 points|

To prove T(n) = Ω(f(n)) using substitution what inequality do you need to show?

Question options:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) ≤ cf(n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) ≥ df(n) for some constant d > 0|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) < f(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = df(n)|

|   |   |
|---|---|
|Hide question 20 feedback|   |
|||
|## Feedback<br><br>For a lower bound (Ω-notation) you need to show T(n) ≥ df(n) for some positive constant d and all sufficiently large n.|   |
## Quiz 3
|   |   |   |
|---|---|---|
|**Question 1**||1 / 1 point|

T(n) = 3T(n/3) + Θ(n). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n^(log₃ 3))|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Watershed: n. f(n) = Θ(n). Case 2: Θ(n lg n).|   |

|   |   |   |
|---|---|---|
|**Question 2**||1 / 1 point|

T(n) = 7T(n/2) + Θ(n²). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n² lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n^2.81)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n³)|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Watershed: n^(lg 7) ≈ n^2.81. f(n) = Θ(n²) smaller. Case 1: Θ(n^(lg 7)).|   |

|   |   |   |
|---|---|---|
|**Question 3**||1 / 1 point|

T(n) = 2T(n/2) + cn. Tree height?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n/2|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|lg n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|2 lg n|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>Divide by 2 until reach 1: n/2^h = 1 → h = lg n.|   |

|   |   |   |
|---|---|---|
|**Question 4**||1 / 1 point|

T(n) = 4T(n/2) + Θ(√n). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(√n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n lg n)|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>Watershed: n². f(n) = Θ(n^0.5) smaller. Case 1: Θ(n²).|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

T(n) = 9T(n/3) + Θ(n²). What is the solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n²)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n² lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n³)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n^(log₃ 9))|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>Watershed: n^(log₃ 9) = n². f(n) = Θ(n²) equals watershed. Case 2 k=0: T(n) = Θ(n² lg n).|   |

|   |   |   |
|---|---|---|
|**Question 6**||1 / 1 point|

Why is Strassen's (7 calls) faster than simple recursive (8 calls)?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Better constant factors|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Less bushy tree; fewer leaves dominate|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Better divide step|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Better combine step|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>7 vs 8 calls changes exponent from 3 to lg 7 ≈ 2.81. Less bushy tree.|   |

|   |   |   |
|---|---|---|
|**Question 7**||1 / 1 point|

For T(n) = 2T(n/2) + n, to prove T(n) = O(n lg n), use hypothesis:

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = O(n lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) ≤ cn lg n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) < n lg n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = cn lg n|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>Use explicit constant: T(n) ≤ cn lg n.|   |

|   |   |   |
|---|---|---|
|**Question 8**||1 / 1 point|

T(n) = 16T(n/4) + Θ(n²). Which case?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 1|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Case 2|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|None|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>Watershed: n^(log₄ 16) = n². Equal → Case 2.|   |

|   |   |   |
|---|---|---|
|**Question 9**||1 / 1 point|

Which CANNOT use master method?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = 2T(n/2) + Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = 4T(n/2) + Θ(n²)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|T(n) = T(n/3) + T(2n/3) + Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|T(n) = 8T(n/2) + Θ(1)|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Master method needs equal-sized subproblems. Option C has n/3 and 2n/3.|   |

|   |   |   |
|---|---|---|
|**Question 10**||1 / 1 point|

T(n) = 2T(n/2) + Θ(n⁴). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n² lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n⁴)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n⁴ lg n)|

|   |   |
|---|---|
|Hide question 10 feedback|   |
|||
|## Feedback<br><br>Watershed: n. f(n) = Θ(n⁴) much larger. Case 3: Θ(n⁴).|   |

|   |   |   |
|---|---|---|
|**Question 11**||1 / 1 point|

T(n) = 8T(n/2) + Θ(n). Which case and what solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 2; Θ(n lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Case 1; Θ(n³)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 3; Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Doesn't apply|

|   |   |
|---|---|
|Hide question 11 feedback|   |
|||
|## Feedback<br><br>Watershed: n^(log₂ 8) = n³. f(n) = Θ(n) is polynomially smaller. Case 1: T(n) = Θ(n³).|   |

|   |   |   |
|---|---|---|
|**Question 12**||1 / 1 point|

T(n) = 2T(n/2) + Θ(n³). Which case?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 1|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 2|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Case 3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|None|

|   |   |
|---|---|
|Hide question 12 feedback|   |
|||
|## Feedback<br><br>Watershed: n. f(n) = Θ(n³) larger. Case 3.|   |

|   |   |   |
|---|---|---|
|**Question 13**||1 / 1 point|

What must algorithmic recurrence satisfy?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Must have 2+ recursive calls|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|All recursion paths terminate in finite time|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Must use master method|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Base case must be T(1)=1|

|   |   |
|---|---|
|Hide question 13 feedback|   |
|||
|## Feedback<br><br>Algorithmic means every path terminates in finite steps.|   |

|   |   |   |
|---|---|---|
|**Question 14**||1 / 1 point|

T(n) = 3T(n/4) + Θ(n²). What is the solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n³)|

|   |   |
|---|---|
|Hide question 14 feedback|   |
|||
|## Feedback<br><br>Watershed: n^(log₄ 3) ≈ n^0.79. f(n) = Θ(n²) is polynomially larger. Case 3: T(n) = Θ(n²).|   |

|   |   |   |
|---|---|---|
|**Question 15**||1 / 1 point|

T(n) = T(n/2) + Θ(1). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(1)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(√n)|

|   |   |
|---|---|
|Hide question 15 feedback|   |
|||
|## Feedback<br><br>Watershed: n⁰ = 1. f(n) = Θ(1). Case 2 k=0: Θ(lg n).|   |

|   |   |   |
|---|---|---|
|**Question 16**||1 / 1 point|

T(n) = 4T(n/2) + cn. How many leaves?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|n|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|n²|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|2n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|4 lg n|

|   |   |
|---|---|
|Hide question 16 feedback|   |
|||
|## Feedback<br><br>4^(lg n) = n^(lg 4) = n².|   |

|   |   |   |
|---|---|---|
|**Question 17**||1 / 1 point|

T(n) = 2T(n/2) + Θ(n lg n). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n lg n)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n lg² n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n² lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n)|

|   |   |
|---|---|
|Hide question 17 feedback|   |
|||
|## Feedback<br><br>Watershed: n. f(n) = Θ(n lg n). Case 2 k=1: Θ(n lg² n).|   |

|   |   |   |
|---|---|---|
|**Question 18**||0 / 1 point|

T(n) = 2T(n/2) + Θ(n). Solution?

|   |   |
|---|---|
|![Incorrect Response](https://stcloudstate.learn.minnstate.edu/d2l/img/0/Shared.Main.infIncorrect.gif?v=20.26.1.20806 "Incorrect Response")![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n)|
|![Correct Answer](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.infRightAnswer.gif?v=20.26.1.20806 "Correct Answer")![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n lg n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(lg n)|

|   |   |
|---|---|
|Hide question 18 feedback|   |
|||
|## Feedback<br><br>Watershed: n. f(n) = Θ(n). Case 2 k=0: Θ(n lg n).|   |

|   |   |   |
|---|---|---|
|**Question 19**||1 / 1 point|

T(n) = 4T(n/2) + Θ(n²). Which case?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 1|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Case 2|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Case 3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|None|

|   |   |
|---|---|
|Hide question 19 feedback|   |
|||
|## Feedback<br><br>Watershed: n². f(n) = Θ(n²). Equal → Case 2.|   |

|   |   |   |
|---|---|---|
|**Question 20**||1 / 1 point|

T(n) = 8T(n/2) + Θ(1). Solution?

|   |   |
|---|---|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n²)|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.20806 "Selected")|Θ(n³)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n^2.81)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.20806 "Unselected")|Θ(n lg n)|

|   |   |
|---|---|
|Hide question 20 feedback|   |
|||
|## Feedback<br><br>Watershed: n³. f(n) = Θ(1) smaller. Case 1: Θ(n³).|   |