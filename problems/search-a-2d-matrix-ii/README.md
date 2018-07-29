
# Leetcode: Search a 2D Matrix II     :BLOG:Medium:

---

Search a 2D Matrix  

---

Similar Problems:  

-   [Kth Smallest Element in a Sorted Matrix](https://code.dennyzhang.com/kth-smallest-element-in-a-sorted-matrix)
-   [Review: Binary Search Problems](https://code.dennyzhang.com/review-binarysearch)
-   Tag: [#binarysearch](https://code.dennyzhang.com/tag/binarysearch)

---

Write an efficient algorithm that searches for a value in an m x n matrix. This matrix has the following properties:  

Integers in each row are sorted in ascending from left to right.  
Integers in each column are sorted in ascending from top to bottom.  
For example,  

Consider the following matrix:  

    [
      [1,   4,  7, 11, 15],
      [2,   5,  8, 12, 19],
      [3,   6,  9, 16, 22],
      [10, 13, 14, 17, 24],
      [18, 21, 23, 26, 30]
    ]

Given target = 5, return true.  

Given target = 20, return false.  

Github: [challenges-leetcode-interesting](https://github.com/DennyZhang/challenges-leetcode-interesting/tree/master/problems/search-a-2d-matrix-ii)  

Credits To: [leetcode.com](https://leetcode.com/problems/search-a-2d-matrix-ii/description/)  

Leave me comments, if you have better ways to solve.  

---

    ## Blog link: https://code.dennyzhang.com/search-a-2d-matrix-ii
    ## Basic Ideas: We search from the left bottom position
    ##    If the value is smaller than the target, move right
    ##    If bigger, move up
    ##
    ## Complexity: Time O(n+m), Space O(1)
    class Solution:
        def searchMatrix(self, matrix, target):
    	"""
    	:type matrix: List[List[int]]
    	:type target: int
    	:rtype: bool
    	"""
    	row_count = len(matrix)
    	# []
    	if row_count == 0: return False
    	col_count = len(matrix[0])
    	# [[]]
    	if col_count == 0: return False
    	if matrix[0][0] > target or matrix[-1][-1] < target: return False
    	i, j = row_count-1, 0
    	while i>=0 and j<=col_count-1:
    	    if matrix[i][j] == target: return True
    	    if matrix[i][j] < target: j += 1
    	    else: i -= 1
    	return False
