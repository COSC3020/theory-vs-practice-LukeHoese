# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

  - asymptotic analysis is used to compare growth rates for algorithms. This means that constant factors and lower order factors are ignored. a function that has a practical runtime of 3n^2 would have a better runtime on smaller data sets than a function with a runtime of 50n, even though an asymptotic analysis would result in them being O(n^2) and O(n) respectively. For example if we know that the data set we're using is only going to consist of a first middle and last initial of people, so three elements for each run, our O(n^2) runtime would actually come out to 27, while our O(n) runtime would come out to 150. 
    
  - asymptotic analysis operates under assumptions about the data set used, ie best case, worst case, average case. Real data has no adherence to these assumptions. Even random data can have patterns, and most data in practical uses is not completely random. The patterns data adheres to can also change over time which can in real time affect the performance of a given algorithm. Even tight bounds leave wiggle room for algorithms to perform better or worse depending on their practical applications. Average case complexity does not mean an implementation of that algorithm on real world data will actually average that runtime, despite its MISLEADING naming convention. Underlying patterns can lead to a much faster or slower average runtime.

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
  - another possible slow down could come from how the program interacts directly with its hardware. In a typical computer model the fastest access data has the smallest memory, and at each level of memory, storage increases but access time also increases. This means that if for example our computers cache could hold 5,000 elements of a tree, then the tree with 1,000 elements could be stored entirely in cache with a really fast access time. However if we tried to store a tree of 10,000 elements, there would not be enough room for all the elements, leaving some to be pushed back to the RAM which has a slower access time. Seeing as cache can be anywhere from 10 to 100 times faster access than RAM, this could account for why finding the element in the tree of size 10,000 would take significantly longer
  - a final possible reason could be the external hardware and software interferences. Stuff that doesn't interact with our program directly but could interfere. This could be other higher priority processes, or just how the CPU handles processes. For example if the CPU was using a round robin cycle for processes, where a search of 1000 elements can be completed within the alloted cycle time, but a search of 10000 elements could exceed the cycle time and have to wait for other processes to have their turn with the CPU, this could account for the time difference, as perhaps there are 19 other programs waiting for their 5 seconds of time with the CPU.

prior knowledge and lecture material were able to cover most of this assignment, however I did do further research on the hardware and environmental effects on time complexity. some additional information was added to environmental factors from stuff learned in COrg
 
I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Add your answers to this markdown file.
