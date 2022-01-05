# Tabu Search on Product Line Design

![](images/Brute%20Force%20versus%20Tabu%20Search.JPG)

## Development
This work was part of the seminar thesis I wrote in the Fall semester 2021 at the Chair of Revenue Management [Prof. Dr. Cornelia Schön](https://www.bwl.uni-mannheim.de/schoen/ "Prof. Dr. Cornelia Schön"), University of Mannheim on product line design optimization. 

## Background

In this project, I tried to solve Product Line Design (PLD) problem using Tabu Search (TS). TS is a heuristic that has been applied to solve problems in various fields. However, in the context PLD, to the best of my knowledge, as of December 2021, there is only one paper that implements TS to solve an instance of the general PLD problem. The author shows that TS performs better than Genetic Algorithm and Simulated Annealing even when parameters of the original problem are varied.
* Tsafarakis, Stelios; Zervoudakis, Konstantinos; Andronikidis, Andreas (2021): Optimal product line design using Tabu Search. In Journal of the Operational Research Society, pp. 1–12.

## Demonstration
![](images/Tabu%20Search%202D%20Demonstration.gif)

TS is able to identify the global optimum in this 2D multimodal function thanks to its **Tabu Move** feature. Once a certain move is kept in memory as a tabu move, the algorithm doesn't allow dialing back to the tabu move anymore. Thus further exploration in the search space is possible. In our case, as the algorithm finds lower points beyond the tabu move, we can say that the tabu move is the global optimum. This is indeed the case because the other optimum is only the local optimum.

If we consider Greedy Approach, there are two potential issues. First, Greedy Approach could stop at the local optimum. If we start on the very left of our 2D example, we will stop at the local optimum. Second, Greedy Approach is blind to further search space. In Greedy Approach, there is no mechanism that allows acceptance of solutions that are less than the previous one. Suppose we started Greedy Approach in the middle of the function, we would end up at the global optimum. But actually we don't know that.

## Environment
For this particular project, I use Microsoft Excel to implement TS. The file is visible in the main tab or can be accessed via this [link](https://github.com/iamphuc/Tabu-Search/blob/main/OPM_781_Software_Nguyen_Phuc.xlsx)

## License
This repository contains a [MIT LICENSE](https://github.com/iamphuc/Tabu-Search/blob/main/LICENSE)
