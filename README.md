# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

  - asymptotic analysis is used to compare growth rates for algorithms. This means that constant factors and lower order factors are ignored. a function that has a practical runtime of 2n^2 + 5 would have a much better performance on smaller data sets than a fuction with a runtime of 4242n + 7log(n) + 5555, even if their asymptotic complexities would be evaluated to O(n^2) and O(n) respectively.
 
  - asymptotic analysis operates under assumptions about the data set used, ie best case, worst case, average case. In reality data used may adhere to certain patterns, such as always being partially or nearly sorted. algorithms that have good best case but bad average or worst case complexity may be faster on said data sets, while an algorithm with the same best worst and average case may be less effective. Asymptotic analysis is a tool to quantify and compare algorithms based on assumptions that in reality are not true. This means the less a person understands about asymptotic complexity, the more misleading it will be. It does not lie, but the truth it portrays may not be immediately obvious. It gives a heirarchy of complexities, but this heirarchy is only truly aplicable to the cases for which it evaluates. Practical applications of algorithms are much more complicated, as I've demonstrated with my examples, and when working within finite data sets, the asymptotic complexities may not hold true in their present heirarchy of "better" and "worse"
 
  - hardware and environmental factors can have an affect on the time taken and can affect different algorithms and different implementations different. I am currently in computer organization while taking this class so it's fun to see these two courses intersect like this. The architecture of a system can work to the advantage or disadvantage of an algorithm. For example, non-contiguous storage access may take longer or result in more misses than something that uses contiguous storage, a factor not considered by asymptotic complexity.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

  a binary search has a time complexity of log2(n)
  plug in 5 seconds and 1000 elements to determine a theoretical constant factor
  5 = (k)log2(1000)
  5 = (k)9.97
  k = .5
  plug back in 10000
  x = (.5)log2(10000)
  x = (.5)13.29
  x = 6.65 seconds

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

  - The obvious reason that comes to mind is that perhaps the search tree with 10k elements is extremely unbalanced, leading to a structure more akin to a list than a binary search tree. This can cause search time to go from logarithmic to linear, a significantly worse case. To expand, if the list of 1,000 elements was perfectly balances, it was averaging .5 seconds per layer (as shown in math above). Now if our tree of 10k elements was completely unbalanced, meaning 10k layers, that would give a search time of up to 5,000 seconds, just from poor balancing, which could more than account for the unpredictable behavior.
  - another possibility could be that the element in the 1k search was closer to the root, while the element searched for in the 10k tree was a lot further from the root
  - a final possible reason could be the hardware and environmental factors discussed in question 1. Other processes running at the same time could take resources away from running the search algorithm, data distribution could make certain elements more difficult to access, and the increases size of the data set may have unforseen consequences if the algorithm is not implemented accordingly.

prior knowledge and lecture material were able to cover most of this assignment, however I did do further research on the hardware and environmental effects on time complexity
 
I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Add your answers to this markdown file.
