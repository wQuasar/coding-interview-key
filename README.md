# Coding Interview Key

Leetcoding chronicles: A cheat sheet of common topic-wise coding interviews with solutions.

The Error sections mentions the error that I faced when running/attempting the problem, you can ignore it. Or better yet, clone the repository and keep track of your own errors so that you can be mindful of those.

IOOB = Index Out of Bound error
OBOB = Off by One Bug

---

## Arrays

### 1. Sort Array by Parity

LC [905](https://leetcode.com/problems/sort-array-by-parity/description/) 🟢, (Array)

All even numbers at start, all odd at end of array.
[solution gist](https://gist.github.com/wQuasar/abe12e0814c1e617671d619bdb54618d)

**Learnings:** Initially, had two loops, one at start and one at end of array. This is redundant. We can have just one var to track if the start numbers are even, if yes, move to next number, if not, swap with end of list var (while decreasing the end of list index).
**Compile errors:** 2 (variable name mismatch)

### 2. Sort Colors

LC [75](https://leetcode.com/problems/sort-colors/description/) 🟠, (Array)

Sort array of 0, 1, 2 in a single pass.
[solution gist](https://gist.github.com/wQuasar/0172521a08043820d6fb070445d9c343)

**Learnings:** Single pass with three sections using two vars for boundary is sufficient. Always try to minimise loop usage. Mostly single passes are enough. Try to reduce basic logical bugs.
**Compile errors:** 2 (library method name wrong (length -> size), logical error(OBOB))
**Errors:** 2 (logical bugs)

### 3. Plus One

LC [66](https://leetcode.com/problems/plus-one/) 🟢, (Array)

Increment number in array form by one.
[solution gist (recursion)](https://gist.github.com/wQuasar/92815e34e84aeb142fcb4f0ff3da639b)
[solution gist](https://gist.github.com/wQuasar/4c9c741c69634666bebca09b69d326b3)

**Learnings:** Although, recursion may seem easier to implement, it is often a bad performing solution. Prefer loops over recursion.
**Compile errors:** 2 (library method name wrong, logical error (IOOB))

### 4. Jump Game

LC [55](https://leetcode.com/problems/jump-game/) 🟠, (Array)

Progress through array to end, each entry depicts max jump from that index.
[solution gist (recursion)]([ss](https://gist.github.com/wQuasar/980985d5f61c2580c600ed9249a90d76))
[solution gist](https://gist.github.com/wQuasar/935cc76aec8b53f6ee8c100bc221462e)

**Learnings:** Just keep track of max that you can reach till now. If you process an index which is less than max, return false. Else see if this new index can increase your max. As mentioned, recursion leads to confusion.
**Compile error:** 2 (return value incorrect, incorrect code arrangement)
**Error:** 1 (logical error)

### 5. Remove Duplicates from Sorted Array

LC [26](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/) 🟢, (Array)

[solution gist](https://gist.github.com/wQuasar/0ed1479d3b7d522e44cfce4313c33528)

**Learnings:** Keep index of current processed numbers while travelling through the array of duplicates. Develop habit to perform code walkthroughs properly instead of letting the IDE tell you bugs.
**Errors:** 2 (logical error, OBOB)

### 6. Best Time to Buy and Sell Stock

LC [121](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) 🟢, (Array)

Given an array of stock prices, return max profit that can be made by buying and selling a stock once.
[solution gist](https://gist.github.com/wQuasar/bfadfe6c80ca386c6bc80c4259f5afdf)

**Learnings:** Iterate through the prices, keep track of current min and compare with current price to calculate max profit.

### 7. Best Time to Buy and Sell Stock II

LC [122](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/description/) 🟠, (Array)

Buy and sell a stock multiple times but, having at most one stock.
[solution gist](https://gist.github.com/wQuasar/3ccf8b9507ec9a3ff316746c224247e8)

**Learning:** Keep track of min till now and sell as soon as you see a chance at profit (while updating min to sell price).

### 8. Count Primes

LC [204](https://leetcode.com/problems/count-primes/description/), 🟠

Return no. of prime numbers till n.
[solution gist]([dd](https://gist.github.com/wQuasar/0c8348d713660e80f25cd8b0ca58732f))

**Learnings:** Adding all primes to a set and then dividing new numbers with nos. in primeSet. If cannot divide by any no., add number to set. 

**Compile errors:** 5 (3 syntax errors, 1 logical error, 1 incorrect question interpretation)

**Follow up: This fails LC test set.**

### 9. Permutations

LC [46](https://leetcode.com/problems/permutations/) 🟠, (Array)

Return all permutations of an array of distinct numbers.
[solution gist](https://gist.github.com/wQuasar/89c43a754c524c9383f962973ca61686)

**Learnings:** Take each num out and add it to the permutations of the remaining numbers. 
**Compile errors:** 3 (Collections.add() returns boolean!, library method name wrong (sublist -> subList), syntax error)

**Follow up: This has a DFS as well as a cyclic permuatation swap based solutions.**

### 10. Next Permutation

LC [31](https://leetcode.com/problems/next-permutation/) 🟠, (Array)

Return the next lexicographical permutation of the given digits array.
[solution gist](https://gist.github.com/wQuasar/f4c5d3b40839f05de59a6550ab76e962)

**Learnings:** Basically find next bigger number using the same digits (in order). Move from end till you find digit which is less than current digit. Swap the next digit with the next bigger number in the processed part of digits. Reverse the array from the point of initial discrepancy. Run as many edge cases as possible to ensure correct solution is found.
**Compile errors:** n (incorrect library method usage, out of mind errors)
**Errors:** 1 (incorrect solution)

### 11. Spiral Matrix

LC [54](https://leetcode.com/problems/spiral-matrix/) 🟠, (Array)

Return the elements of a m x n matrix in spiral order.
[solution gist](https://gist.github.com/wQuasar/76501a4b4f7bd1434cbcadf9243f5fdc)

**Learnings:** Keep four variables to keep track of the four phases of traversal. We *need* to add loop breaking check before each phase.
**Compile errors:** 4 (logical errors)

### 12. Rotate Matrix

LC [48](https://leetcode.com/problems/rotate-image/) 🟠, (Array)

Given a n x n matrix, rotate the matrix by 90 degrees.
[solution gist (four phased)](https://gist.github.com/wQuasar/7332b50fc21bdc8b9f142130f41651c9)
[solution gist (two reflections)](https://gist.github.com/wQuasar/004df8a817a40b9f5de1513861c8db4e)

**Learnings:** Do traditional rotation in four phases. This is slightly tricky to get right but wiht patience can be done easily. Another solution is based on two reflections. One dialgonal and other vertical.
**Errors:** 3 (logical errors, OBOB)

### 13. Rotate Array

LC [189](https://leetcode.com/problems/rotate-array/) 🟠, (Array)

Given an array, rotate the array by a given number k.
[solution gist (hop chain)](https://gist.github.com/wQuasar/e35881d938e24286dbe785bfa916098e)
[solution gist](https://gist.github.com/wQuasar/e654438d8385f5533a63b2a99a24ffbb)

**Learnings:** Intuitive solution (hop chain) is slightly complicated to code but, we need to use two loops as the inner loop may end in a cycle. To counter this we keep track of the start element in the inner loop and also processedCount is updated. Outer loop is stopped if processedCount is length of the array. A much simpler solution is to firstly reverse the entire array then, reverse the first k numbers followed by reversing the remaining numbers.

**Errors:** 4 (incorrrect solution for even size arrays, method name mismatch)

---

## Strings

### 1. Excel Sheet Column Title

LC [168](https://leetcode.com/problems/excel-sheet-column-title/) 🟢, (Strings)

Given an integer columnNumber, return it's corresponding columnTitle.
[solution gist](https://gist.github.com/wQuasar/75bb4e2661cfd9d23f11572ed5d4d128)
[solution gist (simplified)](https://gist.github.com/wQuasar/e90ff195270874c97dff327c88eece5d)

**Learnings:** Read the input cases properly! We can proceed with a remainder and quotient based logic but the problem arises when the remainder is 0, In this case, the added char should be `Z` and the 'previous' should be one lesser. We can specifically look for this case, or generalise and reduce 1 from the columnNumber in each case (simplified but, this requires us to build a char array that starts with 'Z').

**Errors:** 2 (incorrect output interpretation, too long time to come up with generalized solution)

### 2. Valid Palindrome

LC [125](https://leetcode.com/problems/valid-palindrome/) 🟢, (String)

Tell if a string after removing all the non-alphanumeric characters is a valid palindrome or not.
[solution gist](https://gist.github.com/wQuasar/a4b8f6bf6ee281cddd4c18e4edc43752)

**Learnings:** We can just take a start and end pointer and check if the chars are same (equals, ignore case) while skipping if the pointers are at non-alphanumeric characters.

**Errors:** 1 (incorrect library method (s.size -> s.length))

### 3. Reverse Words in a String

LC [151](https://leetcode.com/problems/reverse-words-in-a-string/) 🟠, (Strings)

Given a string containing alphabets, digits and spaces, return string with order of the words reversed.
[solution gist](https://gist.github.com/wQuasar/001e4516b0d241c0cdbf37483526473c)

**Learnings:** Reverse the entire string. Find the start and end of each word and reverse those. Finally, fetch only alphanumeric characters and put them in a list separated by ' '. Problem arises with OBOB so, look out for those.

**Errors:** 2 (incorrect variable name, logical bug)

### 4. Count and Say

LC [38](https://leetcode.com/problems/count-and-say/) 🟠, (Strings)

Return the nth term of the CountAndSay sequnece (saying the number of digits while breaking them into minimal digits followed by their count)
[solution gist](https://gist.github.com/wQuasar/fe0a6d6a2eb82d0460d7b0e865ade403)

**Learnings:** Start with "1" and then iteratively calculate further sequences using StringBuilder and normal count tracking logic.

**Errors:** 1 (incorrect is String[idx] return type)

### 5. Roman to Integer

LC [13](https://leetcode.com/problems/roman-to-integer/) 🟢, (String)

Given a roman number representation, convert it to decimal number.
[solution gist (naive)](https://gist.github.com/wQuasar/08fe569f21b7f34f03c14b0e68d3fd93)
[solution gist](https://gist.github.com/wQuasar/0b90423687349cba163746b77be1cc11)

**Learnings:** We can go with the naive approach which just keeps track of legal numbers that can be encountered (this works by keeping track of substractions by looking ahead for the next char). This is easy and fast but, the program can grow in size. The problem can be solved faster by noticing that Roman numeral depictions follow a descending path which we can leverage for keeping track of substractions. For e.g. 'I' can never come before 'M'. This implies that if the current char value is more that the last char value then, it means we need to reduce the [twice of] previous char value from result.

### 6. 93. Restore IP Addresses

LC [93](https://leetcode.com/problems/restore-ip-addresses/) 🟠, (String, Backtracking)

Given a decimal string, return all the valid ip addresses from it.
[solution gist](https://gist.github.com/wQuasar/33ad30c9cd6e1c32e3bff22bf7fb24ee)

**Learnings:** The logic can be simplified by using 3 nested for loops to get all 4 numbers individually. Problem comes with getting the loop and substring variables correct.

**Errors:** 3 (variable name mismatch), 3 (logical errors)

### 7. Zigzag Conversion

LC [6](https://leetcode.com/problems/zigzag-conversion/) 🟠, (String)

Given a string and a number of rows, print the string in the zigzag pattern of given number of rows.
[solution gist](https://gist.github.com/wQuasar/ca588b8dbb505328ec260a93c55da2ae)

**Learning:**  The logic revolves around adding chars in the pattern: every (2n - 1)st element in addition to (2(n - i) - 1)th element for intermediate rows till we reach the end of string for that row.

**Errors:** 1 (IOOB), 1 (silly logical bug)

---

## Linked Lists

### 1. Merge Two Sorted Lists

LC [21](https://leetcode.com/problems/merge-two-sorted-lists/) 🟢, (Linked List)

Given header nodes of two sorted list, return node representing the given lists in sorted order.
[solution gist](https://gist.github.com/wQuasar/28878d94d8a683e0afd481edd61b0f73)

**Learning:** Create a fauxHead, two travellers and an insertionPoint node pointing to fauxHead initially. Now, travel through the lists firstly checking for null cases and then checking for the comparison case.

### 2. Reverse Linked List II

LC [92](https://leetcode.com/problems/reverse-linked-list-ii/) 🟠, (Linked List)

Given a singly linked list and two indexes, return the list with the sublist between the two indexes reversed.
[solution gist](https://gist.github.com/wQuasar/2e00c54cc5513a60afaccb5f23643225)

**Learnings:** Create a fauxHead and travel to the left node. Create prev, curr and next nodes. Repeat the loop based list reversal (right - left) times.

**Errors:** 1 (variable name mismatch), 1 (logical bug), 1 (incorrect solution)

### 3. Linked List Cycle

LC [141](https://leetcode.com/problems/linked-list-cycle/) 🟢, (Linked List)

Given head of a linked list, return `true` if the there is a cycle in the list.
[solution gist](https://gist.github.com/wQuasar/71f84f2a1c811a0e96001e515ef3a224)

**Learnings:** Have a slow and fast node and proceed till fast reaches end or fast == slow. You may run into issues of nullability w.r.t. Kotlin non-null checks. We can counter this by failing fast before assignment.

**Errors:** 1 (Kotlin non-null check may result in runtime errors)

### 4. Linked List Cycle II

LC [142](https://leetcode.com/problems/linked-list-cycle-ii/) 🟠, (Linked List)

Given a linked list, return the node where cycle begins, iff cycle is there.
[solution gist](https://gist.github.com/wQuasar/6b6dd4eac5b29342651f68b579f5f59c)

**Learnings:** Detect cycle using fast and slow pointers. If cycle is there, start another pointer from head and move either of the previous pointers from the hit point one step along with the pointer at the start until they meet. Their meeting point is the cycle start point. The reason of this can be found in equations of travels by slow and fast pointers. More info [here](https://youtu.be/-YiQZi3mLq0?t=331).

**Errors:** 1 (Kotlin nullability misunderstanding - smart cast does not result to non-nullable intrinsic variable type)

### 5. Intersection of Two Linked Lists

LC [160](https://leetcode.com/problems/intersection-of-two-linked-lists/) 🟢, (Linked List)

Given heads of two linked lists, return the node at which they intersect. If they don't intersect, return null.
[solution gist](https://gist.github.com/wQuasar/21015d603e6d83cda14f8f8e5a502a13)

**Learnings:** Calculate the length of both the lists. Travel again from start of the longer list the difference b/w their lengths. Now their length difference from meeting point should be same. Move each pointer until they are same. If they get null, then they don't intersect. Take care of nullability of the `next` variable of the ListNode type.

**Errors:** 2 (misunderstanding of nullability of `next` of ListNode), 2 (logical bugs)

### 6. Remove Nth Node From End of List

LC [19](https://leetcode.com/problems/remove-nth-node-from-end-of-list/) 🟠, (Linked List)

Given head of a linked list and an integer n, remove the nth element from the end of the list.
[solution gist](https://gist.github.com/wQuasar/2d80ba670f610957e12ebdf7668e4277)

**Learnings:** Create an aheadTraveller and move it n times. Now, start another traveller from the head till the aheadTraveller reaches the end. Remove the next node of the new traveller from head. Problem comes when we need to remove the head pointer. To help with this, we will need a head pointer.

**Errors:** 1 (logical bug w.r.t. removing the head pointer)

### 7. Remove Duplicates from Sorted List

LC [83](https://leetcode.com/problems/remove-duplicates-from-sorted-list/) 🟢, (Linked List)

Given head of a sorted list, remove all duplicates from the list.
[solution gist](https://gist.github.com/wQuasar/f9497907eea29c64225b53d627c3fb07)

**Learnings:** Solution is straightforward (skip based). Problem arises when we try to counter nullability checks with edge cases (specially w.r.t. end of the list). Be agressive and proactive with these checks. For e.g. make nullability check at the start of the loop, start skip check from the next node itself instead of the same node, etc.

**Errors:** 3 (logical bugs)

### 8. Rotate List

LC [61](https://leetcode.com/problems/rotate-list/) 🟠, (Linked List)

Given head of a linked list, rotate is rightward by given k places.
[solution gist](https://gist.github.com/wQuasar/c408ffbe45d3da383633126e8c5e7d16)

**Learnings:** We can solve this by having a traveller node go ahead by the rotation count. Then, start a node pointer from the start and increase both this node and traveller till the traveller reaches the end of the list. Now, we mark the next of this starting node as `null` (marking end of the list, the original `next` is also the value to return) and traveller's `next` to head.

**Errors:** 1 (cannot break from `repeat(n)` loop), 1 (logical error)

### 9. Odd Even Linked List

LC [328](https://leetcode.com/problems/odd-even-linked-list/) 🟠, (Linked List)

Given head of a linked list, reorder the list such that all odd numbered nodes are grouped together at the start followed by all the even numbered nodes.
[solution gist](https://gist.github.com/wQuasar/c6d18ea80eefc70b5ab19a694663d13a)

**Learnings:** Create two head points for odd and even lists and a single traveller. Alternatively add the new node to the two lists. At the end, set the `next` of odd list to even list. Remember to set the `next` of even list to `null` at the end.

### 10. Palindrome Linked List

LC [234](https://leetcode.com/problems/palindrome-linked-list/description/) 🟢, (Linked List)

Given head of a linked list, return `true` if the list is palindrome.
[solution gist](https://gist.github.com/wQuasar/13768b826d3dffa11f9ff01d6daec503)

**Learnings:** Reverse the list from the centre. Readjust based on even/odd length of the list. Do normal comparison from start and centre now. If needed, reverse the list back. There's a caveat related to reversing the linked list iteratively so, double check the reversal steps.

**Errors:** 3 (logical bugs)

### 11. Add Two Numbers

LC [2](https://leetcode.com/problems/add-two-numbers/) 🟠, (Linked List)

Given two lists representing two numbers in reverse order of the digits, return a list containing the sum of these numbers in reverse order of digits.
[solution gist](https://gist.github.com/wQuasar/687db6820288bb9376e5e9bacecbf44f)

**Learnings:** Take a traveller which represents valid return list path and two travellers for each lists. Modify each list traveller's values based on current node values and nullability and keep updating the traveller path as you go along. This method avoids new node creation.

---

## Stacks and Queues

### 1. Max Stack

LC [716](https://leetcode.com/problems/max-stack/)p 🟠, (Stacks)

Create an API that acts as a stack and provides ability to return the maximum current number.
https://gist.github.com/wQuasar/a58b44c432892c013b03231981885c84)

**Learnings:** Take two stacks - one for storing the numbers and other for storing the current max number along with its count (create a data class to hold this together). There are some logical decisions that needs to be take for the different operations so, be attentive to avoid basic errors.

**Errors:** 1 (logical bug)

### 2. Evaluate Reverse Polish Notation

LC [150](https://leetcode.com/problems/evaluate-reverse-polish-notation/) 🟠, (Stack)

Given an array of strings representing tokens in Reverse Polish Notation, return the value of the RPN expression.
[solution gist](https://gist.github.com/wQuasar/14bcf1ef93cc4ff04b05435a5ec79cf5)

**Learnings:** Classic stack problem. Iterate through the array. If number, add to stack else, pop last two numbers and operate on them. Numbers are added in reverse order i.e. secondNum / firstNum after popping from stack. Trying to convert token using `toInt()` and then catching the exception (i.e. operator case) is very slow so, avoid.

### 3. Valid Parentheses

LC [20](https://leetcode.com/problems/valid-parentheses/description/) 🟢, (Stacks)

Given a string constaining only parentheses, return `true` if the brackets in the string are well-formed.

[solution gist](https://gist.github.com/wQuasar/a23c0bab75104561251ce4bec0ac4d4f)

**Learnings:** Create a stack of `Char`. Iterate through the string. If you encounter an opening bracket, add to stack else, remove the last element from stack and check that the new bracket is the complement of the removed bracket. If not, return `false`. At the end, the stack should be empty.

### 4. Simplify Path

LC [71](https://leetcode.com/problems/simplify-path/description/) 🟠, (Stack)

Given a Unix style path, convert it to simplified canonical path.
[solution gist](https://gist.github.com/wQuasar/970858b51176a847c300bbac81c3132e)

**Learnings:** Split the given path using "/". Note that the rules for Unix path to canonical path resemble a stack based operation with some token to ignore. Process each path then return the elements of the queue by joining using "/".

**Errors:** 2 (Kotlin language proficiency)

### 5. Binary Tree Level Order Traversal

LC [102](https://leetcode.com/problems/binary-tree-level-order-traversal/) 🟠, (Queue, Tree)

Given root of a binary tree, return the nodes in lists of nodes at the same level for all levels.
[solution gist](https://gist.github.com/wQuasar/7aacb5e9ea5bc8ef3a65052bdcfe62fb)

**Learnings:** This is not a recursion problem unless you really want to make it! Create a data class that holds the `TreeNode` and the depth of it's encounter. Then, create a queue and add the root to it. Now, process the queue till empty. In each process step, add the current node's value to list and add the `left` and `right` to queue. In this way nodes will be added to the queue in depth order. `depth` value in data class is used to make sure that if we run into a new depth, we need to add another list to the return list.

Another way to tackle this problem is to create two queues - one for current level and one for the next level. In each process step, we add the `left` and `right` nodes to the next level's queue and then swap the queues at the end of the step.

**Errors:** 1 (trying to reassign `val`), 1 (smart cast to complex expressions not possible), 2 (logical bugs)

### 6. Design Circular Queue

LC [622](https://leetcode.com/problems/design-circular-queue/) 🟠, (Queue, Array)

Design a queue based linear data structure of fixed length.
[solution gist](s)

**Learnings:** Start with analysing how the general case behaves and make general rules of operations from those. Then, see how the breakout cases can be handled. Start by writing API implementations of the simple cases. Run proper tests to test implementation.

**Errors:** 1 (logical bug)

### 7. Implement Queue using Stacks

LC [232](https://leetcode.com/problems/implement-queue-using-stacks/) 🟢, (Stack, Queue)

Design a queue based data structure using two stacks.
[solution gist](https://gist.github.com/wQuasar/aed6cc8f1a04dffd8c6f3495fbf4e04c)

**Learnings:** Create two stacks - one handy for addition (primary) and one handy for removal (auxilliary). Keep a bool to maintain the current handy state (addition or removal). For each new operation, if that operation is handy then, perform it. Otherwise, perform stack swap and then perform operation.

**Errors:** 2 (incorrect question interpretation)

### 8. Max Queue

LC ? 🟠, (Queue)

Implement a queue with an API to return current maximum number.
[solution gist](https://gist.github.com/wQuasar/2587dd0a0214704cb767e9974cd88c5a)

**Learnings:** Needs two queue - one for queue operations, one for maintaining current max. On dequeue, just remove element from queue and if maxQueue's first is equal to removed element, remove it as well. For enqueue, remove elements from maxQueue's head until the it's empty or the current element at front is larger or equal than the number being inserted. Then, insert the number at the tail of maxQueue.

---

## Binary Tree

### 1. Balanced Binary Tree

LC [110](https://leetcode.com/problems/balanced-binary-tree/) 🟢, (Binary Tree, Recursion)

Given the root of a binary tree, determine if it's height balanced.
[solution gist](https://gist.github.com/wQuasar/c0882edb85d397c111d81492ba76fc3e)

**Learnings:**  Recursive solution in which we firstly return 0 for leaf node. Then we check the left right and right height and see if their difference is more than 1. If yes, return -1 (fail fast) else return the max of left or the right height.

**Errors:** 1 (logical bug)

### 2. Symmetric Tree

LC [101](https://leetcode.com/problems/symmetric-tree/description/) 🟢, (Binary Tree, Recursion)

Given the root of a binary tree, test if the tree is vertically symmetric.
[solution gist](https://gist.github.com/wQuasar/574c4eced0b3fc3eedb6d55beeb3986d)

**Learnings:** A bit tricky to start the problem. Note that we need to check value on the left and right of the root using two pointers. We can simplify this by passing both these nodes to a single function and check if the values are same. If yes, we can check the same for their left and right subtrees in mirror fashion. The mirror fashion movement works because we initially gave the function left and right subtrees of the `root`.

Take care of proper nullbility assurance here.

**Errors:** 2 (nullability assurance failures)

### 3. Lowest Common Ancestor of a Binary Tree

LC [236](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) 🟠, (Binary Tree, Backtracking)

Given root of a binary tree and two nodes p and q guranteed to be in the tree, find the lowest common ancestor node of p and q in the tree.
[solution gist](https://gist.github.com/wQuasar/88697732fb6a79ea2fca882253c7413d)
[solution gist (magic)](https://gist.github.com/wQuasar/751b5accf4c94509e4b58e94d75efef7)

**Learnings:** The logic relies on finding one of the nodes by inorder traversal. When found, set a global 'lookupNode' as the other node and then search for it firstly in the nodes below the found node and then travel up the call stack. This up movement tries to put the current node as probable candidate so, we'll also need to pass the 'parent'.

There's another simlified algorithm that works on 'mogic'.

**Errors:** 2 (Kotlin nullability related errors)

### 4. Binary Tree Paths

LC [257](https://leetcode.com/problems/binary-tree-paths/) 🟢, (Binary Tree, Recursion)

Given root of a binary tree, return all root to leaf paths in any order.
[solution gist](https://gist.github.com/wQuasar/ba58aca721e9b9ded437034c00ceceee)

**Learnings:** The logic relies on travelling on each node until we reach leaf nodes at which point we return a list of list containing that leaf node. While returning in the recursion, we just add the current element to the travelled lists. Make sure that the code is sound w.r.t. to Kotlin language rules before subitting.

**Errors:** 1 (variable name mismatch), 1 (incorrect logic w.r.t. return type)

### 5. Path Sum

LC [112](https://leetcode.com/problems/path-sum/) 🟢, (Binary Tree, Recursion)

Given root of a binary tree and a target sum, return `true` if there exists a root-to-leaf path which is equal to the target sum.
[solution gist](https://gist.github.com/wQuasar/3a519d90ef9395c751a835a83438ca61)

**Learnings:** Traverse each node while reducing the current node's val from targetSum. If we reach a leaf node and target sum is equal to that leaf node's val, we return true.

**Errors:** 1 (logical error) 

### 6. Binary Tree Inorder Traversal

LC [94](https://leetcode.com/problems/binary-tree-inorder-traversal/description/) 🟢, (Binary tree)

Given root of a binary tree, return inorder traversal without using recursion.
[solution gist](https://gist.github.com/wQuasar/33059a22b991d10b6bf9235a1f299f68)

**Learnings:** Slightly tricky logic - we keep adding left children to stack till we can. When left becomes null, we pop the stack and move to the right child. If right child is empty, we pop again else, we try to move as much left as possible in that branch. In this way, we traverse in proper in-order fashion.

### 7. Binary Tree Preorder Traversal

LC [144](https://leetcode.com/problems/binary-tree-preorder-traversal/description/) 🟢, (Binary Tree)

Given the root of a binary tree, return the preorder traversal without using recursion.
[solution gist](https://gist.github.com/wQuasar/5a68f60ead5a0ad4010d4c1a100a5f68)

**Learnings:** The solution is trivial as the traversal follows stack rules directly. Just create a stack and add the root node. Now, process the stack until empty by first adding the val of top of the stack entry and then adding the right child followed by the left child to the stack.

### 8. Inorder Successor in Binary Tree

LC [285](https://leetcode.com/problems/inorder-successor-in-bst/)p 🟠, (Binary Tree)

Given the root of a binary tree and node, return the next inorder successor of the given node.
[solution gist](https://gist.github.com/wQuasar/ab0207ab75d7015708246c2a30441edf)

**Learnings:** Firstly, find the node. Once found, try to find the leftmost node in the right subtree of the found node. If not, return the node itself. This will indicate to the parent recursion calls that the node was found so that they can trigger finding the successor. Note that in inorder traversal, if the node is found in the left traversal then, the node itself would be the next successor.

### 9. Construct Binary Tree from Preorder and Inorder Traversal

LC[105](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) 🟠, (Binary Tree)

Given two arrays containing preorder and inorder traversal of a binary tree, construct and return the root of the binary tree.
[solution gist](https://gist.github.com/wQuasar/c9d5c62967a93f7f2d419438b6e4705d)

**Learnings:** The first value of preorder traversal is the root. Look for that value in inorder. The numbers to the left of that value in inorder traversal are the left sub-tree and the numbers to the right of that value are in the right sub-tree. Use this notion repeatedly. Know that as you do divide and conquer, the progression through the pre-order traversal will be from start to end so you can keep a global variable to track it.

Your recursion function can take the start and end indexes in the inorder traversal for the current sub-tree. Note that the root of this subtree will always be the current first element in the preorder traversal.

**Error:** 1 (silly logical bug)

### 10. Construct Binary Search Tree From Preorder Traversal

LC [1008](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/) 🟠, (BST)

Given preorder traversal of a Binary Search Tree, reconstruct the binary tree from it and return it's root.
[solution gist](https://gist.github.com/wQuasar/ba063cd6fb491cb8352966aa83c51749)

**Learnings:** The first value of the preorder traversal is the root. Since the tree is BST, we can now search for value in the remaining pre-order traversal which is greater than the root value. The values towards right of this value (inclusive) would be in the right sub-tree and the values towards the left of this value would be in the left sub-tree. This property would be followed by all the sub-trees.

In your recurse function, you can pass the start and end indexes of the preorder traversal. The root of the subtree would always be the first value. The rest of the values would follow the above property recursively.

**Errors:** 2 (logical bugs)

### 11. Flatten Binary Tree To Linked List

LC [114](https://leetcode.com/problems/flatten-binary-tree-to-linked-list/description/) 🟠, (Binary Tree)

Given the root of a binary tree, flatten it into a linked list (using the same TreeNode) which represents the preorder traversal of the tree in O(1) space.
[solution gist](https://gist.github.com/wQuasar/648ba536f37b291c1ca0f013219b36c1)

**Learnings:** Try with smaller node types. The gist of the solution is that we need flatten left subtrees of each node. This flattened tree should then be added between this node and the right sub-tree of this node. Therefore, the flattened subtree should return rightmost node. Look how we can achieve this with the simplest of tree types and then write your recursion from there.

**Errors:** 1 (Kotlin nullability check failure)

### 12. Binary Tree Right Side View

LC [199](https://leetcode.com/problems/binary-tree-right-side-view/description/) 🟠, (Binary Tree)

Given the root of binary tree, print the right side view of the tree.
[solution gist](https://gist.github.com/wQuasar/72e80526860b785bbe67e82d60932191)

**Learnings:** Traverse as much right as possible and put the elements in a global list. Then, travel in the left sub-tree. If the height of current node is greater than the global list size then this means this element needs to be in the list. So, the recursion works by firstly checking if the current node belongs in the list and then traverse right followed by left traversal.

### 13. Diameter of Binary Tree

LC [543](https://leetcode.com/problems/diameter-of-binary-tree/) 🟠, (Binary Tree)

Given the root of binary tree, return the lenght of the maximum path between any two nodes (this path may or may not pass through the root).
[solution gist](https://gist.github.com/wQuasar/17043ea540680f286626e4ec987426b1)

**Learnings:** You just need to calculate the depth from each node for each of it's left and right subtree. Add these and compare it with the global maximum. At the end of the recursion, return the maximum of left and right traversal. Know that since we calculate the depth for each node, we do not need to pass the depth of the current node to recursion. We only care about the depth returned by the sub-tree traversal.

---

## Heaps

### 1. Merge K Sorted Lists

LC [23](https://leetcode.com/problems/merge-k-sorted-lists/description/) 🔴, (Heap, Linked List)

Given an array of k sorted linked lists, merge the lists and return the head.
[solution gist](https://gist.github.com/wQuasar/140dc0975a5fa37766ac2ac810f2da23)

**Learnings:** Create a min-heap of lists with comparator for first element. Keep removing min elements (list) from the heap, add it's first element to current list and then adding it back to the heap if it has more elements. Do it until the heap is empty.

**Errors:** 1 (code syntax error, used `size` in linked-list!)

### 2. Sort K-Sorted Array

LC ? 🟠, (Heap)

Given an array where each number is at most k positions away from it's sorted position, sort the array.
[solution gist](https://gist.github.com/wQuasar/27edee0f6873ed13b1d47b6f0f6cf290)

**Learnings:** To find the correct position of the first element, we just need to find minimum within the first k + 1 elements. We can create a heap of size k + 1, add numbers to it and keep popping it at each iteration until we've added all numbers to the heap. Notice that the heap has a copy of the numbers so you can directly replace the numbers in the array.

**Errors:** 1 (logical bugs)

---

## Searching

### 1. Find First and Last Position of Element in Sorted Array

LC [34](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) 🟠, (Binary Search)

Given an array of integers and a target num, return the first and last position of target in the array.
[solution gist](https://gist.github.com/wQuasar/6965b6842e0da9ec057c80838387969c)

**Learnings:** This can be solved using two iterative sections of the classical binary search algorithm. One for first occurence and the other for last occurence. Look out for OBOBs and dryrun your logic to find errors before they occur.

**Errors:** 1 (silly code bugs), 1 (logical bug)

### 2. Search in Rotated Sorted Array

LC [33](https://leetcode.com/problems/search-in-rotated-sorted-array/description/) 🟠, (Binary Search)

Given an array possibly rotated at an index k and a target number, return the index of the target number.
[solution gist](https://gist.github.com/wQuasar/2e34ede8708f35f05fff26ef6c739ac7)

**Learnings:** Search for the pivot point using binary search. The check condition might be slightly tricky. Look in which section the target may reside and then do regular binary search.

**Errors:** 1 (undeclared variable use), 1 (silly syntax error), 1 (OBOB), 1 (trial and error success)

### 3. Search a 2D Matrix

LC [74](https://leetcode.com/problems/search-a-2d-matrix/) 🟠, (Search)

Given a 2D sorted array in which each first entry of each row is more than last entry of previous row and a target num, return whether the target is in the given matrix.
[solution gist](https://gist.github.com/wQuasar/7c6e3f58f22e00ec44fe767d35ac21b7)

**Learnings:** Firstly, find the row in which the number may belong using binary search and then find the coloumn in that row for the target number. Pretty easy to cause OBOBs so, look out for those.

**Errors:** 2 (logical bugs)

### 4. Kth Largest Element in an Array

LC [215](https://leetcode.com/problems/kth-largest-element-in-an-array/description/) 🟠

Given an array of integers and an integer k, return the kth largest element in the array.

**Learnings:** TBD

---

## Hash Tables

### 1. Groups Anagrams

LC [49](https://leetcode.com/problems/group-anagrams/) 🟠, (Hash Table)

Given an array of strings, group the anagrams together and return them.
[solution gist](https://gist.github.com/wQuasar/d4e1b523fc4d0803e077e1ad43376496)
[solution gist (esoteric)](https://gist.github.com/wQuasar/f310b617bc9d85bd471784d4cf8e9c8b)

**Learnings:** We can create a function to calculate a new hash of the string and go for doing anagram check iff the length and hash are both equal for two strings. Anagram check can be done using character count in array. Rest is implementation dependent.

There is another implementation of the solution but, it's slightly esoteric and possibly incorrect but it shows good use of language structure.

**Errors:** 2 (silly code bugs)

### 2. Palindrome Permutation

LC [266](https://leetcode.com/problems/palindrome-permutation/editorial/) 🟢, (Set, Arrays)

Given a string, determine if a permutation of the string could be a palindrome.
[solution gist](https://gist.github.com/wQuasar/0569712812bd4601e97936c931ef6ffa)

**Learnings:** Required condtion is - if the string length is even then, all characters must appear even no. of times. If the string length is odd then, only 1 character can appear odd no. of times.

**Errors:** 2 (logical errors) 

### 3. Ransom Note

LC [383](https://leetcode.com/problems/ransom-note/) 🟢, (Arrays)

Given a ransom note string and a magazine string, return if we can construct the ransom note from the magazine string.
[solution gist](https://gist.github.com/wQuasar/092f90863b32a6cf89cdf75780f3c1ce)

**Learnings:** Count the characters magazine string in an array. Return `false` if the magazine count array runs out while counting down the ransom note string.

**Errors:** 1 (variable name mismatch)

### 4. LRU Cache

LC [146](https://leetcode.com/problems/lru-cache/) 🟠, (HashMap, Linked List)

Create a LRU based caching data structure.
[solution gist](https://gist.github.com/wQuasar/7d7f3a6dfa6c660e3d211273965f1d56)

**Learnings:** Various data structures can be used but, each have it's own drawbacks. To use best of both worlds, we can use a HashMap to allow us to get quick access along with a self-managed doubly linked list. The map's value woule be the nodes of this list. Coding this without OBOBs might pose a challenge so review properly.

**Errors:** n (extreme trial and error)

### 5. Top K Frequent Elements

LC [347](https://leetcode.com/problems/top-k-frequent-elements/) 🟠, (Hash Table)

Given an array of integers and a number `k`, return the `k` most frequent elements in the array.

**Learnings:** TBD

**Errors:** 1 (Kotlin nullability checks)

### 6. Minimum Window Substring

LC [76](https://leetcode.com/problems/minimum-window-substring/) 🔴, (Sliding Window, String, Hash Table)

Given two strings `s` and `t`, return the minimum window substring in `s` such that every character in `t` is included in it.
[solution gist](s)

**Learnings:**

**Errors:** (minor trial and error), 2 (variable name mismatch), 1 (logical error)
