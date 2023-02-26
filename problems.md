# Remove Nth Node From End List
Tags: linked list
Link: https://leetcode.com/problems/remove-nth-node-from-end-of-list/;  
Idea: counter number of nodes in the list, then walk again until Nth node from the end.

# Add Two Numbers (Linked list representation)
Tags: linked list, two pointers  
Link: https://leetcode.com/problems/add-two-numbers/;  
Idea: create two pointers, one for each list. Start walking through both lists, adding up numbers and saving overflow state. Stop when there is no node for both lists.

# Longest substring without repeating characters
Tags: string, hash map, two pointers, sliding window  
Link: https://leetcode.com/problems/longest-substring-without-repeating-characters/  
Idea: create left and right pointers, walk right and store position for each character we meet. If we find character we've met before, we need to move left pointer to position next to it. Then we calculate string length and check if its larger than current. If it its - this is a new result.

# Longest palindrome string
Tags: recursion  
Link: https://leetcode.com/problems/longest-palindromic-substring/  
Idea: here I tried to look at palindrome from the center of it. Walking through substring and trying to build palindrome from current character: it can either be a odd palindrom where characters around are equal or even palindrome where two characters at the center are equal. I believe this is not most optimal solution, maybe should try something with sliding window.

# Add to Array-Form of Integer
Tags:  
Link: https://leetcode.com/problems/add-to-array-form-of-integer/  
Idea: here I tried to flex so I used C, the idea is just to walk from the ends of arrays, add numbers and save overflow state.

# Reverse Integer
Tags:  
Link: https://leetcode.com/problems/reverse-integer/  
Idea: here we make interger positive, and take its digits one by one (combining % and /). At any step we check if adding new digit to result will overflow - we do this by checking if INT_MAX / 10 is smaller then result. If it's okay - we add digit to result.

# Container With Most Water
Tags: two pointers  
Link: https://leetcode.com/problems/container-with-most-water/  
Idea: we start with to pointers, one at the start of the array and one at the end of the array. We know that each time we move either of the pointers to the center we reduce one part of the product. That's why we should always move pointer where height is smallest because holding to it won't give us bigger container.

# Generate parenthesis
Tags: recursion, tree  
Link: https://leetcode.com/problems/generate-parentheses/  
Idea: here I tried to think of this problem as about building a tree where we start with "_" and we can create and we can create "(\_)\_" from it and "((\_)\_)\_" and "(\_)(\_)\_" after that. So each time we build tree we create an option where we can insert parenthesis next. We should stop when we reach required depth.

# Reverse Linked List
Tags: linked list, recursion  
Link: https://leetcode.com/problems/reverse-linked-list/  
Idea: the idea is that the last element will be the first, so we go recursively deep until we get it and after we get it when recursive calls go from the stack we rearrange nodes.
```
head.next.next = head; // (1) -> (2) -> (3) => (1) -> (2) -> (3) -> (2) -> ...
head.next = null; // remove loop
```

# Merge Two Sorted Lists
Tags: linked list  
Link: https://leetcode.com/problems/merge-two-sorted-lists/  
Idea: here we create two pointers and walk over each list building a new one, we do it until both lists end.

# Two Sum
Tags: hash map  
Link: https://leetcode.com/problems/two-sum/  
Idea: we walk over the array and for each number save complimentary to the target. Then if for the number we meet complimentary record - this is the answer.

# Squares of a sorted array
Tags: two pointers  
Link: https://leetcode.com/problems/squares-of-a-sorted-array/  
Idea: we know that the smallest square number will be number that is closest to zero. The idea is to find that number and put it in the first position of the array. Then start going left and right and look for smallest numbers, square them and put into the array.

# Permutations of a string
Tags: hash map, sliding window  
Link: https://leetcode.com/problems/permutation-in-string/  
Idea: first we count all the letters inside children string, then we create and sliding window and start moving right pointer. If we meet the letter that is not present in child string - we drop current map and move left pointer - that just means the letter is wrong and we should start building again. Then if we meet a correct letter - we add up. Then if we meet an extra correct letter, we start moving left until we get rid of extra letter. Then we check if maps are equal.

# Validate binary search tree
Tags: DFS, binary tree  
Link: https://leetcode.com/problems/validate-binary-search-tree/  
Idea: for this problem I thought that for each node we should clamp values in between smallest and largest parent. So we start with minimum -Infinity and maximum Infinity. If we go left - that means that all nodes on the left will be smaller than current node, but larger than -Infinity. Then, for example, if we go right after than - all nodes in the subtree will be larger then our current node, but smaller than it's parents node.

# Sort colors
Tags:   
Link: https://leetcode.com/problems/sort-colors/  
Idea: I just practiced quick sort here

# 3Sum
Tags: two pointers  
Link: https://leetcode.com/problems/3sum/  
Idea: the idea is to sort an array and fix a number and think of it as a two sum problem. We go over elements, if we seen this element before we skip it. For each element we start left on the next one and right at the end of the array. We check when sum. If sum is 0 - good for us, we've found the triplet - we add it to the result and skip repeating numbers. If it is not 0 - we move left or right depending on whether sum is smaller or larger than 0.

# 3Sum closest
Tags: two pointers  
Link: https://leetcode.com/problems/3sum-closest/  
Idea: same as [3Sum](#3Sum), but we just try to get a closer number

# Merge intervasl
Tags: intervals  
Link: https://leetcode.com/problems/merge-intervals/  
Idea: here I tried to walk over intervals, saving currentStart and currentEnd. If we meet an interval whit start lower than currentEnd - that means we can merge it and maybe increase current end. Else there is a gap and we push current interval and start building next one. Here I also sorted interval first by their starts.

# Interval List intersections
Tags: intervals, two pointers  
Link: https://leetcode.com/problems/interval-list-intersections/  
Idea: idea here was a bit spaghetti. I tried starting with earliest interval, than tried to find all intervals in another list that intersect it and add them to answer (we find them by comparing their start to current interval end). If second list interval ends earlier than first one - we move its index.

# Binary Tree Zigzag Level Order Traversal
Tags: BFS  
Link: https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/  
Idea: here is where I first encountered BFS, I did it using queue. Then we meet a node, we add its children to queue and then process it. Queue will look something like this: [5, 2, 3, 6, 7]. For Zigzag pattern I just used a flag.

# Binary Tree Level Order Traversal
Tags: BFS  
Link: https://leetcode.com/problems/binary-tree-level-order-traversal/  
Idea: same as [zigzag order traversal, but without flag](#binary-tree-zigzag-level-order-traversal)

# Minimum depth of Binary Tree
Tags: DFS  
Link: https://leetcode.com/problems/minimum-depth-of-binary-tree/  
Idea: here we need to find leaf node, which is a node that does not have any children - so this is our base condition - we find it and return depth, otherwise we go deeper for minimum of left and right if both are present and if only one of them is present than just for them.

# Minimum window substring
Tags: sliding window  
Link: https://leetcode.com/problems/minimum-window-substring/description/  
Idea: here I tried couting all letters in given substring. Then we create two pointers and start moving right pointer until we have enough letters to match substring. Then we move forward and if we meet an extra letter - we can move left, removing letters until we hit one we can't remove - than we move right again.

# Permutations
Tags: recursion  
Link: https://leetcode.com/problems/permutations/description/  
Idea: I went to this problem with something like in [Generate parenthesis](#generate-parenthesis), the idea is to take each number and elements that are left, permutation will be [thiNumber, ...elementsThatAreLeft], and we keep doing this until elements that are left are just 1
