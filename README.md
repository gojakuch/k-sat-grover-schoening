# Solving k-SAT problems with Grover's and Schöning's Algorithms
In this notebook, I present you three (actually, even more) approaches to SAT problems. These are classical Schoening's algorithm, quantum Grover's algorithm, and a combination of the two. Of course, the main purpose, to my mind, was to shed some light on the combined approach, as the first two are generally mainstream. For the proposed 9-SAT problem, with Grover, we can solve it in 3-4 quantum oracle queries, while with the combined approach we only need one and then one additional classical algorithm iteration. This sounds quite inspiring, however, the resulting quantum oracle that we use in the latter is implemented so computationally hard that the method becomes, to my mind, unusable. Surely, if we do not take the insides of the oracle to account, then such a method is overwhelmingly efficient. An alternative combined approach which is to apply Grover's search to the space of random seeds is much better in any case.

If you want to read more on what SAT problems are, you can do it [on Wikipedia](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem). SAT problems are basically systems of logical statements.

This notebook can obviously be used as a tutorial for combining Schoening's and Grover's methods, if the reader is aware of the Grover's Algorithm and 3-SAT (k-SAT) problems.

by Atell Krasnopolski, 2022

## Sources
Even though this algorithm (combined Schöning's and Grover's approaches) is quite frequently mentioned, I haven't found its implementation, detailed description, or pseudocode anywhere. In fact, I only used the following sources and simply derived everything myself using those descriptions. Frankly, this was all quite intuitive and I haven't proven resulting algorithms formally, so there can be some mistakes (if so, please let me know).

1) [Notes on the Classical Schöning's Algorithm](http://cs.yale.edu/homes/spielman/365/schoening.pdf)

2) [A Particularly Useful StackExchange Question](https://quantumcomputing.stackexchange.com/questions/14293/grovers-search-applied-to-sch%C3%B6nings-algorithm)

3) [Qiskit Tutorial on Grover's Algorithm](https://learn.qiskit.org/course/introduction/grovers-search-algorithm), specifically, this paragraph:

"It may not be obvious at first glance, but we can actually combine Grover and Schöning's algorithms to get something even better than either individually. If you create a circuit that carries out the bit-toggling part of Schöning's algorithm, you can use this as the oracle and use Grover's algorithm to find the best "initial guess"."

4) [Another Qiskit Tutorial on Gorver's Algorithm](https://qiskit.org/textbook/ch-algorithms/grover.html)
