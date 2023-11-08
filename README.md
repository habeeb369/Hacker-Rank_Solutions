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
  > In this problem, there are given the coordinates of a house and the positions of apple and orange trees. We need to complete the function 'countApplesAndOranges' to count the number of apples and oranges that fall within a certain range of the house.

``` c program solution

void countApplesAndOranges(int s, int t, int a, int b, int apples_count, int* apples, int oranges_count, int* oranges) {
    int apples_on_house = 0;
    int oranges_on_house = 0;

    // Calculate the position of each apple and check if it falls on the house.
    for (int i = 0; i < apples_count; i++) {
        int apple_position = a + apples[i];
        if (apple_position >= s && apple_position <= t) {
            apples_on_house++;
        }
    }

    // Calculate the position of each orange and check if it falls on the house.
    for (int i = 0; i < oranges_count; i++) {
        int orange_position = b + oranges[i];
        if (orange_position >= s && orange_position <= t) {
            oranges_on_house++;
        }
    }

    // Print the counts of apples and oranges on the house.
    printf("%d\n%d\n", apples_on_house, oranges_on_house);
}

```
### Steps of execution

1.at first we input s ( starting point of Sam's house location.) and t ( ending location of Sam's house location.),then on second line we input a (location of the Apple tree.) and b (location of the Orange tree),the third input line contains m and n,The fourth line contains m space-separated integers denoting the respective distances that each apple falls from point a.The fifth line contains n space-separated integers denoting the respective distances that each orange falls from point b.

2.in function 'countApplesAndOranges' Initialize apple_count and orange_count variables to keep track of the number of apples and oranges within the range s to t.

3. Calculate the actual landing positions of apples and oranges by adding their distances (apples and oranges arrays) to the respective trees (a and b).

4.Iterate through the apple positions and count how many fall within the specified range s to t. Increment apple_count for each apple that falls within the range.

5. Iterate through the orange positions and count how many fall within the specified range [s, t]. Increment orange_count for each orange that falls within the range.

6.Print the counts of apples and oranges that fall within the specified range.

#### Sample input & output
input
```
7 11
5 15
3 2
-2 2 1
5 -6
 
```
output
```
1
1
```

