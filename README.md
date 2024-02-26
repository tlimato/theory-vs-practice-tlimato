[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/FgMJElkj)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.
  ## Sol
  1) Constant Factors and Lower Order Terms. Really high constant factors or lower order terms that are ignored when simplifying for the sake of an asymptotic expression can cause very extreme time differences
  2) Memory and cache. Innefficient memory utilization and cache misses can increase time significantly.
  3) Distribution of Inputs and Special Cases. Already sorted, reverse sorted, or other special cases can drastically impact the efficiency and runtime.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.
  ## Sol
  The asymptotic complexity of search in a binary search tree is typically O(log⁡n), where nn is the number of elements in the tree. This means that as the size of the tree increases, in other words the time taken to search for an element grows logarithmically. if solving with 1000 elements takes 5 seconds, we can use the same logarithmic complexity to calculate 10,000.  Since we're increasing the size of the tree by an order of magnitude; time should increase from 5 to 6 seconds


- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

  ## Sol
  The tree being unbalanced is a big factor in the time increase. For example, The data distribution of the additional elements could heavily skew the date to one side of the tree causing massive inefficiencies. It could also be as convulated as memory issues.

Add your answers to this markdown file.
