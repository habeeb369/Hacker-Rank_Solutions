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

4.The  function 'birthdayCakeCandles' takes the array as an argument and find the count of tallest candle 

5.An integer variable max_height is declared to store the maximum height of the candle initially declared as -1 & another variable count is declared with value 0 to count number of tallest candle

6..A loop runs from 0 to candle_count - 1 to check all the elements of the array whether it is bigger than the current value in max_height, if the condition met true that element is assigned as max_height and count variable is set 1 

7.else if the array element is equal to the value of max_height the count variable is incremented by 1

8.after completing the loop the count variable is returned to the main function.

9.The result  is then printed at the main function.

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

## 3.Staircase
 - [Problem](https://www.hackerrank.com/challenges/staircase/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - Explanation:
  > In this problem, the user inputs a value to variable 'n', we need to complete the 'staircase' function which will prints a staircase using'#' and ' ' whose height and base will be equal to n

``` c program solution
void staircase(int n) {
    for (int i = 1; i <= n; i++) {
        // Print spaces
        for (int j = 1; j <= n - i; j++) {
            printf(" ");
        }
        
        // Print #
        for (int k = 1; k <= i; k++) {
            printf("#");
        }
        
        // Move to the next line
        printf("\n");
    }
}

```
### Steps of execution
1.The program starts by asking the user to input the value 'n' (base and height of staircase).

2.The  function 'staircase' takes the variable 'n' as an argument and execute it.

3.A loop runs fom 1 to n for creating stair case

4.There are 2 inner loops with one ranging from 1 to n-i to print spaces and another loop ranging from 1 to i for printing #

5.At  the end of loop a  print line command is given to jump to next line 

6.A staircase is printed by  the end of the first loop with 'n' as its base & height

#### Sample input & output
input
```
6 
```
output
```
     #
    ##
   ###
  ####
 #####
######
```

## 4.Mini-Max Sum
 - [Problem](https://www.hackerrank.com/challenges/mini-max-sum/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - Explanation:
  > In this problem, the user inputs 5 positive integers .We need to complete 'miniMaxSum' to find out the minimum and maximum values that can be calculated by adding any 4 of the 5 integers, and print it

``` c program solution
void miniMaxSum(int arr_count, int* arr) {
    long long totalSum = 0;
    
    // Sort the array in ascending order
    for (int i = 0; i < arr_count - 1; i++) {
        for (int j = 0; j < arr_count - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    // Calculate the minimum sum (sum of the first four elements)
    for (int i = 0; i < 4; i++) {
        totalSum += arr[i];
    }
    
    long long minSum = totalSum;
    
    // Calculate the maximum sum (sum of the last four elements)
    totalSum = 0;
    for (int i = 1; i < 5; i++) {
        totalSum += arr[i];
    }
    
    long long maxSum = totalSum;

    // Print the minimum and maximum sums
    printf("%lld %lld\n", minSum, maxSum);
}


```

### Steps of execution
1.The program starts by asking the user to input the 5 integer values to array 'arr[]'.

2.The  function 'miniMaxSum' takes the variable 'arr_count' (no of elemnts in array) & 'arr[]' (integer array) as an argument and execute it.

3.totalsum a long variable is declared as 0 

4.sort the array in asscending order

5.calculate the minimum sum by caculating the first of 4 elements of array and assigned to a variable minSum.

6.calculate the the maximum sum by calculating the last four elements of the array and assigned to variable maxSum

7.print the maxsum & minsum 

#### Sample input & output
input
```
1 2 3 4 5 
```
output
```
10 14
```

## 5.Apple and Orange
- [Problem](https://www.hackerrank.com/challenges/apple-and-orange/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - Explanation:
  > In this problem, the user inputs 5 positive integers .We need to complete 'miniMaxSum' to find out the minimum and maximum values that can be calculated by adding any 4 of the 5 integers, and print it

