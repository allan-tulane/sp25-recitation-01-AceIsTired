[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/tqM-lrvp)
# CMPS 2200  Recitation 01

**Name:** Jamari Ross

In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`. All tests are in `test_main.py`.

## Install Python Dependency

We need Python library of "tabulate" to visualize the results in a good shape. Please install it by running 'pip install tabulate' or 'pip install -r requirements.txt' in Shell Tab of Repl.

## Running and testing your code

- To run tests, from the command-line shell, you can run
  + `pytest test_main.py` will run all tests
  + `pytest test_main.py::test_one` will just run `test_one`
  + We recommend running one test at a time as you are debugging.

## Turning in your work

- Once complete, click on the "Git" icon in the left pane on repl.it.
- Enter a commit message in the "what did you change?" text box
- Click "commit and push." This will push your code to your github repository.
- Although you are working as a team, please have each team member submit the same code to their repository. One person can copy the code to their repl.it and submit it from there.

## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

`Binary Search`: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

- [X] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`.

- [X] 2. Test that your function is correct by calling from the command-line `pytest test_main.py::test_binary_search`

- [X] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

- [X] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`?

**TODO: your answer goes here**
The worst-case input value for linear_search would be the last value in the list, or a value not in the list. Working with the same list in test_main.py, this would mean the worst-case input key would be 5 or -1, as 5 is the last value in the list, and -1 is not in the list.

For binary search (in my example), the worst-case is the second or last value, or a value not in the list. This would mean the worst-case key would be 2, 5, or -1. 2 and 5 are the second and last values in the array respectively, and -1 is not in the list.



- [X] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`?

**TODO: your answer goes here**
The best case key for linear search would be 1, and the best case key for binary search would be 3. This is because these keys are the values in the first indexes that are checked by their respective algorithms.


- [X] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

- [X] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest test_main.py::test_compare_search`, which contains some simple checks.

- [X] 8. Call `print_results(compare_search())` and paste the results here:

**TODO: add your timing results here**
|            n |   linear |   binary |
|--------------|----------|----------|
|       10.000 |    0.000 |    0.000 |
|      100.000 |    0.000 |    0.000 |
|     1000.000 |    0.000 |    0.000 |
|    10000.000 |    0.000 |    0.000 |
|   100000.000 |    5.000 |    0.000 |
|  1000000.000 |   53.000 |    0.000 |
| 10000000.000 |  503.000 |    0.000 |

- [X] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?

**TODO: your answer goes here**
My compare_search results do match the theoretical running times that are expected from linear and binary search. I believe this is because the worst-case time complexity of binary search ($O(log_2(n))$) will always run faster than the worst-case time complexity of linear search ($O(n)$).

- [X] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times.
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search?
      + **TODO: your answer goes here**
      The worst-case time complexity would be $O(n*k)$, because the loop is ran $k$ times.

  + For binary search?
      + **TODO: your answer goes here**
      The worst-case time complexity would be $O((n^2 + log_2(n)) * k)$.
      If it is assumed that the list will be sorted each time, then its time cost would be $n^2$, which is added to the search time cost of $log_2(n)$. This is all multiplied by $k$ because it is ran $k$ times.

  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting?
      + **TODO: your answer goes here**
      It's more efficient to use linear search for all values of $k$, because the added time cost of sorting for binary search causes the time complexity to be significantly greater than that of linear search.