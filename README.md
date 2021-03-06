# Introduction
Here, I demonstrate a simple implementation of a simple phase field model of solid-to-solid phase transformation in ANSYS using the APDL macro. This approach is not computationally efficient but it does the job and the implementation is very simple. For simplicity, the phase field model here operates only with one order parameter and the transformation strain is modelled through the analogy with thermal expansion. 

![](martensite_phase_transformation.gif)

*Growth of a single martensitic variant in an austenitic matrix*

## Phase Field Model
The program minimizes the following energy functional:

<img src="https://latex.codecogs.com/svg.latex?\Psi&space;=\int_{\Omega}&space;d\boldsymbol{r}\left[\frac{A}{2}\phi^2&space;&plus;&space;\frac{B}{3}\phi^3&space;&plus;&space;\frac{C}{4}\phi^3&space;&plus;&space;\frac{\kappa}{2}|\boldsymbol{\nabla}\phi|^2&space;\right&space;]&space;&plus;&space;\frac{1}{2}\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right):\boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right)" title="\Psi =\int_{\Omega} d\boldsymbol{r}\left[\frac{A}{2}\phi^2 + \frac{B}{3}\phi^3 + \frac{C}{4}\phi^3 + \frac{\kappa}{2}|\boldsymbol{\nabla}\phi|^2 \right ] + \frac{1}{2}\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right):\boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right)" />

within the Ginzburg-Landau theory:

<img src="https://latex.codecogs.com/svg.latex?\frac{\partial&space;\phi}{\partial&space;t}&space;=&space;-\mathcal{M}&space;\frac{\delta&space;\Psi}{\delta&space;\phi}" title="\frac{\partial \phi}{\partial t} = -\mathcal{M} \frac{\delta \Psi}{\delta \phi}" />

where, <img src="https://latex.codecogs.com/svg.latex?\inline&space;A,B,C" title="A,B,C" /> are double well potential constants, <img src="https://latex.codecogs.com/svg.latex?\inline&space;\phi" title="\phi" /> is the order parameter, <img src="https://latex.codecogs.com/svg.latex?\inline&space;\kappa" title="\kappa" /> is the gradient coefficient, <img src="https://latex.codecogs.com/svg.latex?\inline&space;\boldsymbol{\varepsilon},&space;\boldsymbol{\varepsilon}^0" title="\boldsymbol{\varepsilon}, \boldsymbol{\varepsilon}^0" /> are strain tensors (total strain and transformation strain), and <img src="https://latex.codecogs.com/svg.latex?\inline&space;\boldsymbol{C}" title="\boldsymbol{C}" /> is the tensor of elastic constants. <img src="https://latex.codecogs.com/svg.latex?\inline&space;\mathcal{M}" title="\mathcal{M}" /> is a mobility constant. 

I have chosen the following double well potential:

<img src="https://github.com/MikulaJakub/simple-phase-field-model-with-ANSYS/blob/master/double_well_potential.png" width="50%">

These equations are solved together with the equations of mechanical equilibrium at each time step:

<img src="https://latex.codecogs.com/svg.latex?\boldsymbol{K}\boldsymbol{u}=\boldsymbol{F}" title="\boldsymbol{K}\boldsymbol{u}=\boldsymbol{F}" />


## Implementation into ANSYS using APDL macro

In this implementation I model the transformation strain through the analogy of thermal expansion which I define by the secant coefficients (representing the transformation strain) and temperature (representing the order parameter). 


## Solution
### Clamped Boundaries
Under clamped boundary conditions the system equilibrates with the following pattern formation:

![](martensite_phase_transformation.gif)
