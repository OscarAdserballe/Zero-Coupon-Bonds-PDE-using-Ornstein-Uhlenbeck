# Zero-Coupon-Bonds-PDE-using-Ornstein-Uhlenbeck

## Overview

This project aims to model and analyze the pricing of zero-coupon bonds using an Ornstein-Uhlenbeck process for the short rate. The model is based on a partial differential equation (PDE) that resembles the Black-Scholes equation and allows for a closed-form solution. The project includes both theoretical derivations and practical applications, utilizing real-world bond yield data for model validation.

## Core Concepts

### Ornstein-Uhlenbeck Process

The short rate, y_t, is modeled using the Ornstein-Uhlenbeck process:

![] ("\images\orn.png")

### Zero-Coupon Bond Pricing

The bond price \( V \) is modeled as a function of time \( t \), yield \( y \), and other parameters:

\[\
V(t, y) = e^{(f(t)-yg(t))}
\]

This is derived from a PDE resembling the Black-Scholes equation, with boundary conditions applied.

## Mathematics and Derivation

### Derivation of the PDE

The PDE for bond pricing is derived using a Black-Scholes-esque argument involving dynamic hedging. A portfolio \( \\pi \) is set up consisting of two bonds \( V_1 \) and \( V_2 \) such that:

\[\
\\pi = q_1 V_1 + q_2 V_2, \\frac{q_1}{q_2} = -\\frac{\\partial V_2/\\partial y}{\\partial V_1/\\partial y}
\]

Using Ito's lemma and reordering terms, the PDE becomes:

\[\
\\frac{\\partial V}{\\partial t} + \\frac{\\sigma ^ 2}{2}\\frac{\\partial^2V}{\\partial y^2} - yV + \\alpha(\\bar y - y)\\frac{\\partial V}{\\partial y} = 0
\]

### Closed-Form Solution

The closed-form solution is obtained by making an ansatz \( V(t, y) = e^{(f(t)-yg(t))} \) and substituting into the PDE. This reduces the PDE to a system of two ordinary differential equations (ODEs):

\[\
\\frac{df}{dt} = g \\alpha  \\bar y - \\frac{\\sigma^2g^2}{2}
\]
\[\
\\frac{dg}{dt} = -1 + g\\alpha
\]

Solving these ODEs and imposing boundary conditions leads to the closed-form solution for \( V(t, y) \).

### Boundary Conditions

The boundary condition applied is \( V = 1, t = T \), which makes the model specifically suited for zero-coupon bonds.

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
