---
title: Microsoft Quantum Solution 
description: This document provides the technical details of the Microsoft Quantum Solution provider
author: KittyYeungQ
ms.author: kitty
ms.date: 06/29/2020
ms.topic: article
uid: microsoft.azure.quantum.providers.microsoft-quantum-solution
---

# Microsoft Quantum Solution provider

The Microsoft Quantum Solution provider is enabled in every Quantum Workspace.

- Publisher: [Microsoft](https://microsoft.com)
- Provider ID: `microsoft`

During the private preview, customers get the following usage for free:

- Five hours of solver time per month
- Up to five concurrent optimization jobs

## Targets

The Microsoft Quantum Solution provider makes the following targets available:

- [Solver: Simulated Annealing (Parameter
  Free)](#parameter-free-simulated-annealing)
- [Solver: Simulated Annealing](#simulated-annealing)
- [Solver: Parallel Tempering (Parameter
  Free)](#parameter-free-parallel-tempering)
- [Solver: Parallel Tempering](#parallel-tempering)
- [Solver: Tabu Search (Parameter Free)](#parameter-free-tabu-search)
- [Solver: Tabu Search](#tabu-search)

### Parameter-free simulated annealing

A parameter-free (up to a time out) solver for binary optimization problems with
k-local interactions on an all-to-all graph topology with double precision
support for the coupler weights. To use the parameter-free simulated annealing
solver, specify only the `timeout` and/or `seed` parameters when instantiating
the `SimulatedAnnealing` class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.simulatedannealing-parameterfree.cpu`
- Python Solver class name: `SimulatedAnnealing`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type     | Required | Description |
|----------------|----------|----------|-------------|
| `timeout`      | int      | Required | Maximum number of seconds to run the core solver loop. Initialization time does not respect this value, so the solver may run longer than the value specified. |
| `seed`         | int      | Optional | Seed value  |

### Simulated annealing

A solver for binary optimization problems with k-local interactions on an
all-to-all graph topology with double precision support for the coupler weights.
To use the parameterized simulated annealing solver, specify one or more of the
below parameters when instantiating the `SimulatedAnnealing` class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.simulatedannealing.cpu`
- Python Solver class name: `SimulatedAnnealing`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type     | Required | Description |
|----------------|----------|----------|-------------|
| `beta_start`   | float    | Required | Inverse starting temperature. |
| `beta_stop`    | float    | Required | Inverse stopping temperature. |
| `sweeps`       | int      | Required | Number of sweeps to run. |
| `restarts`     | int      | Required | Number of restarts. |

### Parameter-free parallel tempering

A parameter-free solver for binary optimization problems with k-local interactions
on an all-to-all graph topology with double precision support for the coupler
weights. To use the parameter-free parallel tempering solver, specify only the
`timeout` and/or `seed` parameters when instantiating the `ParallelTempering`
class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.paralleltempering-parameterfree.cpu`
- Python Solver class name: `ParallelTempering`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type     | Required | Description |
|----------------|----------|----------|-------------|
| `timeout`      | int      | Required | Maximum number of seconds to run the core solver loop. Initialization time does not respect this value, so the solver may run longer than the value specified. |
| `seed`         | int      | Optional | Seed value  |

### Parallel tempering

A solver for binary optimization problems with k-local interactions on an
all-to-all graph topology with double precision support for the coupler weights.
To use the parameterized parallel tempering solver, specify one or more of the
below parameters when instantiating the `ParallelTempering` class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.paralleltempering.cpu`
- Python Solver class name: `ParallelTempering`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type        | Required | Description |
|----------------|-------------|----------|-------------|
| `sweeps`       | int         | Required | Number of sweeps to run. |
| `replicas`     | int         | Required | Number of replicas. |
| `all_betas`    | List[float] | Required | List of inverse temperatures. Must be equal in length to the `replicas` parameter. |

### Parameter-free Tabu Search

A parameter-free (up to a time out) version of the tabu search algorithm described below. To use the parameter-free tabu search
solver, specify only the `timeout` and/or `seed` parameters when instantiating
the `Tabu` class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.tabu-parameterfree.cpu`
- Python Solver class name: `Tabu`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type     | Required | Description |
|----------------|----------|----------|-------------|
| `timeout`      | int      | Required | Maximum number of seconds to run the core solver loop. Initialization time does not respect this value, so the solver may run longer than the value specified. |
| `seed`         | int      | Optional | Seed value  |

### Tabu Search

Uses a variant of the tabu search algorithm for binary optimization problems with k-local interactions on an
all-to-all graph topology. To use the parameterized tabu search solver, specify one or more of the
below parameters when instantiating the `Tabu` class.

- Job type: `Quantum-Inspired Optimization Problem`
- Data Format: `microsoft.qio.v2`
- Target ID: `microsoft.tabu.cpu`
- Python Solver class name: `Tabu`

Billing information: **Free in Private Preview**

Monthly quota: **50 hours per month**

| Parameter Name | Type        | Required | Description |
|----------------|-------------|----------|-------------|
| `sweeps`       | int         | Required | Number of meaningful iterations to run. This is recommended to be at least the number of variables times 100|
| `tabu_tenure`  | int         | Required | Tenure of the tabu list in moves. Describes how many moves a variable stays on the tabu list once it has been made. Recommended to be between 1 and number of variables for any impact. |
| `seed`         | int | Optional | Seed value |