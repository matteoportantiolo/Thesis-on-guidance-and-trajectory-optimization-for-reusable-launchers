# Real-time Convex Guidance for Rocket Landing

## ⚠️ Code Availability
The `src` folder (MATLAB, C, CMake, Makefile) is **not included** in this repository due to company policy restrictions.

This thesis was conducted in collaboration with **Indra**, and the implementation is subject to confidentiality constraints.

---

## Overview
This thesis focuses on the development of **real-time guidance algorithms for reusable rocket landing**, based on convex optimization techniques.

The main contribution is the investigation of **Sequential Convex Programming (SCvx) using Quadratic Programming (QP) subproblems**, with the goal of improving computational efficiency for embedded applications.

The proposed approach is compared against the **baseline SCvx implementation using Second-Order Cone Programming (SOCP)** currently adopted in the company.

---

## Mission Context
The problem addressed is the **powered descent and landing of a reusable launch vehicle**, which requires:

- Real-time trajectory generation
- Constraint satisfaction (thrust limits, state constraints)
- Robustness to uncertainties
- Fast onboard computation

These requirements make **computational efficiency** a key driver in guidance algorithm design.

---

## System Architecture

### Guidance Framework
The landing problem is formulated as a **nonlinear optimal control problem**:

- Nonlinear spacecraft dynamics
- State and control constraints
- Minimum-fuel or minimum-effort objective

The problem is solved onboard through **iterative convexification**.

### Convexification Strategy
- Linearization of dynamics around a reference trajectory
- Convex approximation of non-convex constraints
- Trust-region and penalty techniques to ensure convergence

Each iteration results in a convex subproblem to be solved efficiently.

---

## Methods

### SCvx with QP Subproblems (Proposed Approach)
- Reformulation of SCvx subproblems as **Quadratic Programs (QP)**
- Exploitation of problem structure for computational efficiency
- Compatibility with fast embedded QP solvers

This approach targets:
- Reduced solve time
- Improved scalability for onboard applications

### SCvx with SOCP (Baseline – Company Implementation)
- Convex subproblems formulated as **Second-Order Cone Programs (SOCP)**
- Higher modeling flexibility for certain constraints
- Increased computational cost compared to QP-based formulations

### Comparative Analysis
A detailed comparison is performed between:

- **QP-based SCvx (this work)**
- **SOCP-based SCvx (baseline)**

Key evaluation metrics include:
- Solver execution time
- Convergence behavior
- Feasibility and constraint satisfaction
- Sensitivity to initialization and discretization

### Solver Considerations
- Use of off-the-shelf QP solvers for embedded applications
- Trade-offs between accuracy and computational load
- Impact of problem scaling and conditioning

---

## Results

Main outcomes include:

- Demonstration that **QP-based SCvx significantly reduces computational cost**
- Comparable solution quality with respect to SOCP-based approach
- Improved suitability for **real-time onboard implementation**
- Identification of trade-offs between:
  - Modeling flexibility (SOCP)
  - Computational efficiency (QP)

The analysis highlights that **QP reformulation is a strong candidate for embedded guidance systems**.

---

## Implementation

The (non-public) implementation includes:

- MATLAB prototypes for algorithm development
- C-based implementation for embedded execution
- Integration of QP solvers
- Build system using CMake / Makefile
- Simulation framework for trajectory validation

---

## Key Concepts

- Sequential Convex Programming (SCvx)
- Quadratic Programming (QP)
- Second-Order Cone Programming (SOCP)
- Real-time trajectory optimization
- Rocket landing guidance
- Embedded optimization
- Convexification of nonlinear dynamics

---

## Author
Matteo Portantiolo  
MSc Space Engineering – GNC  
Thesis conducted in collaboration with **Indra**
