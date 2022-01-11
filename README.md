# Tabu Search on Product Line Design

![](images/Brute%20Force%20versus%20Tabu%20Search_v2.JPG)

## Development
This work was part of the seminar thesis I wrote in the Fall Semester 2021 at the Chair of Service Operations Management [Prof. Dr. Cornelia Schön](https://www.bwl.uni-mannheim.de/schoen/ "Prof. Dr. Cornelia Schön"), University of Mannheim on product line design optimization. 

## Background
The original Product Line Design (PLD) problem is the profit maximization of a 7-product line. This can be solved using commercial optimization program such as AMPL. However, for implementation purpose in Microsoft Excel, I choose to solve the profit maximiation of 1-product line. Additional information about the problem and procedure is shown in the Environment and Implementation Section.

About Tabu Search (TS), the algorithm was first introduced by Fred Glover in 1986 (Glover and Laguna, 1988). The key idea behind TS is the introduction of memorized moves, called **Tabu Move**. TS starts with a random point the search space. The algorithm then looks for neighborhood solutions. A certain number of neighborhood solutions can be specified. Once this neighborhood search is finished, the best solution is stored in memory as **Tabu Move** and the search process continues in other neighborhoods. 

**Tabu Move** essentially means moves that the algorithm cannot repeat. That prevents the sampling in the neighborhoods of already visited points. In this way, the algorithm is able to explore further solution space. The memory component of TS can also be adaptive such that new tabu moves (higher value solutions) replace the old ones. Therefore, the memory capacity can be small and the algorithm can still find the global optimal solution. 

TS has been applied to solve problems in various fields. However, to the best of my knowledge, as of December 2021, there is only one paper that applies TS in the context of PLD. In this paper, TS shows superior performance in terms of both accuracy and speed. Also, the author shows that TS performs better than Genetic Algorithm and Simulated Annealing even when parameters of the original problem are varied. 
* Tsafarakis, Stelios; Zervoudakis, Konstantinos; Andronikidis, Andreas (2021): Optimal product line design using Tabu Search. In Journal of the Operational Research Society, pp. 1–12.

## Demonstration
![](images/Tabu%20Search%202D%20Demonstration.gif)

TS is able to identify the global optimum in this 2D multimodal function thanks to its **Tabu Move** feature. Once a certain move is kept in memory as a tabu move, the algorithm doesn't allow cycling back to the tabu move anymore. Thus further exploration in the search space is possible. In our case, as the algorithm finds lower points beyond the tabu move, we can say that the tabu move is the global optimum. This is indeed the case because the other optimum is only the local optimum.

If we consider Greedy Approach, there are two potential issues. First, Greedy Approach could stop at the local optimum. If we start on the very left of our 2D example, we will stop at the local optimum. Second, Greedy Approach is blind to further search space. In Greedy Approach, there is no mechanism that allows acceptance of solutions that are less than the previous one. Suppose we started Greedy Approach in the middle of the function, we would end up at the global optimum. But actually we don't know that.

## Environment
For this particular project, I use Microsoft Excel to implement TS. The file is visible in the main tab or can be accessed via this [link](https://github.com/iamphuc/Tabu-Search/blob/main/OPM_781_Software_Nguyen_Phuc.xlsx).

The file contains:
1. The mathematical formulation of the problem, 
2. The dataset, 
3. Brute Force Search, 
4. TS, 
5. Result.

## TS Implementation
Specific steps of implementation is shown in the below diagram.
![](images/TS%20Implementation%20Step.jpg)

## Reference
Glover, Fred; Laguna, Manuel (1998): Tabu Search. In : Handbook of Combinatorial Optimization: Springer, Boston, MA, pp. 2093–2229.

## License
This repository contains a [MIT LICENSE](https://github.com/iamphuc/Tabu-Search/blob/main/LICENSE)
