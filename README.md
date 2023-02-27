# Colloquial-LC



The 'lc' in 'colloquial-lc' stands for the LeetCode. I will record the solutions to problems from leetcode in a conversational style in this project, which can make me more familiar with many terminologies from the field of computer science, especially in data structures and algorithms, and improve my spoken English.



Let's start!



## Solutions



### 1. Two Sum



#### Terminology



+ Index/Indices
+ Brute Force
+ Complexity
+ N squared
+ N cubed
+ N to the fourth power
+ The square root of N
+ In ascending order
+ In descending order 
+ Decrement
+ Loop through
+ Shift



#### Good Expression



+ They add up to the target.



#### Colloquial Solution



I have two solutions to this problem. 



First, sort this array in ascending order and use a left pointer at the start index and a right pointer at the end index to compute the sum of the numbers two pointers point to. If the sum is greater than the target, shift the right pointer to the left by one, and if the sum is less than the target, shift the left pointer to the right by one until we find the target equals the sum or the left pointer equals the right pointer. And the time complexity is O(nlogn), and the space complexity is O(1).



Second, I can use a dictionary to solve this problem. I can loop through the array, and for each element, we check if the complement of the current element is already in the dictionary. If it is, we return the indices of the current element and its complement. If not, we add the current element and index to the dictionary. In this solution, the time complexity is O(n), and the space complexity is O(n).



### 2. Add Two Numbers



#### Terminology



+ Linked list

+ Carry variable
+ Simulate
+ Initialize
+ Indicate



#### Good Expression



+ While either pointer isn't None.
+ Iterating over both linked lists



#### Colloquial Solution



I can use the two-pointer method to simulate the whole process to solve this problem. One pointer points to the head of the first linked list, and the other points to the head of the second linked list. And we'll also initialize a new linked list to store output and a carry variable to set to 0.



Now, While either pointer isn't None:

+ We'll add the values of the numbers two pointers point to, along with the carry variable. By the way, If the pointer is None, set its number to zero.
+ If the sum is lower than 10, we'll add the new node to the output linked list with the sum as its value.
+ If the sum is higher than 10, we'll add the new node to the output linked list with the sum - 10 as its value and set the carry variable to 1. 
+ Then, we'll shift pointers that aren't None.

Finally, if the carry variable equals 1, add the new node to the output linked list with a value of 1. Once we've done that, return the output linked list.







