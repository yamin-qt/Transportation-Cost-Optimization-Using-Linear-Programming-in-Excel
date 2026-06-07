# 🚛 Transportation Cost Optimization Using Linear Programming in Excel

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel)
![Data Source](https://img.shields.io/badge/Data-World%20Bank-003087?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

This project applies **Linear Programming (LP)** to solve a classic **Transportation Problem** in supply chain management using Microsoft Excel's Solver add-in.

The core objective was straightforward but high-impact:
- Minimize total transportation cost across a distribution network
- Meet all city-level demand requirements
- Respect the capacity constraints of each distribution center

Instead of guessing or using trial-and-error, this model finds the **mathematically optimal shipment allocation** from each distribution center to each destination city — automatically.

---

## 🛠️ Tools & Techniques Used

| Tool / Feature | Purpose |
|---|---|
| Microsoft Excel | Primary modeling environment |
| Excel Solver (GRG/Simplex LP) | Linear programming optimization engine |
| Decision Variable Matrix | Shipment allocation per route |
| Objective Function | Total cost minimization formula |
| Constraint Modeling | Demand fulfillment + capacity limits |
| Sensitivity Analysis | Understanding shadow prices and allowable ranges |

---

## 🔢 How the Model Was Built

### Step 1 — Data Structuring
Organized four key inputs into a clean Excel layout:
- **Supply** — capacity of each distribution center
- **Demand** — required units for each destination city
- **Distance** — route distance matrix (DC → City)
- **Cost per Mile** — transportation rate per unit per mile

### Step 2 — Cost Matrix Calculation
Combined distance and cost-per-mile to generate a **unit transportation cost** for every possible route. This became the coefficient matrix for the objective function.

### Step 3 — Decision Variable Setup
Created a **shipment allocation matrix** — these cells are what Solver changes to find the optimal solution. Each cell represents units shipped from a specific DC to a specific city.

### Step 4 — Objective Function
Built a `SUMPRODUCT` formula multiplying the cost matrix by the allocation matrix. This single formula represents the **total transportation cost** Solver will minimize.

### Step 5 — Constraints
Added two types of constraints:
- **Supply constraints** — each DC cannot ship more than its capacity
- **Demand constraints** — each city must receive exactly its required units
- **Non-negativity** — shipment values cannot be negative

### Step 6 — Running Solver
Configured Solver with Simplex LP method and executed. The model returned the **optimal allocation plan** with minimum total cost.

---

## 📊 What the Model Tells Decision-Makers

| Question | Model Answer |
|---|---|
| Which DC should supply which city? | Optimal allocation matrix |
| What is the minimum possible cost? | Objective function result |
| Are any DCs over/under-utilized? | Supply constraint analysis |
| What happens if demand increases? | Sensitivity / shadow price report |

---

## 💼 Real-World Applications

This model type is directly applicable in:

- **Port to inland freight allocation** — deciding which port handles which inland destination
- **Distribution network planning** — warehouse-to-retailer shipment optimization
- **Container depot assignment** — allocating empty containers from depots to shipping lines
- **Warehouse dispatch decisions** — which warehouse fulfills which order cluster
- **Cost optimization in 3PL operations** — minimizing last-mile delivery cost
- **Feeder vessel routing** — optimizing cargo flow between hub and feeder ports

---

## 📈 Decision-Making Value

In logistics operations, even a **3–5% reduction in transportation cost** can translate to significant savings at scale. This model eliminates subjective routing decisions and replaces them with **data-driven, mathematically verified allocations**.

For port and freight operations specifically, this approach supports:
- Reducing empty truck movements
- Balancing load across distribution centers
- Justifying routing decisions with quantifiable cost evidence

---

## 🔍 What Could Be Improved

- **Multi-objective optimization** — balance cost vs. delivery time simultaneously
- **Stochastic demand modeling** — account for demand uncertainty rather than fixed values
- **Multi-period planning** — extend the model across weekly/monthly time horizons
- **Integration with live data** — connect to TMS or ERP exports for real-time optimization
- **Python/PuLP version** — rebuild in Python for scalability beyond Excel's row limits

---

## 🎓 What I Learned

- How to translate a real logistics problem into a mathematical model
- Excel Solver configuration for LP problems (Simplex method)
- The difference between feasible solutions and optimal solutions
- How sensitivity analysis reveals cost risk in logistics networks
- Why operations research is a core competency in supply chain management

<img width="1782" height="790" alt="image" src="https://github.com/user-attachments/assets/059cc25a-fe7a-4292-8172-4afd299b0007" />


---

