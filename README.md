# quantum_enhanced_last_mile_route_optimization
Route optimization using Quantum Approximate Optimization Algorithm (QAOA) and classical optimization techniques to find efficient delivery routes with minimum travel distance.
# SparkRoute
# Quantum-Enhanced Last-Mile Route Optimisation Using Qiskit

**Team Name:** Quantum Sparks  
**Team ID:** HT55  
**Event:** Qiskit Fall Fest 2026  
**Problem Statement ID:** VNQFF-08

## 1. Project Overview

SparkRoute is a quantum computing prototype that explores the use of quantum optimization for last-mile delivery route planning. The project aims to find efficient delivery routes by minimizing the total travel distance between a depot and multiple delivery locations.

The implementation uses Python and Qiskit to formulate the routing problem as a Quadratic Unconstrained Binary Optimization (QUBO) model. The Quantum Approximate Optimization Algorithm (QAOA) is used to search for candidate solutions, which are compared with a classical exhaustive-search approach.

## 2. Problem Statement

Last-mile delivery is an important part of logistics, where finding efficient routes can help reduce travel distance and transportation costs. As the number of delivery locations increases, route planning can become more complex.

SparkRoute explores whether a hybrid quantum-classical optimization approach can be applied to this problem and how its results compare with classical optimization methods.

## 3. Proposed Solution

SparkRoute represents the depot and delivery locations using coordinates and calculates the distances between them. These distances form the basis of the route optimization objective.

The routing problem is converted into a QUBO model using binary decision variables. QAOA is then used to search for candidate route assignments. The resulting assignments are decoded, validated, and evaluated using classical Python calculations.

A classical exhaustive-search method is also implemented to find the shortest route for the small demonstration problem. The results can then be compared using route distances and visualizations.

## 4. Project Objectives

- Formulate a delivery-routing problem as a QUBO model.
- Apply QAOA using Qiskit to search for candidate solutions.
- Validate route assignments against the required constraints.
- Compare QAOA results with a classical exhaustive-search baseline.
- Visualize routes and compare their calculated distances.
- Explore the potential of hybrid quantum-classical optimization for logistics.

## 5. Technology Stack

| Technology | Purpose |
 Python 
 Main programming language 
 Google Colab
 Development and execution environment 
 Qiskit 
 Quantum computing framework 
 Qiskit Optimization 
 Optimization problem formulation and QUBO conversion 
 QAOA 
 Quantum approximate optimization algorithm 
 COBYLA 
 Classical optimizer for QAOA parameters 
 StatevectorSampler 
 Local quantum-circuit sampling 
 NumPy 
 Numerical calculations 
 Pandas 
 Distance matrices and result tables 
 Matplotlib 
Route visualization and comparison charts 

## 6. Methodology

The project follows these steps:

1. Define the depot and delivery locations.
2. Calculate pairwise distances using Euclidean distance.
3. Create binary decision variables representing delivery-stop assignments to route positions.
4. Formulate the distance objective and assignment constraints.
5. Convert the optimization problem into QUBO form.
6. Configure and execute QAOA using Qiskit.
7. Decode and validate the candidate route.
8. Calculate the route distance and compare it with the classical baseline.
9. Display the results using tables and route visualizations.

## 7. Qiskit Implementation

The notebook contains a QUBO model with nine binary decision variables for assigning three delivery stops to three route positions.

The decision variable \(x_{i,t}\) represents whether delivery stop \(i\) is assigned to route position \(t\).

The objective accounts for the distance travelled:
- From the depot to the first delivery stop.
- Between consecutive delivery stops.
- From the final delivery stop back to the depot.

Assignment constraints and penalty terms are used to discourage invalid solutions.

The QUBO model is solved using Qiskit's `MinimumEigenOptimizer` with QAOA. The QAOA configuration uses `StatevectorSampler`, the COBYLA optimizer, and one circuit repetition in the current implementation.

The notebook also includes classical exhaustive search, which evaluates all six possible orders of three delivery stops to identify the minimum-distance route.

## 8. Dataset Information

The current demonstration uses simulated delivery-location coordinates created within the notebook. It does not rely on an external delivery dataset.

Pairwise distances are calculated using Euclidean distance. This provides a simple way to evaluate candidate routes for the prototype.

These distances are not actual road distances and do not account for traffic, travel time, road restrictions, fuel prices, or live delivery conditions.

## 9. Results and Observations

The notebook includes route-distance calculations, QAOA execution, route validation, classical exhaustive search, and visualization.

The later comparison cells report a classical route distance of 16.01 coordinate units and a QAOA route distance of 16.01 coordinate units, giving a reported distance difference of 0.00%.

These results need to be verified by rerunning the final experiment with consistent route definitions and inputs because earlier notebook cells contain different route definitions and distance values.

The current experiment demonstrates the implementation of a small routing optimization workflow. It does not establish quantum advantage or quantum speedup over classical methods.

## 10. How to Run the Project

1. Open the project notebook, `Quantum_route_optimization.ipynb`, in Google Colab.
2. Run the package installation cells.
3. Execute the notebook cells in the correct order.
4. Review the generated distance matrix and QUBO formulation.
5. Run the QAOA optimization and classical exhaustive-search comparison.
6. Inspect the route validation, distance comparison, and visualizations.

The project uses a local quantum simulator and does not require a physical quantum computer.

## 11. Team Information

**Team Name:** Quantum Sparks  
**Team ID:** HT55  
**Event:** Qiskit Fall Fest 2026  
**Problem Statement ID:** VNQFF-08  
**Project Name:** SparkRoute

## 12. Future Improvements

Future development may include:

- Testing larger routing problems with additional delivery locations.
- Using real road-network distances and travel-time data.
- Adding vehicle-capacity and delivery-time-window constraints.
- Improving route validation and fallback mechanisms.
- Comparing QAOA with additional classical optimization algorithms.
- Testing different QAOA parameters, circuit depths, and random seeds.
- Evaluating the implementation on quantum hardware when suitable access is available.

## 13. References

1. Farhi, E., Goldstone, J., and Gutmann, S. (2014). *A Quantum Approximate Optimization Algorithm.* https://arxiv.org/abs/1411.4028
2. Qiskit Documentation: https://docs.quantum.ibm.com/
3. Qiskit Optimization Documentation: https://qiskit-community.github.io/qiskit-optimization/
4. Qiskit Algorithms Documentation: https://qiskit-community.github.io/qiskit-algorithms/

## 14. Acknowledgements

We acknowledge IBM Quantum and the Qiskit community for providing the tools and learning resources that support experimentation with quantum computing and optimization.

## 15. Limitations

SparkRoute is an experimental prototype developed for hackathon and educational purposes. The current implementation uses simulated coordinates and a small routing problem.

Further testing and validation are needed before applying the approach to real-world delivery operations. The current results should not be interpreted as evidence of quantum advantage or production-ready optimization.
