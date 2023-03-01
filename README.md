# Colloquial-LC



The 'lc' in 'colloquial-lc' stands for the LeetCode. I will record the solutions to problems from leetcode in a conversational style in this project, which can make me more familiar with many terminologies from the field of computer science, especially in data structures and algorithms, and improve my spoken English.



Let's start!



## Solutions



### 3. Longest Substring Without Repeating Characters



#### Terminology



+ Repeating Characters
+ Sliding Window Technique
+ Enqueue
+ Dequeue
+ Shrink
+ Expand
+ Maintain
+ Encounter
+ Keep track of
+ Maximum
+ Minimum



#### Good Expression



+ We also keep track of the maximum length of the window seen so far.
+ The maximum of the current window size and the previous maximum length.



#### Colloquial Solution



We can solve this problem by using the sliding window technique. We maintain a window of characters that have not been repeated yet, and we keep expanding it as long as the new character is not already in the window. If we encounter a new character already in the window, we shrink this window from left to right until we remove that character from the window. We also keep track of the maximum length of the window seen so far.



```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        char_set = set()
        left, right = 0, 0
        max_len = 0
        
        while right < len(s):
            if s[right] not in char_set:
                char_set.add(s[right])
                right += 1
                max_len = max(max_len, right - left)
            else:
                char_set.remove(s[left])
                left += 1
        
        return max_len
```





In this code, we initialize an empty set `chat_set` to keep track of the characters in the sliding window. We also initialize `left` and `right` pointers to the beginning of the string. We then iterator over the string `s` using the `right` pointer, and check if the character at `right` is already in the `char_set`. If it is not in the set, we add it to the set and shift the `right` pointer to the next. We also update `max_len` to the maximum of the current window size and the previous maximum length.



If it is in the set, we remove the character at the `left` from the set and shift the `left` pointer to the next until we remove that character from the set. We then repeat this process of adding new characters to the set and updating `max_len`.



Once we have processed the entire string, we return `max_len`.



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



We can use the two-pointer method to simulate the whole process to solve this problem. One pointer points to the head of the first linked list, and the other points to the head of the second linked list. And we'll also initialize a new linked list to store output and a carry variable to set to 0.



Now, While either pointer isn't None:

+ We'll add the values of the numbers two pointers point to, along with the carry variable. By the way, If the pointer is None, set its number to zero.
+ If the sum is lower than 10, we'll add the new node to the output linked list with the sum as its value.
+ If the sum is higher than 10, we'll add the new node to the output linked list with the sum - 10 as its value and set the carry variable to 1. 
+ Then, we'll shift pointers that aren't None.

Finally, if the carry variable equals 1, add the new node to the output linked list with a value of 1. Once we've done that, return the output linked list.





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





### 



