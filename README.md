# Kadane-s-Algorithm
Kadane's Algorithm is an efficient method used to solve the Maximum Subarray Problem, which involves finding the contiguous subarray (within a one-dimensional array) that has the largest sum. The algorithm has a time complexity of 
𝑂
(
𝑛
)
O(n), making it one of the most optimized approaches for this problem.

Problem Statement
Given an integer array 
𝑎
𝑟
𝑟
arr of size 
𝑛
n, find the maximum sum of a contiguous subarray.

Algorithm Explanation
Initialize Variables:

max_so_far to store the overall maximum sum (initialize it to the first element or a very small number like -∞).
max_ending_here to store the maximum sum of the subarray ending at the current position (initialize it to 0 or the first element).
Iterate through the array:

Update max_ending_here by adding the current element to it.
Compare max_ending_here with max_so_far. If max_ending_here is greater, update max_so_far.
If max_ending_here becomes negative, reset it to 0 because a negative sum cannot contribute to the maximum sum.
Result:

max_so_far will hold the maximum sum of the contiguous subarray.
Implementation (Python)
python
Copy code
def max_subarray_sum(arr):
    max_so_far = float('-inf')  # Initialize to a very small number
    max_ending_here = 0

    for num in arr:
        max_ending_here += num
        if max_so_far < max_ending_here:
            max_so_far = max_ending_here
        if max_ending_here < 0:
            max_ending_here = 0

    return max_so_far

# Example
arr = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
print("Maximum Subarray Sum:", max_subarray_sum(arr))  # Output: 6
Dry Run Example
For 
𝑎
𝑟
𝑟
=
[
−
2
,
1
,
−
3
,
4
,
−
1
,
2
,
1
,
−
5
,
4
]
arr=[−2,1,−3,4,−1,2,1,−5,4]:

Index	Current Element	max_ending_here	max_so_far
0	-2	-2	-2
1	1	1	1
2	-3	-2	1
3	4	4	4
4	-1	3	4
5	2	5	5
6	1	6	6
7	-5	1	6
8	4	5	6
Final Output: 
max_so_far
=
6
max_so_far=6 (subarray: [4, -1, 2, 1]).

Applications
Stock market analysis: Finding the best time to buy and sell.
Signal processing: Identifying high-intensity segments.
Genomics: Detecting regions of high similarity.
Let me know if you’d like to explore variations or visualize the working further!
