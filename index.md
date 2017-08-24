---
layout: default
---
# [](#header-1)Me, Here!

Hi, my name is Mingya Ma. I am a senior student at University of Minnesota studying computer science. I am currently looking for jobs in software engineering and related fields. You can reach  me at maxxx950@umn.edu or 585-7481507! Welcome to have a look at my [LinkedIn profile](https://www.linkedin.com/in/mingya-m-273317a1), and you can as well view my resume on LinkedIn! 

# [](#header-1)LCs Here :) 

## [](#header-2) DFS traversals
### [](#header-3) Basic DFS
DFS traversal is a super basic and useful hack to solve tree problems or related. Good examples of such problems are LC 104 [Maximum Depth of Binary tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/) and [Convert BST to Greater Tree](https://leetcode.com/problems/convert-bst-to-greater-tree/description/). Max Depth of BT should be very straight forward, using the DFS. Every time the function is poped from the recursion stack, return current depth + 1. If null node is reached, return 0 as current depth. Return all the depths to ```Math.max()```, which will filter out the branches with smaller depthes. Convert BST to Greater Tree is a little tricky. One place people(like me) may ignore is, when the DFS traversed all the nodes on the right side, the pointer will go back to the right most node on the left side, which does not have the previous value from the right side. To avoid this error, I used a class attribute called ```sum``` to record previous sums. When the node pointer go back to root and started the traverse the left side of tree, I still have the previous sum. ETC...
### [](#header-3) Advanced DFS
Two questions from LC:[Recover Binary Search Tree](https://leetcode.com/problems/recover-binary-search-tree/) and [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/discuss/) are good examples of solving BST problems using in-order traversal. One trick that are used in solutions of these two problems are: in-order traversal of BST follows the increasing order of node values in BST! [Recover Binary Search Tree](https://leetcode.com/problems/recover-binary-search-tree/) basically trace back one previous node to find the swapped elements since the previous one element value should be greater than the current root value in BST. [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/discuss/) is much straight forward, just go to the left most node, and count down for k nodes, which gives us the Kth Smallest Node in BST! Ez Ez Ez! 
### [](#header-3) More DFS
BST problems some times can be solved by DFS along with other algorithms to optimalize the solution. For instance, [House Robber III](https://leetcode.com/problems/house-robber-iii/discuss/) utilize both DP and In-Order Traversal. A good step-by-step explanation by [Renpeng Fang](https://discuss.leetcode.com/user/fun4leetcode) can be found here [Step by step tackling of the problem](https://discuss.leetcode.com/topic/39834/step-by-step-tackling-of-the-problem).
For instance:
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {    
    public int rob(TreeNode root) {
        return rob(root, new HashMap<TreeNode, Integer>());
    }
    
    public int rob(TreeNode root, Map<TreeNode, Integer> nodeToRobbedMoney) {
        if (root == null) return 0;
        if ( nodeToRobbedMoney.containsKey(root)) return nodeToRobbedMoney.get(root);
        int val = 0;
        
        if (root.left != null) 
            val += rob(root.left.left, nodeToRobbedMoney) + rob(root.left.right, nodeToRobbedMoney);
        if (root.right != null) 
            val += rob(root.right.left,nodeToRobbedMoney) + rob(root.right.right,nodeToRobbedMoney);
        
        val = Math.max(val + root.val, rob(root.left,nodeToRobbedMoney) + rob(root.right,nodeToRobbedMoney));
        //every time we compute a new cost of current node, we put it in the map. 
        nodeToRobbedMoney.put(root, val);
        
        return val;
    }
}
```

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [](#header-1)Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## [](#header-2)Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### [](#header-3)Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [](#header-4)Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [](#header-5)Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [](#header-6)Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
