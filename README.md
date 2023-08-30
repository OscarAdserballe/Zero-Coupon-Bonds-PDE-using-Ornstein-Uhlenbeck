# Zero-Coupon-Bonds-PDE-using-Ornstein-Uhlenbeck

## Overview

This project aims to model and analyze the pricing of zero-coupon bonds using an Ornstein-Uhlenbeck process for the short rate. The model is based on a partial differential equation (PDE) that resembles the Black-Scholes equation and allows for a closed-form solution. The project includes both theoretical derivations and practical applications, utilizing real-world bond yield data for model validation.

## Core Concepts

### Ornstein-Uhlenbeck Process

The short rate, y_t, is modeled using an Ornstein-Uhlenbeck process:

<img src="\images\orn.png">

### Zero-Coupon Bond Pricing

The bond price V is modeled as a function of time t, maturity T and yield y:

V = V(t, T, y_t)

This is derived from a PDE resembling the Black-Scholes equation.

## Mathematics and Derivation

### Derivation of the PDE

The PDE for bond pricing is derived using a Black-Scholes-esque argument involving dynamic hedging. A portfolio pi is set up consisting of two bonds V_1 and V_2 to eliminate all risk so we can use the risk-free rate, s.t.:

<img src="\images\dynamic.png">

Using Ito's lemma and reordering terms, the PDE becomes:

<img src="\images\pde.png">

### Closed-Form Solution

The closed-form solution is obtained by using the following ansatz,

<img src="\images\ansatz.png">

and substituting into the PDE. This reduces the PDE to a system of two ordinary differential equations (ODEs):

<img src="\images\system.png">

Solving these ODEs and imposing boundary conditions leads to the closed-form solution for V(t, y).

### Boundary Conditions

The boundary condition applied is V=1, t=T, which makes the model specifically suited for zero-coupon bonds.

### Results

Testing on 10-year Bond prices inferred from 10 yr yields over time, we end up with a result that's surprisingly close to the actual data, when we apply a scaling factor to adjust it to the data, considering the simplicity of the model.

<img src="\images\output.png">

## Technologies and Dependencies

- Python for numerical simulations and data analysis
- NumPy for numerical computations
- Matplotlib for plotting and data visualization
- Pandas for data manipulation and analysis

## Unique Features

- Closed-form solution allows for quick and efficient calculations.
- Model parameters can be easily adjusted to fit different economic environments.
- Real-world data is used for model validation, making the project more robust and applicable.


Feel free to use, modify, and distribute this project as you see fit. For any issues, questions, or contributions, please open an issue.
