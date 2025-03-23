# OPTIMIZATION-MODEL

COMPANY: CODETECH IT SOLUTIONS

NAME: DEEKSHITH KUMAR

INTERN ID: CODHC14

DOMAIN: Data science

DURATION: 8 WEEKS

MENTOR: NEELA SANTHOSH

##DESCRIPTION
This Python script uses PuLP, an optimization library, to solve a supply chain optimization problem using linear programming. The goal is to minimize transportation costs while ensuring that warehouses do not exceed their supply capacities and customers receive their required demand. The problem is formulated as a Linear Programming (LP) model and solved using PuLP’s built-in solvers.
The script starts by importing the necessary libraries: PuLP for optimization and Pandas for result handling. It then defines the warehouses (W1, W2, W3) as supply points and customers (C1, C2, C3) as demand points. The supply dictionary specifies the maximum number of units each warehouse can ship, while the demand dictionary represents the number of units each customer needs. Next, the costs dictionary defines the per-unit transportation costs between warehouses and customers. For example, shipping one unit from W1 to C1 costs 2.
To define the decision variables, the script creates a dictionary x using LpVariable.dicts(). Each variable x[w, c] represents the number of units shipped from warehouse w to customer c. The lowBound=0 ensures non-negative values, and cat='Continuous' indicates that fractional values are allowed.
The objective function is formulated to minimize total transportation costs. It sums up the transportation costs for all warehouse-customer pairs, weighted by the shipped quantity (x[w, c] * costs[w, c]). This function is added to the model using model +=.
Next, the script enforces supply constraints to ensure that no warehouse ships more than its available supply. This is done by iterating through each warehouse and adding a constraint that the total units shipped to all customers from that warehouse cannot exceed its supply capacity. Similarly, demand constraints ensure that each customer receives at least the required units from all warehouses combined.
After defining the model, the script calls model.solve() to find the optimal shipping quantities that minimize cost while satisfying all constraints. It then prints the optimization status, which indicates whether the problem has been solved optimally, is infeasible, or unbounded. The total transportation cost of the optimal solution is extracted using pulp.value.
Finally, the script iterates over all pairs, retrieves the optimized shipping quantities (varValue), and stores the results in a Pandas DataFrame. This DataFrame provides a structured table showing how many units should be shipped from each warehouse to each customer to achieve the minimum transportation cost. The results are printed, allowing easy interpretation of the optimal transportation plan.
This approach is widely used in supply chain management, logistics, and operations research to optimize transportation networks, reduce costs, and improve efficiency. By using linear programming, businesses can make data-driven decisions about how to distribute goods in the most cost-effective manner while meeting customer demand and respecting warehouse constraints.

##OUTPUT

![Image](https://github.com/user-attachments/assets/3b90cf2a-ad2c-4c86-9db5-a99f9f0d56c6)
