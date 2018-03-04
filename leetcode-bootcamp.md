# Leetcode Bootcamp

## Array
- [x] [Two Sum ]( https://leetcode.com/problems/two-sum/ )
 <details>
 <summary>Answer</summary>
 <p>
  ```js
     /**
      * @param {number[]} nums
      * @param {number} target
      * @return {number[]}
      */
     var twoSum = function(nums, target) {
         let seen = { } 
         for (let i = 0; i < nums.length; i++) {
             let curr = nums[i];
             if (target - curr in seen) return [i, seen[target - curr]]
             seen[curr] = i
         }
         return false;
     };
  ``` 
 </p>
</details>
- [x] [Best Time to Buy and Sell Stock ]( https://leetcode.com/problems/best-time-to-buy-and-sell-stock/ )
 <details>
 <summary>Answer</summary>
 <p>
  ```js
    /**
     * @param {number[]} prices
     * @return {number}
     */
    var maxProfit = function(prices) {
      let p1 = 0;
      let p2 = 1
      let maxProfit = 0;
      while (p2 < prices.length) {
          if (prices[p1] > prices[p2]) {
              p1 = p2;
          } else {
              let diff = prices[p2] - prices[p1]
              maxProfit = maxProfit > diff ? maxProfit : diff 
          }
          p2++
      }
        return maxProfit
    };
  ``` 
 </p>
</details>
- [x] [Contains Duplicate ]( https://leetcode.com/problems/contains-duplicate/ )
 <details>
 <summary>Answer</summary>
 <p>
    ```js
    /**
     * @param {number[]} nums
     * @return {boolean}
     */
     var containsDuplicate = function(nums) {
        let seen = new Set();
        for (let i = 0; i < nums.length; i++) {
            if (seen.has(nums[i])) return true;
            seen.add(nums[i])
        }
        return false;
     }; 
    ``` 
 </p>
</details>
- [x] [Product of Array Except Self ]( https://leetcode.com/problems/product-of-array-except-self/ )
 <details>
 <summary>Answer</summary>
 <p>
    ```js
    /**
    * @param {number[]} nums
    * @return {number[]}
    */
     var productExceptSelf = function(nums) {
       let product = 1;
       let result = []
       for (let i = 0; i < nums.length; i++) {
           result[i] = product;
           product *= nums[i]
       }
       product = 1
       for (let i = nums.length - 1; i >= 0; i--) {
           result[i] *= product;
           product *= nums[i]
       }
       return result;
    };
    ```
</p>
</details>
- [  ] [Maximum Subarray ]( https://leetcode.com/problems/maximum-subarray/ )

- [  ] [Maximum Product Subarray ]( https://leetcode.com/problems/maximum-product-subarray/ )
- [  ] [Find Minimum in Rotated Sorted Array ]( https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/ )
- [  ] [Search in Rotated Sorted Array ]( https://leetcode.com/problems/search-in-rotated-sorted-array/ )
- [  ] [3Sum ]( https://leetcode.com/problems/3sum/ )
- [  ] [Container With Most Water ]( https://leetcode.com/problems/container-with-most-water/ )


## Binary

- [  ] [Sum of Two Integers ]( https://leetcode.com/problems/sum-of-two-integers/ )
- [  ] [Number of 1 Bits ]( https://leetcode.com/problems/number-of-1-bits/ )
- [  ] [Counting Bits ]( https://leetcode.com/problems/counting-bits/ )
- [  ] [Missing Number ]( https://leetcode.com/problems/missing-number/ )
- [  ] [Reverse Bits ]( https://leetcode.com/problems/reverse-bits/ )

---

## Dynamic Programming

- [  ] [Climbing Stairs ]( https://leetcode.com/problems/climbing-stairs/ )
- [  ] [Coin Change ]( https://leetcode.com/problems/coin-change/ )
- [  ] [Longest Increasing Subsequence ]( https://leetcode.com/problems/longest-increasing-subsequence/ )
- [  ] [ Word Break Problem ]( https://leetcode.com/problems/word-break/ )
- [  ] [ Combination Sum ]( https://leetcode.com/problems/combination-sum-iv/ )
- [  ] [ House Robber ]( https://leetcode.com/problems/house-robber/ )
- [  ] [ House Robber II ]( https://leetcode.com/problems/house-robber-ii/ )
- [  ] [ Decode Ways ]( https://leetcode.com/problems/decode-ways/ )
- [  ] [ Unique Paths ]( https://leetcode.com/problems/unique-paths/ )
- [  ] [ Jump Game ]( https://leetcode.com/problems/jump-game/ )



## Graph

- [  ] [ Clone Graph ]( https://leetcode.com/problems/clone-graph/ )
- [  ] [ Course Schedule ]( https://leetcode.com/problems/course-schedule/ )
- [  ] [ Pacific Atlantic Water Flow ]( https://leetcode.com/problems/pacific-atlantic-water-flow/ )
- [  ] [ Number of Islands ]( https://leetcode.com/problems/number-of-islands/ )
- [  ] [ Longest Consecutive Sequence ]( https://leetcode.com/problems/longest-consecutive-sequence/ )
- [  ] [ Alien Dictionary (Leetcode Premium) ]( https://leetcode.com/problems/alien-dictionary/ )
- [  ] [ Graph Valid Tree (Leetcode Premium) ]( https://leetcode.com/problems/graph-valid-tree/ )
- [  ] [ Number of Connected Components in an Undirected Graph (Leetcode Premium) ]( https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/ )


## Interval

- [  ] [ Insert Interval ]( https://leetcode.com/problems/insert-interval/ )
- [  ] [ Merge Intervals ]( https://leetcode.com/problems/merge-intervals/ )
- [  ] [ Non Overlapping Intervals ]( https://leetcode.com/problems/non-overlapping-intervals/ )
- [  ] [ Meeting Rooms (Leetcode Premium) ]( https://leetcode.com/problems/meeting-rooms/ )
- [  ] [ Meeting Rooms II (Leetcode Premium) ]( https://leetcode.com/problems/meeting-rooms-ii/ )


## Linked List
- [x] [ Reverse a Linked List ]( https://leetcode.com/problems/reverse-linked-list/ )
<details>
 <summary>Answer</summary>
  <p>
     ```js
        var reverseList = function(head) {
           if (!head || !head.next) return head;
           let rev = head,
               curr = head.next;
               rev.next = null;
           while (curr) {
               let s = curr.next;
               curr.next = rev;
               rev = curr
               curr = s;
           }
          return rev; 
        };
     ```
  </p>
</details>

- [x] [ Detect Cycle in a Linked List ]( https://leetcode.com/problems/linked-list-cycle/ )
<details>
<summary>Answer</summary>
<p>
  ```js
   if (!head || !head.next) return false;
     let slow = head;
     let fast = head.next;
     while (fast && fast.next) {
         if (slow === fast) return true;
         slow = slow.next
         fast = fast.next.next;
     } 
    return false;
  ```
 </p>
</details>

- [x]  [Merge Two Sorted Lists ]( https://leetcode.com/problems/merge-two-sorted-lists/ )
<details>
  <summary>Answer</summary>
  <p>
  ```js
     /**
     * Definition for singly-linked list.
     * function ListNode(val) {
     *     this.val = val;
     *     this.next = null;
     * }
     */
    /**
     * @param {ListNode} l1
     * @param {ListNode} l2
     * @return {ListNode}
     */
    var mergeTwoLists = function(l1, l2) {
    if (!l1 && !l2) return null
    if (!l1) return l2
    if (!l2) return l1
    let head = null;
    if (l1.val <= l2.val) {
        curr = l1
        head = l1;
        l1 = l1.next;
    } else {
        curr = l2
        head = l2
        l2 = l2.next
    }
    while (l1 && l2) {
        if (l1.val < l2.val) { 
            curr.next = l1
            l1 = l1.next
        }
        else {
            curr.next = l2
            l2 = l2.next
        }
        curr = curr.next
    }
    l1 = !l1 ? l2 : l1
    curr.next = l1
    return head;
    }
    ```
- [  ]  [Merge K Sorted Lists ]( https://leetcode.com/problems/merge-k-sorted-lists/ )
- [x]  [Remove Nth Node From End Of List ]( https://leetcode.com/problems/remove-nth-node-from-end-of-list/ )
<details>
<summary>Answer</summary>
<p>
  ```js
     /**
     * function ListNode(val) {
     *     this.val = val;
     *     this.next = null;
     * }
     */
     /**
      * @param {ListNode} head
      * @param {number} n
      * @return {ListNode}
      */
     var removeNthFromEnd = function(head, n) {
         let curr = head;
         let length = 0;
         while (curr) {
             curr = curr.next
             length += 1
         }
         if (n === length) return head.next
         snd = head;
         let index = 0
         while (snd) {
             if (length - n === index + 1) {
                 if (!snd.next.next) {
                     snd.next = null
                      } else {
                          snd.next = snd.next.next
                          snd = snd.next.next
                      }
                      break;
                  } 
                  snd = snd.next
                  index++
              }
              return head;    
          }; 
  ```
</p>
</details>
- [  ]  [Reorder List ]( https://leetcode.com/problems/reorder-list/ )



## Matrix

- [  ] [ Set Matrix Zeroes ]( https://leetcode.com/problems/set-matrix-zeroes/ )
- [  ] [ Spiral Matrix ]( https://leetcode.com/problems/spiral-matrix/ )
- [  ] [ Rotate Image ]( https://leetcode.com/problems/rotate-image/ )
- [  ] [ Word Search ]( https://leetcode.com/problems/word-search/ )


## String

- [  ] [ Longest Substring Without Repeating Characters ]( https://leetcode.com/problems/longest-substring-without-repeating-characters/ )
- [  ] [ Longest Repeating Character Replacement ]( https://leetcode.com/problems/longest-repeating-character-replacement/ )
- [  ] [ Minimum Window Substring ]( https://leetcode.com/problems/minimum-window-substring/ )
- [  ] [ Valid Anagram ]( https://leetcode.com/problems/valid-anagram/ )
- [  ] [ Group Anagrams ]( https://leetcode.com/problems/group-anagrams/ )
- [  ] [ Valid Parentheses ]( https://leetcode.com/problems/valid-parentheses/ )
- [  ] [ Valid Palindrome ]( https://leetcode.com/problems/valid-palindrome/ )
- [  ] [ Longest Palindromic Substring ]( https://leetcode.com/problems/longest-palindromic-substring/ )
- [  ] [ Palindromic Substrings ]( https://leetcode.com/problems/palindromic-substrings/ )
- [  ] [ Encode and Decode Strings (Leetcode Premium) ]( https://leetcode.com/problems/encode-and-decode-strings/ )



## Tree

- [x] [ Maximum Depth of Binary Tree ]( https://leetcode.com/problems/maximum-depth-of-binary-tree/ )
<details>
<summary>Answer</summary>
<p>
  ```js
    /**
     * Definition for a binary tree node.
     * function TreeNode(val) {
     *     this.val = val;
     *     this.left = this.right = null;
     * }
     */
    /**
     * @param {TreeNode} root
     * @return {number}
     */
    var maxDepth = function(root) {
      const dfs = (root, sum = 0) => {
          if (!root) return sum
          sum += 1
          
          let left = dfs(root.left, sum)
          let right = dfs(root.right, sum)
          
          return Math.max(left, right)
      }  
      return dfs(root)
    };
  ```
- [x] [ Same Tree ]( https://leetcode.com/problems/same-tree/ )
<details>
<summary>Answer</summary>
<p>
  ```js 
  var isSameTree = function(p, q) {
     if (!p && !q) return true; 
     if (!p || !q || p.val !== q.val) return false;
     return isSameTree(p.left, q.left) && isSameTree(p.right, q.right)
  };
  ```
- [x] [ Invert/Flip Binary Tree ]( https://leetcode.com/problems/invert-binary-tree/ )
<details>
<summary>Answer</summary>
<p>
  ```js
    /**
     * Definition for a binary tree node.
     * function TreeNode(val) {
     *     this.val = val;
     *     this.left = this.right = null;
     * }
     */
    /**
   * @param {TreeNode} root
   * @return {TreeNode}
   */
  var invertTree = function(root) {
    if (root) {
        if (root.left || root.right) {
            temp = root.left
            root.left = root.right
            root.right = temp;
            invertTree(root.left)
            invertTree(root.right)
        }
    }
    return root;
  };
  ```
- [  ] [ Binary Tree Maximum Path Sum ]( https://leetcode.com/problems/binary-tree-maximum-path-sum/ )
- [  ] [ Binary Tree Level Order Traversal ]( https://leetcode.com/problems/binary-tree-level-order-traversal/ )
- [  ] [ Serialize and Deserialize Binary Tree ]( https://leetcode.com/problems/serialize-and-deserialize-binary-tree/ )
- [x] [ Subtree of Another Tree ]( https://leetcode.com/problems/subtree-of-another-tree/ )
<details>
<summary>Answer</summary>
<p>
  ```js
   * @return {boolean}
   */

  function isSame (s, t) {
      if (!s && !t) return true;
      if (!s || !t) return false;
      if (s.val === t.val) {
          return isSame(s.left, t.left) && isSame(s.right, t.right)
      }
      return false;
  }
  var isSubtree = function(s, t) {
      if (!s || !t) return !s && !t 
      let is = isSame(s, t)
      if (is) return true;
      let a = isSubtree(s.left, t) || isSubtree(s.right, t)
      return a;
  };
  ```
</p>
</details>
- [  ] [ Construct Binary Tree from Preorder and Inorder Traversal ]( https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/ )
- [  ] [ Validate Binary Search Tree ]( https://leetcode.com/problems/validate-binary-search-tree/ )
- [  ] [ Kth Smallest Element in a BST ]( https://leetcode.com/problems/kth-smallest-element-in-a-bst/ )
- [  ] [ Lowest Common Ancestor of BST ]( https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/ )
- [  ] [ Implement Trie (Prefix Tree) ]( https://leetcode.com/problems/implement-trie-prefix-tree/ )
- [  ] [ Add and Search Word ]( https://leetcode.com/problems/add-and-search-word-data-structure-design/ )
- [  ] [ Word Search II ]( https://leetcode.com/problems/word-search-[ii/ )

---

## Heap

- [  ] [ Merge K Sorted Lists ]( https://leetcode.com/problems/merge-k-sorted-lists/ )
- [  ] [ Top K Frequent Elements ]( https://leetcode.com/problems/top-k-frequent-elements/ )
- [  ] [ Find Median from Data Stream ]( https://leetcode.com/problems/find-median-from-data-stream/ )

