---
title: "Combustion Toolbox v1.1.0 is Here!"
date: 2024-09-24
math: true
diagram: true
# Schedule page publish date (NOT publication's date).
publishDate: "2024-09-24T00:00:00Z"
#image:
#  placement: 3
#  caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'

tags:
- CombustionToolbox
- Thermochemistry
- MATLAB

#   url: ""
links:
- name: Website
  url: 'https://combustion-toolbox-website.readthedocs.io/'
- name: GitHub
  url: 'https://github.com/CombustionToolbox/combustion_toolbox'
---

# The Combustion Toolbox v1.1.0 is Here!

After months of refinement and debugging, I’m thrilled to announce the release of Combustion Toolbox v1.1.0! Along with the release, you can check out the [preprint](https://doi.org/10.48550/arXiv.2409.15086). For detailed documentation, visit our [website](https://combustion-toolbox-website.readthedocs.io/).

## What's New in v1.1.0?

- **Object-Oriented Architecture**: The transition to an object-oriented design brings enhanced performance, better encapsulation, and smoother integration with other frameworks. The core modules—CT-EQUIL, CT-SD, and CT-ROCKET—are powered by new solver classes like `EquilibriumSolver`, `ShockSolver`, `DetonationSolver`, and `RocketSolver`.

- **New algorithm for initial chemical composition estimation**:  
  The estimation of initial gaseous species composition has been upgraded from a fixed value approach to a more sophisticated max-min composition method, akin to the Mutation$^{++}$ code. This estimation, solved using the Simplex algorithm (see `Simplex.m` and `SimplexDual.m`), provides more accurate and reliable results for all the species involved, including condensed species.

- **Improved Chemical Equilibrium Solver**:  
  The chemical equilibrium solver, encapsulated in the `EquilibriumSolver` class, now includes slack variables to manage the composition of condensed species at chemical equilibrium. This approach, inspired by the Reaktoro and FastChem-Condensed codes, allows for simultaneous computation of all condensed species that meet the vapor pressure test.

- **Performance Boost**:  
  The latest version runs between **1.3x to 1.9x faster** than v1.0.5!

- **Cached Thermodynamic Functions**:  
  The thermodynamic functions are typically the most called routines when using the Combustion Toolbox. Although their performance was already fast, these functions are now temporarily stored in the cache for even faster data access.

- **New code organization**:  
  The code components are now organized using namespaces (`+folders`), ensuring a more structured and maintainable codebase.

For a full list of updates, check out the [Changelog](https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.0.5...v1.1.0).