## 6.Electronics Shop
- [Problem](https://www.hackerrank.com/challenges/electronics-shop/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - Explanation:
  > In this problem, A person wants to determine the most expensive computer keyboard and USB drive that can be purchased with a given budget. we want to complete the 'getMoneySpent' function to find the maximum can spent for buying.the inputs are three space-separated integers ,b ,n and m, the budget, the number of keyboard models and the number of USB drive models.

  ``` c program solution
    int getMoneySpent(int keyboards_count, int* keyboards, int drives_count, int* drives, int b) {
    int maxSpent = -1; // Initialize with -1 to represent no possible purchase
    
    for (int i = 0; i < keyboards_count; i++) {
        for (int j = 0; j < drives_count; j++) {
            int totalCost = keyboards[i] + drives[j];
            
            // Check if the total cost is within budget and higher than the current maxSpent
            if (totalCost <= b && totalCost > maxSpent) {
                maxSpent = totalCost;
            }
        }
    }
    
    return maxSpent;
  }
  ```

### Steps of execution

1.Initialize max_spent as -1, indicating that it's not possible to purchase both items within the budget.

2.Iterate through all combinations of keyboards and drives using nested loops.

3.For each combination, calculate the total cost (total_cost) by adding the cost of the current keyboard and drive.

4.Check if the total_cost is within budget (total_cost <= b) and if it's greater than the current max_spent. If both conditions are met, update max_spent with the total_cost.

5.After iterating through all combinations, max_spent contains the maximum amount that can be spent on a keyboard and a USB drive within the budget. If no valid combination is found, max_spent remains -1.

6.Return the max_spent value as the result, indicating the maximum amount that can be spent on both items within the budget or -1 if it's not possible.

#### Sample input & output
input
```
10 2 3
3 1
5 2 8

```
output
```
9
```
## 7.Viral Advertising
- [Problem](https://www.hackerrank.com/challenges/strange-advertising/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - - Explanation:
      > Complete the viralAdvertising function to  determine how many people have liked the ad by the end of a given day, beginning with launch day as day 1.

     ``` c program solution
    int viralAdvertising(int n) {
    int shared = 5; // Start with 5 initial recipients
    int cumulativeLikes = 0;

    for (int day = 1; day <= n; day++) {
        int likedToday = shared / 2; // Number of people who liked the ad today
        cumulativeLikes += likedToday;
        shared = likedToday * 3; // Number of people who will receive the ad tomorrow
    }

    return cumulativeLikes;
     }
  ```

### Steps of execution

1. cumulativeLikes is initialized to 0 to store the cumulative likes received over n days.

2. shared is initialized to 5 representing the initial number of people the advertisement is shared with on the first day.

3. Iterate through the number of days using the variable day.

4. For each day, calculate the number of likes received (likes) by dividing the current shared count by 2. Add this to the cumulativeLikes

5. Update the shared count for the next day by multiplying the current likes by 3.

6. After iterating through all days, cumulativeLikes contains the total number of likes received over n days.

7. Return the cumulativeLikes as the result, indicating the cumulative number of people who liked the advertisement.


#### Sample input & output
input
```
3
```
output
```
9
```

## 8.Minimum Distances
- [Problem](https://www.hackerrank.com/challenges/minimum-distances/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - - Explanation:
      > The distance between two array values is the number of indices between them. Given a,Complete the 'minimumDistances' function to find the minimum distance between any pair of equal elements in the array. If no such value exists, return -1

``` c program solution
  int minimumDistances(int a_count, int* a) {
    int minDistance = a_count; // Initialize with a large value

    // Iterate through each element in the array
    for (int i = 0; i < a_count; i++) {
        int currentElement = a[i];
        
        // Iterate through the array to find another occurrence of the same element
        for (int j = i + 1; j < a_count; j++) {
            if (a[j] == currentElement) {
                int distance = j - i;
                if (distance < minDistance) {
                    minDistance = distance;
                }
            }
        }
    }

    if (minDistance == a_count) {
        // No pair of equal elements found
        return -1;
    } else {
        return minDistance;
    }
   }

```
### Steps of execution
1. Create a array a[] with some integer elements

2. Initialize the min_distance variable as the total number of elements in the array

3. through nested loop compare each element of the array with the other elements at the array to find the occurence of the same element.

4. if we found any occurence find the distance between them in array ,by counting the array elemnt between them and store it in varable distance,and if it is lesser than minDistance change the value of miinDistance as distance

5.  After iterating through the array, if min_distance remains as the initial large value, it means no equal elements were found, so return -1. Otherwise, return the calculated min_distance representing the minimum distance between equal elements.

## 9.Grading Students
- [Problem](https://www.hackerrank.com/challenges/grading/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - - Explanation:
      > in this Every student receives a grade in the inclusive range from 0 to 100.Any  less than 40 is a failing grade.we want to Complete the function 'gradingStudents' to automate the rounding process

``` c program solution
  int* gradingStudents(int grades_count, int* grades, int* result_count) {
    // Allocate memory for the result array.
    int* result = (int*)malloc(grades_count * sizeof(int));
    
    for (int i = 0; i < grades_count; i++) {
        int grade = grades[i];
        int nextMultiple = (grade / 5 + 1) * 5; // Calculate the next multiple of 5.
        
        // Check if the grade needs rounding.
        if (grade >= 38 && nextMultiple - grade < 3) {
            result[i] = nextMultiple; // Round up.
        } else {
            result[i] = grade; // No rounding needed.
        }
    }
    
    // Set the result_count and return the result array.
    *result_count = grades_count;
    return result;
}
```

### Steps of execution

1. Create an empty arrey called result to store the rounded grades.

2. Iterate through the input grades. For each grade, check if it's less than 38. If it is, add the grade to result without rounding.

3. If the grade is 38 or higher, calculate the next multiple of 5 greater than or equal to the grade.

4. Check if the difference between the next multiple and the grade is less than 3. If it is, round up the grade by using the next multiple of 5. Otherwise, keep the grade unchanged.

5. After iterating through all grades, return the result array, which contains the rounded grades based on the specified rules.

#### Sample input & output
input
```
4
73
67
38
33
```
output
```
75
67
40
33
```
## 9.Diagonal Difference
- [Problem](https://www.hackerrank.com/challenges/diagonal-difference/problem?isFullScreen=true)(navigate to the Problem)
  - [Solution](Staircase.c) (navigate to the Solution file)
  - - Explanation:
      > in this problem a square matrix is given we want to complete the 'diagonalDifference' function which will return the absolute difference between the sums of its diagonals.
    
``` c program solution
  
int diagonalDifference(int arr_rows, int arr_columns, int** arr) {
    int primaryDiagonalSum = 0;
    int secondaryDiagonalSum = 0;

    // Calculate the sum of the primary diagonal
    for (int i = 0; i < arr_rows; i++) {
        primaryDiagonalSum += arr[i][i];
    }

    // Calculate the sum of the secondary diagonal
    for (int i = 0; i < arr_rows; i++) {
        secondaryDiagonalSum += arr[i][arr_rows - 1 - i];
    }

    // Calculate the absolute difference
    int absoluteDifference = abs(primaryDiagonalSum - secondaryDiagonalSum);

    return absoluteDifference;
}


```
      
### Steps of execution

1. primary_diagonal_sum and secondary_diagonal_sum are initialized to 0 to store the sums of the primary and secondary diagonals, respectively.

2. The function iterates through the rows of the matrix. For each row i, it adds the element at position (i, i) (primary diagonal) to primary_diagonal_sum and the element at position arr[i][arr_rows - 1 - i] (secondary diagonal) to secondary_diagonal_sum.

3. After iterating through the matrix, the function calculates the absolute difference between primary_diagonal_sum and secondary_diagonal_sum.

4. The absolute difference is returned as the result, representing the diagonal difference of the input matrix.

#### Sample input & output
input
```
3
11 2 4
4 5 6
10 8 -12
```
output
```
15
```
