# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

Resources used:
https://www.freecodecamp.org/news/git-squash-commits/


## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)

9b257

2. What is the SHA for the last commit associated with line 9 of this file?

d1d83

3. What did line 12 of this file say in commit d1d83?

"2. I should really finish writing this."

4. What changed between commit e474c and 82045?
process_movie_data.py:
Line 18: `gross_sort = lambda x : int(x["Gross"])`
Line 20: `top_five = rows[:-6:-1]`

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```
Nothing happens to top_N, but test would "absorb" the changes from top_N and the code would be overwritten. answers.md would remain unchanged from the test branch.

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```
Nothing happens to test, but top_ten also absorb the changes from test in answers.md (the rename). The python file would remain unchanged from the test branch.

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```
At first, we'd apply the quiz.md changes onto the top_ten branch. Then, we'd apply the same changes to the top_N branch. Nothing would change in test.