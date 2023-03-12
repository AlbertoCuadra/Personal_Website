---
title: Combustion Toolbox is now available for testing
date: 2021-10-13
math: true
diagram: true
# Schedule page publish date (NOT publication's date).
publishDate: "2021-10-13T00:00:00Z"
#image:
#  placement: 3
#  caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'

tags:
- Numerical code
- App
- Thermochemistry
- Shock waves
- MATLAB
- Open-source

#   url: ""
url_code: 'https://github.com/AlbertoCuadra/combustion_toolbox'
---


In the [poster presented at the XI Mediterranean Combustion Symposium](https://www.acuadralara.com/talk/msc11/) we introduced our first steps toward the development of an open-source wider-scope thermochemical tool. It's been a while since then and we're excited to say that **Combustion-Toolbox (CT) is now available for testing**. The kernel of the code has been rewritten to improve the performance and convergence of the numerical algorithms. The results obtained with the code are in good agreement with, NASA’s Chemical Equilibrium with Applications (CEA) program, CANTERA and Caltech’s Shock and Detonation Toolbox. A brief summary of the current stage of CT:

* The code computes the equilibrium composition by minimization of the Gibbs–Helmholtz free energy by using Lagrange multipliers and allows `gaseous and condensed species`.
* The code also computes equilibrium properties of `ideal plasmas`, i.e., no coulombic interactions are considered.
* It employs `NASA’s 9-coefficient polynomial` fits to evaluate the thermodynamic properties.
* CT solves six chemical equilibrium problems (`TP, HP, SP, TV, EV and SV transformations`; where T denotes temperature, P pressure, H enthalpy, S entropy, E internal energy and V volume), `incident and reflected planar shock waves, as well as ideal detonations according to Chapman-Jouguet theory and overdriven detonations`.
* A more comprehensive and user-friendly `GUI will be released in November 2021`.
* The code is in it's `transition to Python`.

**Repositories:**

`MATLAB` URL: https://github.com/AlbertoCuadra/combustion_toolbox

`PYTHON` URL: https://github.com/AlbertoCuadra/Combustion-PyToolbox
