# List of some of my LeetCode, HackerRank, and other practice codes!
1. [compress.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/compress.go)

 - Time Complexity: O(n)
   
   Space Complexity: O(1)

 - **Input and Output Examples:**
 
   **Example 1:**

   Input: chars = ["a","a","b","b","c","c","c"] 
   Output: Return 6, and the first 6 characters of the input array should be: ["a","2","b","2","c","3"] 
   Explanation: The groups are "aa", "bb", and "ccc". This compresses to "a2b2c3". 
   
   **Example 2:** 

   Input: chars = ["a"] 
   Output: Return 1, and the first character of the input array should be: ["a"] 
   Explanation: The only group is "a", which remains uncompressed since it's a single character. 
  
   **Example 3:**

   Input: chars = ["a","b","b","b","b","b","b","b","b","b","b","b","b"] 
   Output: Return 4, and the first 4 characters of the input array should be: ["a","b","1","2"]. 
   Explanation: The groups are "a" and "bbbbbbbbbbbb". This compresses to "ab12". 

 - It will first check if the length of chars is 0 or 1 and it will return 0 or 1 respectively, since there is no need to compress a sequence of 0 or 1 character.

 - The function initializes comp variable to be the first character in chars, count to be 1, and compressIdx to be 0 and it will then enter a for loop that iterates over the characters in chars, starting from the second character. If the current character is the same as the previous one (comp), the function increments the count variable by 1.

 - If the current character is different from the previous one, the function writes the previous character (comp) to the compressIdx position in chars and increments compressIdx by 1.If the count variable is greater than 1, it means there are repeated characters, so the function converts the count to a string using strconv.Itoa(count) and writes each digit of the count to the compressIdx position in chars, and increments compressIdx by the length of the count string. The function then updates comp to be the current character and resets count to 1. After the loop is finished, the function returns the value of compressIdx, which represents the length of the compressed sequence.

2. [isPalindrome.go](https://github.com/bryanoliverh/LeetCode-Practice-Golang/blob/main/sortArray.go)

  - Time Complexity: O(log(n))
  
    Space Complexity: O(n)

  - The function isPalindrome takes an integer x as input and it will return a boolean which indicates whether x is a palindrome or not. A palindrome is a number that reads the same backward as forward.
so for example:

  - **Input and Output Examples:**
    
    Input: x = 121
    
    Output: true
    
    Explanation: 121 reads as 121 from left to right and from right to left.

  - The function first checks if x is negative or ends with a zero, except when x is zero itself. If either condition is true, the function immediately returns false because such numbers cannot be palindromes.

  - Afterward, the function initializes a variable rev to zero and it will enter a loop where it repeatedly extracts the last digit of x and adds it to rev after shifting the digits of rev one position to the left. Therefore, this effectively reverses the digits of x and stores the result in rev. At the same time, the function removes the last digit of x by integer division with 10.

  - The loop will continue as long as x is greater than rev, since the reversal of the first half of x is not complete until x becomes smaller than rev. If x and rev have an odd number of digits, the middle digit is ignored because it is the same in both numbers. After the loop completes, the function checks whether x is equal to rev or to rev/10 and the second case arises when x has an odd number of digits, and the middle digit has already been removed from rev.
  - The expression x == reverse || x == reverse / 10 is checking whether the input integer x is a palindrome or not while at the end of the for loop, the variable reverse will contain the reverse of the first half of x. For example, if x is 1234321, then reverse will be 1234. Then it will compare the first half of x with the second half to check if it's a palindrome. If x has an odd number of digits, we can ignore the middle digit, which will be equal to itself. If x has an even number of digits, we need to compare the first half of x with the second half minus the last digit. For example, if x is 1221, then reverse will be 12, and we need to ignore the last digit in reverse. Therefore, the expression x == reverse / 10 checks if x is a palindrome when it has an even number of digits.
  - If either of these conditions is true, the function returns true, indicating that x is a palindrome. Otherwise, it returns false.

  
3. [sortArray.go](https://github.com/bryanoliverh/LeetCode-Practice-Golang/blob/main/sortArray.go)
  - Time Complexity: O(n log n)
    
    Space Complexity: O(n)

  - Sort Array Function in GO without built-in functions!

  - The function takes 1 list input and returns the sorted list without any built in functions.


  - The function implements quick sort algorithm which takes slice of integers with the variable name of nums, and the range of indices low and high which will be sorted. If low is less than high, the slice will be partitioned using the partition function, and recursively calls itself on the left and right sub-arrays.

 - Another function is the partition function which is used to do the partition of the input slice of integers nums. It will choose the last element in the slice as the initial element that will be use as the pivot, and iterates over the slice from low to high-1. If an element is less than the initial element, it swaps it with the current index i, and increments i. Finally, it swaps the pivot element with the element at index i and returns i.

4. [twoSum.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/twoSum.go)

  - Time Complexity: O(n)
   
    Space Complexity: O(n)
  - Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.  You may assume that each input would have exactly one solution, and you may not use the same element twice. 
  - **Input and Output Examples:**
    
    Example 1: 
    
    Input: nums = [2,7,11,15], target = 9 
    
    Output: [0,1] 
    
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1]. 
  - The twoSum function takes an integer slice array and a target integer target as its input, and returns a slice of two integers that represent the indices of the two numbers in the input array that add up to the target value. If there are no such indices, an empty slice is returned. 
  - The function uses a hash map called seenNums to keep track of the numbers it has already seen while iterating through the array. In each iteration, it calculates the difference between the target value and the current number in the array and checks whether the difference is already in the hash map. If it is, the function returns a slice with the current index i and the index of the difference j that was previously stored in the hash map. If the difference is not in the hash map, the function stores the current number and its index in the hash map. 
  - seenNums map stores the numbers in the input array as keys and their corresponding indices as values. The syntax j, ok := seenNums[potentialMatch] will simultaneously checks whether the value exists in the map and retrieves its value. The value of found will be true if potentialMatch is a key in the seenNums map, and false otherwise. The value of j will be the value associated with the key potentialMatch if it exists in the map, and the zero value for its type otherwise. 
  
 5. [intToRoman_romanToInt.go](hhttps://github.com/bryanoliverh/CodePractice-Golang/blob/main/intToRoman_romanToInt.go)
   -  Time Complexity: O(n)
   
      Space Complexity: O(1)
  - Given an integer, convert it to a roman numeral. 
  - **Input and Output Examples:**
  
     Example 1: 
     
     Input: num = 3 
     
     Output: "III" 
     
     Explanation: 3 is represented as 3 ones. 

     Example 2: 
     
     Input: num = 58 
     
     Output: "LVIII" 
     
     Explanation: L = 50, V = 5, III = 3. 
