# Introduction

## Phase Field Model
The program minimizes the following energy functional:
```
\Psi =\int_{\Omega} d\boldsymbol{r}\left[\frac{A}{2}\phi^2 + \frac{B}{3}\phi^3 + \frac{C}{4}\phi^3 + \frac{\kappa}{2}|\boldsymbol{\nabla}\phi|^2 \right ] + \frac{1}{2}\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right):\boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right)
```

withing the Ginzburg-Landau theory:
```
\frac{\partial \phi}{\partial t} = -\mathcal{M} \frac{\delta \Psi}{\delta \phi}
```

which gives the following equations:
```
\mathcal{M}\frac{\partial \phi}{\partial t} = A\phi + B\phi^2 +C\phi^3 + \kappa\boldsymbol{\nabla}^2\phi - \boldsymbol{C}:\left(\boldsymbol{\varepsilon}-\phi\boldsymbol{\varepsilon}^0\right )\cdot \boldsymbol{\varepsilon}^0
```

These equations are solved together with the equations of mechanical equilibrium at each time step:

```
\boldsymbol{K}\boldsymbol{u}=\boldsymbol{F}
```


## Implementation into ANSYS using APDL macro

## Solution

## Limitations
