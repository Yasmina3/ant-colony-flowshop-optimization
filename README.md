# 🐜 Ant Colony Optimization for Flow Shop Scheduling (ACO-FSSP)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Optimization](https://img.shields.io/badge/Metaheuristics-ACO-green.svg)](#)
[![Problem](https://img.shields.io/badge/Problem-NP--Hard%20FSSP-orange.svg)](#)

An implementation of the **Ant Colony Optimization (ACO)** metaheuristic algorithm tailored to solve the **Permutation Flow Shop Scheduling Problem (PFSSP)**. The solver determines job scheduling sequences on $m$ machines to minimize total makespan ($C_{\max}$).

---

## 📌 Problem Formulation

Given $n$ jobs and $m$ machines, every job $j$ must pass through machine $1, 2, \dots, m$ in exact sequential order with processing times $p_{j,k}$.

**Objective Function:**
$$\min \quad C_{\max} = \max_{j \in \{1 \dots n\}} C(j, m)$$

Where $C(j, m)$ is the completion time of job $j$ on machine $m$.

---

## 💡 ACO Algorithm Highlights

* **Pheromone Trail Update:** 
  $$\tau_{ij}(t+1) = (1 - \rho) \tau_{ij}(t) + \Delta \tau_{ij}$$
* **State Transition Rule:** Ants build job sequences probabilistically using relative pheromone concentration $\tau_{ij}$ and local heuristic information $\eta_{ij}$ (e.g., inverse processing times).
* **Evaporation Strategy:** Prevents premature stagnation into local optima.

---

## 📊 Benchmark Results

| Instance | Jobs ($n$) | Machines ($m$) | Baseline Makespan | ACO Makespan | Improvement (%) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Test Set 1** | 20 | 5 | 1350 | **1282** | **5.0%** |
| **Test Set 2** | 50 | 10 | 3210 | **2980** | **7.2%** |

---

## 🚀 Quickstart

```bash
git clone [https://github.com/Yasmina3/aco-flowshop-scheduler.git](https://github.com/Yasmina3/aco-flowshop-scheduler.git)
cd aco-flowshop-scheduler
python main.py --jobs 20 --machines 5 --ants 50 --iterations 100
