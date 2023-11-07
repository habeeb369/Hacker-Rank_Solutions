# Hacker-Rank_Solutions
>The repository contains the solutions to various HackerRank problems.Organize the solutions so they are easy to navigate and understand. Each solution includes a reference to the problem statement and is well-documented to explain the logic and approach.

## 1.Simple Array Sum

  - [Problem](https://www.hackerrank.com/challenges/simple-array-sum/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution]() (navigate to the Solution file)
  - Explanation:
  > In this problem, We have given an array of integers to find its sum.We need to complete the 'simpleArraySum' Function given in the program and it must return the sum of array elements as an integer

 ``` c program solution
  int simpleArraySum(int ar_count, int* ar) {
    int sum = 0; 

    for (int i = 0; i < ar_count; i++) {
        sum += ar[i]; 
    }

    return sum; 
}

```
### Steps of execution
1.The program starts by asking the user to input the number of elements they want to have in the array (n).

2.An empty array (ar) is initialized to store these elements.

3.A loop runs from 0 to (n-1), where the user is prompted to enter each element for the array. It handles the ValueError exception if the user enters something that's not a valid number.

4.The  function 'simpleArraySum' takes the array as an argument and calculates the sum of its elements and returns 'sum' variable which contains the result value into the main function

5.The result  is then printed at the main function.

#### Sample input & output
input
```
6
1 2 3 4 10 11
```
output
```
31
```
