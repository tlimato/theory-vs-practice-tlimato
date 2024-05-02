[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/FgMJElkj)
# Theory vs. Practice
## Task 1
List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.
### Sol
  1) Constant Factors and Lower Order Terms. Really high constant factors or lower order terms that are ignored when simplifying for the sake of an asymptotic expression can cause very extreme time differences
  2) Memory and cache. Inefficient memory utilization and cache misses can increase time significantly.
  3) Distribution of Inputs and Special Cases. Already sorted, reverse sorted, or other special cases can drastically impact the efficiency and runtime.
     
## Task 2

Suppose finding a particular element in a binary search tree with 1,000
elements take 5 seconds. Given what you know about the asymptotic complexity
of search in a binary search tree, how long would you guess finding the same
element in a search tree with 10,000 elements takes? Explain your reasoning.

### Sol
The asymptotic complexity of search operations in a binary search tree is typically described as $O(log n)$, where $n$ is the number of elements in the tree. This logarithmic complexity implies that the time required to search for any given element increases logarithmically with the number of elements in the tree. 

To break this down further let's go step by step using the relation of 1000 elements in 5 seconds to solve a find operation, we can approximate the find operation for the same element in a tree with 10,000 elements. When the number of elements increases to 10,000 (an increase by a factor of 10), the logarithmic complexity means that the depth of the tree—and subsequently, the maximum number of comparisons needed—increases only slightly. If we calculate the depth of the tree using $n$ to represent the number of elements we get the following:
- For $n = 1,000$, the depth is $log₂(1000) ≈ 9.966$.
- For $n = 10,000$, the depth is $log₂(10000) = 13.288$.
This is really cool because the depth increase from  roughly 10 to approximately 13.3 represents only a $33%$ increase in the depth of the tree, despite a $900%$ increase in the number of elements.
Therefore, If 1,000 elements take 5 seconds, an increase to 10,000 elements would increase the time to $5 * (13.288/9.966) ≈ 6.33 seconds$, under the assumption that all other conditions remain constant and the tree remains balanced as an unbalanced tree would cause a much more dramatic search time.

## Task 3
You measure the time with 10,000 elements and it takes 100 seconds! List 3 reasons why this could be the case, given that reasoning with the asymptotic complexity suggests a different time.

### Sol
There are quite a few things that could be causing the large increase in time relative to what was expected. Given what we discussed in class these are the three that come to mind:

### 1a. **Tree Balance**:
- **Unbalanced Tree**: If the binary search tree is not well-balanced, it might degrade to a structure similar to a linked list, especially if the data insertion order causes a skew. In such cases, the worst-case time complexity becomes $O(n)$ instead of $O(log n)$. However, given the relation of 5 seconds for 1,000  for a logarithmic relation of $O(log n)$, then if we were approximating an unbalanced tree that is using the worst-case time complexity of $O(n)$ we would expect a find operation to take 50 seconds at 10,000 elements. This isn't a likely possibility then.

### 1b. **Improper Measurement**:
- **Extra measured operations**: If the timer used when recording the time for 10,000 elements in the tree included more operations that depend on tree size other than just the search, like creating the tree (insertions for each element), and balancing the tree then we could get an execution time that is much larger than expected. Additionally, if the timer recorded the first time correctly but didn't time the larger tree correctly then this effect would be magnified.

### 2. **System Overheads**:
- **Memory Management**: Large trees might suffer from inefficient memory use, paging times, cache misses, and higher memory access times. All of these issues scale with the number of items in a tree as the tree gets larger which can amplify the slowdown of all these inefficiencies.

### 3. **Implementation Details and Inconsistencies**:
- **Recursive Overhead**: If the search algorithm is implemented recursively, the overhead of recursive calls can add significant time, especially if the compiler or runtime environment does not optimize tail recursion. Additionally, if these calls don't efficiently access memory then system overheads become a factor on top of the recursive overhead.

Add your answers to this markdown file.
