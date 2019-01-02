# Introduction
Here I demonstrate a simple implementation of a phase field model into ANSYS using the macro. This approach is not computationally efficient but it does the job and the implementation is very simple. For simplicity, the phase field model here operates only with one order parameter and the transformation strain is modelled through the thermal coefficients. 

![](martensite_phase_transformation.gif)

*Growth of a single martensitic variant in an austenitic matrix*

## Phase Field Model
The program minimizes the following energy functional:

<img src="https://latex.codecogs.com/svg.latex?\Psi&space;=\int_{\Omega}&space;d\boldsymbol{r}\left[\frac{A}{2}\phi^2&space;&plus;&space;\frac{B}{3}\phi^3&space;&plus;&space;\frac{C}{4}\phi^3&space;&plus;&space;\frac{\kappa}{2}|\boldsymbol{\nabla}\phi|^2&space;\right&space;]&space;&plus;&space;\frac{1}{2}\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right):\boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right)" title="\Psi =\int_{\Omega} d\boldsymbol{r}\left[\frac{A}{2}\phi^2 + \frac{B}{3}\phi^3 + \frac{C}{4}\phi^3 + \frac{\kappa}{2}|\boldsymbol{\nabla}\phi|^2 \right ] + \frac{1}{2}\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right):\boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right)" />

withing the Ginzburg-Landau theory:
```
\frac{\partial \phi}{\partial t} = -\mathcal{M} \frac{\delta \Psi}{\delta \phi}
```

which gives the following equations:

<img src="https://latex.codecogs.com/svg.latex?\frac{\partial&space;\phi}{\partial&space;t}&space;=&space;-\mathcal{M}&space;\frac{\delta&space;\Psi}{\delta&space;\phi}" title="\frac{\partial \phi}{\partial t} = -\mathcal{M} \frac{\delta \Psi}{\delta \phi}" />

These equations are solved together with the equations of mechanical equilibrium at each time step:

<img src="https://latex.codecogs.com/svg.latex?\boldsymbol{K}\boldsymbol{u}=\boldsymbol{F}" title="\boldsymbol{K}\boldsymbol{u}=\boldsymbol{F}" />


## Implementation into ANSYS using APDL macro

## Solution

## Limitations
