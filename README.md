# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: First, identifying all cases of naked twins, by looking for boxes within the same unit with exactly two values. Then, we check if those boxes, which are candidates for being naked twins, have indeed the same value. If they do have the same value, they must be naked twins, because they both have only two values, those values are the same, and they share a unit. Then we procede to erase all values of the naked twins' shared peers that they could absolutely not take because of the presence of the naked twins. These changes are made in a way that permit backtracking, so that if the process of eliminating certain values yields an unsolvable puzzle, we can revert the changes and try another option from the depth-first search. 

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: We add another set of diagonal units, one diagonal from A1 to I9, and the other one from A9 to I1. We update the dictionaries of units and peers and the list of units. Then we procede to use the previously defined methods to eliminate the value of a box if a peer has only one value and that peer's value is a substring of the box's value. We then check if there's a box with a value that only it can take in his unit, if this happens, erase all other values from this box. These two methods, in addition to the naked twins strategy, use constraint propagation to eliminate values that don't comply with specific restrictions of the problem (in this case, having repeated digits in a unit). A depth-first search method is used to apply recursively these strategies, selecting the boxes with the least amount of remaining values, and going forward in a left-toright fashion to test the branches of possible solutions until we find a correct one.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.