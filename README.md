# Hacker-Rank_Solutions
>The repository contains the solutions to various HackerRank problems.Organize the solutions so they are easy to navigate and understand. Each solution includes a reference to the problem statement and is well-documented to explain the logic and approach.

## 1.Simple Array Sum

  - [Problem](https://www.hackerrank.com/challenges/simple-array-sum/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](simpleArraySum.c) (navigate to the Solution file)
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

3.A loop runs from 0 to (n-1), where the user is prompted to enter each element for the array. 

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
## 2.Birthday Cake Candles
 - [Problem](https://www.hackerrank.com/challenges/birthday-cake-candles/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](birthdayCakeCandles.c) (navigate to the Solution file)
  - Explanation:
  > In this problem, the user inputs and array of which contains the height of each candles on the cake, we need to complete the 'birthdayCakeCandles' function which gives the count of tallest candle in the array.

``` c program solution
 int birthdayCakeCandles(int candles_count, int* candles) {
    // Initialize variables to keep track of the maximum height and the count of candles with that height
    int max_height = -1;
    int count = 0;

    // Iterate through the array to find the maximum height
    for (int i = 0; i < candles_count; i++) {
        if (candles[i] > max_height) {
            max_height = candles[i];
            count = 1; // Reset the count to 1 for the new maximum height
        } else if (candles[i] == max_height) {
            count++; // Increment the count for candles with the same maximum height
        }
    }

    return count; // Return the count of candles with the maximum height
}

```
### Steps of execution
1.The program starts by asking the user to input the number of candles (candles_count).

2.An empty array (candles) is initialized to store these elements.

3.A loop runs from 0 to (candles_count -1), where the user is prompted to enter each element for the array. 

4.The  function 'birthdayCakeCandles' takes the array as an argument and find the count of tallest candle and returns 'count' variable which contains the result value into the main function

5.The result  is then printed at the main function.

#### Sample input & output
input
```
4
3 2 1 3
```
output
```
2
```
