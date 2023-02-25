# Colloquial-LC



The lc of colloquial-lc is the acronym of leetcode. I will record the solutions to problems from leetcode conversationally in this project, which can make me more familiar with many terminologies from the field of computer science, especially in data structures and algorithms, and improve my spoken English.



Let's start!



## Solutions



### Two Sum



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

