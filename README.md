#Understanding the problem:
In this problem you are given a partially filled 9*9 2-D array(arr) which represents an incomplete Sudoku state. 
All you are required to do is assign the digits from 1 to 9 to the empty cells following some rules. 
Rule 1 -> Digits from 1-9 must occur exactly once in each row. 
Rule 2 -> Digits from 1-9 must occur exactly once in each column. 
Rule 3 -> Digits from 1-9 must occur exactly once in each 3x3 sub-array of the given 2D array. 
Assumption -> The given Sudoku puzzle will have a single unique solution.

For example:

Sample Input: 3 0 6 5 0 8 4 0 0 
              5 2 0 0 0 0 0 0 0 
              0 8 7 0 0 0 0 3 1 
              0 0 3 0 1 0 0 8 0 
              9 0 0 8 6 3 0 0 5 
              0 5 0 0 9 0 6 0 0 
              1 3 0 0 0 0 2 5 0 
              0 0 0 0 0 0 0 7 4 
              0 0 5 2 0 6 3 0 0 
              
Sample Output: 3 1 6 5 7 8 4 9 2 
               5 2 9 1 3 4 7 6 8 
               4 8 7 6 2 9 5 3 1 
               2 6 3 4 1 5 9 8 7 
               9 7 4 8 6 3 1 2 5 
               8 5 1 7 9 2 6 4 3 
               1 3 8 9 4 7 2 5 6
               
How?

Just by following the rules of the games, you can achieve this output. For more clarity of the question.
2. Approach:
Let us go through the rules again: Each row should have a number from 1 to 9 without repetition. 
Each row should have a number from 1 to 9 without repetition. 
Each 3 X 3 box should have a number from 1 to 9 without repetition.
Sudoku can be divided into 9, 3 X 3 boxes as shown in the image below.

With the help of recursion and backtracking, we will try to place every number from 1 to 9 on the cell where zero is present.
But before using that number, we will first check whether that number is valid or not by checking whether the current row, column or sub matrix contains the number already.
And if that number is already present we will not place it.
If it is not present, we will place the number on the current cell (mark) and move to the next cell which has zero. 
If we have tried all the numbers and we still do not find any valid number, we will use backtracking and unmark all the cells that we marked before and repeat 
 the process for a new number.
 If we reach the end of the Sudoku, it means that we have found a valid Sudoku, and we will print it.
