# Colloquial-LC



The 'lc' in 'colloquial-lc' stands for the LeetCode. I will record the solutions to problems from leetcode in a conversational style in this project, which can make me more familiar with many terminologies from the field of computer science, especially in data structures and algorithms, and improve my spoken English.



Let's start!



## Solutions





### 4. Median of Two Sorted Arrays



#### Terminology



+ Median
+ Mode
+ Average
+ Recursive
+ Recursion
+ Recursively
+ Even number
+ Odd number
+ Floating-point
+ Base case
+ S Floor divided by 2



#### Good Expression



+ This function takes three arguments.

+ We can return the number located at index one in num1.

  

#### Colloquial Solution



To solve this problem, we can use a recursive helper method called `findKth`. This method allows us to discard half of the k numbers from `nums1` or `nums2`, and we can continue to recursively call it until k equals 1. As a result, the time complexity of this approach is O(log(k)), which is more specifically O(log(M + N)), where M represents the length of `nums1` and N represents the length of `nums2`.



This is my code:



```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        n1, n2 = len(nums1), len(nums2)
        def findKth(i1, i2, k):
            if i1 == n1: return nums2[i2 + k - 1]
            if i2 == n2: return nums1[i1 + k - 1]
            if k == 1: return min(nums1[i1], nums2[i2])
            hk = k // 2
            j1, j2 = min(n1 - 1, i1 + hk - 1), min(n2 - 1, i2 + hk - 1)
            if nums1[j1] <= nums2[j2]:
                return findKth(j1 + 1, i2, k - (j1 - i1 + 1))
            return findKth(i1, j2 + 1, k - (j2 - i2 + 1))
        

        s = n1 + n2
        if s % 2 == 0:
            return (findKth(0, 0, s // 2) + findKth(0, 0, (s // 2) + 1)) / 2
        return findKth(0, 0, (s // 2) + 1)
```



We can initialize respectively `n1` and `n2` to equal the lengths of `nums1` and `nums2`. And we can write a recursive method `findKth`, to find the k-th smallest number in the two arrays. This function takes three arguments `i1`, `i2`, and `k`. `i1` and `i2` are indexes that represent the current position in `nums1` and `nums2` respectively,  and `k` is the number smallest we want to find.



To begin, we need to handle several base cases. If `i1` is equal to the length of `nums1`, we can directly return the number located at index `i2 + k - 1` in `nums2`. Similarly, if `i2` is equal to the length of `nums2`, we can directly return the number located at index `i1 + k - 1` in `nums1`. Additionally, if `k` is equal to 1, we can return the minimum value between `nums1[i1]` and `nums2[i2]`.



Next, we attempt to discard half of the `k` numbers from either `nums1` or `nums2`, which results in determining the values of `j1` and `j2`. If `nums1[j1]` is less than or equal to `nums2[j2]`, then we can safely discard the numbers before `j1 + 1` because the k-th smallest number must be located after the number at the index `j1` in `nums1` or after the number at index `i2` in `nums2`. Similarly, if `nums2[j1]` is greater than `nums1[j2]`, we can safely discard the numbers before `j2 + 1` in `nums2`. We can recursively find the answer using this method.



To obtain the median of `nums1` and `nums2`, we add their lengths and calculate the sum `s`. If `s` is even, we take the average of the `s // 2`-th and `(s // 2) + 1`-th smallest elements. If `s` is odd, we return the `(s // 2) + 1`-th smallest element as the median.







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



First, sort this array in ascending order and use a left pointer at the start index and a right pointer at the end index to compute the sum of the numbers two pointers point to. If the sum is greater than the target, shift the right pointer to the left by one, and if the sum is less than the target, shift the left pointer to the right by one until we find the target equals the sum,8u or the left pointer equals the right pointer. And the time complexity is O(nlogn), and the space complexity is O(1).



Second, I can use a dictionary to solve this problem. I can loop through the array, and for each element, we check if the complement of the current element is already in the dictionary. If it is, we return the indices of the current element and its complement. If not, we add the current element and index to the dictionary. In this solution, the time complexity is O(n), and the space complexity is O(n).





