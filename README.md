
# Grover's Algorithm


## What is Grover's Algorithm?

Lov Grover published "Grover's Algorithm" in a 1996 paper. It has become one of the most famous examples of a quantum search algorithm. This quantum algorithm helps to solve a problem that traditional computers will always struggle with: unstructured search.

If I wanted to find a specific card in a deck of shuffled cards I would have to check *on average* 52/2 = ~26 cards before finding the card I'm looking for (ie. n/2 where n = our number of entries). In the worst case I may have to check all 52 cards before finding what I'm looking for. This is due to the linear nature of searching unstructured data. This is the same way traditional computers are forced to search (specifically when the data being searched is unstructured) which translates to O(n) iterations of search. Traditional computers struggle with unstructured searching because there are no speed ups to be found. It doesn't make a difference if we start our search at the top of our deck, in the middle, or at the bottom; our target card is no more likely to be in any of those places. A whole section of math and computer science has been dedicated to studying, classifying, and working towards more efficient solutions of these types of problems, referred to as NP-complete problems. 

Grover's algorithm has been proved to improve the efficiency of unstructured search to O(sqrt(n)). While this speedup does not have much of an impact when n is small, as n grows this speedup from n to sqrt(n) is considerable. One of the potentially most threatening implementations of Grover's would be to brute-force a 256-bit symmetric cryptographic key given the quadratic speedup that would be seen over traditional computers. 




## Grover's Implementation
For this implementation of Grover's algorithm we will be handling a variable 2-5 qubits depending on user input. Grover's algorithm works by applying an oracle that adds a negative phase to the desired solution state and then applying a set of amplitude amplification gates to maximize the probability of measuring the expected output state. This set of steps is repeated $\pi/4\sqrt{n}$ times where n = our search space (2 ^ # qubits).

As is all quantum programming, we are utilizing sets of gates to maximize the probability that when we collapse and measure our qubits that they are in the expected solution state.

General Grover's Steps:
1. Initialize all qubits in the system to a uniform superposition
2. Apply the "Grover Iteration" $\pi/4\sqrt{n}$ times 
	1. Apply oracle gates
	2. Apply amplitude amplification gates
3. Measure the resulting states

## How To Run
In this repository you will find a jupyter notebook which will allow you to run Grover's algorithm on either a simulated quantum computer or on quantum computing hardware. This notebook can be used on [Google Colab](https://colab.research.google.com/) for easy execution. The python code is also attached and is runnable locally, the `requirements.txt` file contains all required libraries.