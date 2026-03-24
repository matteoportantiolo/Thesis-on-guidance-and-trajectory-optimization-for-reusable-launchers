# Guidance and Trajectory Optimization for Reusable Launchers

## ⚠️ Code Availability
The `src` folder (MATLAB, C, CMake, Makefile) is **not included** in this repository due to company policy restrictions.

This thesis was conducted in collaboration with **Indra**, and the implementation is subject to confidentiality constraints.

---

## Overview
This thesis focuses on the development and analysis of **real-time guidance algorithms for reusable rocket landing**, based on convex optimization techniques.

The work investigates the use of **Quadratic Programming (QP)** solvers for embedded trajectory optimization, with particular attention to computational efficiency, robustness, and real-time feasibility.

Two main approaches are studied:
- **Sequential Convex Programming (SCvx)**
- **Sequential Quadratic Programming (SQP)**

---

## Mission Context
The problem addressed is the **powered descent and landing of a reusable launch vehicle**, requiring:

- Real-time trajectory generation
- Constraint satisfaction (thrust limits, state constraints)
- Robustness to model uncertainties
- Fast onboard computation

Typical applications include:
- Vertical landing of reusable boosters
- Planetary landing scenarios with limited computational resources

---

## System Architecture

### Guidance Framework
The guidance problem is formulated as a **trajectory optimization problem**:

- Nonlinear dynamics
- State and control constraints
- Minimum-fuel or minimum-effort objective

The problem is iteratively solved onboard using convex optimization techniques.

### Convexification Strategy
- Nonlinear dynamics are linearized around a reference trajectory
- Non-convex constraints are approximated through convex relaxations
- Trust-region or penalty mechanisms ensure convergence

---

## Methods

### Sequential Convex Programming (SCvx)
- Iterative convexification of the nonlinear optimal control problem
- Solves a sequence of convex subproblems
- Guarantees feasibility through virtual controls and trust regions

### Sequential Quadratic Programming (SQP)
- Solves a sequence of quadratic approximations of the nonlinear problem
- Incorporates second-order information
- Compared against SCvx in terms of convergence and robustness

### QP Solver Analysis
A key contribution of the thesis is the investigation of **off-the-shelf QP solvers** for embedded applications:

- Performance benchmarking (speed, convergence)
- Numerical robustness
- Suitability for real-time onboard implementation

### Custom Solver Strategies
- Problem structure exploitation
- Reduction of computational load
- Trade-offs between optimality and execution time

### Sensitivity Analysis
The robustness of the guidance solution is evaluated with respect to:

- Model uncertainties
- Discretization choices
- Initialization conditions

---

## Results

Main outcomes include:

- Demonstration of **real-time feasibility** of convex guidance methods
- Identification of trade-offs between:
  - SCvx (robustness, feasibility)
  - SQP (potentially faster convergence but less robust)
- Evaluation of QP solver performance for embedded applications
- Validation of guidance strategies under model uncertainties

The results highlight the importance of:
- Solver selection
- Problem scaling
- Initialization strategies

---

## Implementation

The (non-public) implementation includes:

- MATLAB prototypes for algorithm development
- C-based implementation for embedded execution
- QP solver integration
- Build system using CMake / Makefile
- Numerical simulation and validation framework

---

## Key Concepts

- Convex optimization
- Sequential Convex Programming (SCvx)
- Sequential Quadratic Programming (SQP)
- Quadratic Programming (QP)
- Real-time guidance
- Rocket landing
- Embedded optimization
- Trajectory optimization under constraints

---

## Author
Matteo Portantiolo  
MSc Space Engineering – GNC  
Thesis conducted in collaboration with **Indra**
