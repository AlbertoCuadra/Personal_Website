---
title: "Combustion Toolbox v1.2.9 Released"
date: 2026-01-15
lastmod: 2026-01-15
math: true
diagram: true
publishDate: "2026-01-15T00:00:00Z"
tags:
- CombustionToolbox
- Thermochemistry
- MATLAB

links:
- name: Website
  url: 'https://combustion-toolbox-website.readthedocs.io/'
- name: GitHub
  url: 'https://github.com/CombustionToolbox/combustion_toolbox'
- name: Full Changelog
  url: 'https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.8...v1.2.9'
---

This release improves robustness and consistency in shock jump-derivative computations, generalizes the shock–turbulence interaction workflow for broader parametric studies, and integrates **SHOCKTURBULENCE** problems into the Combustion Toolbox App. It also includes bug fixes in chemical system updates, equilibrium stability improvements at low temperatures, and several minor usability enhancements.

## Refactored `JumpConditionsSolver`

This new release fixes inconsistent values of **Gammas1** and **Gammas3** in `JumpConditionsSolver` when using **scalar Mach inputs** (e.g., `M1 = 5`). The previous implementation relied on interpolation along the Hugoniot curve, which is not well-defined for a single point and can change when extra points are added.

**Gammas1** and **Gammas3** now enforce the constant post-shock density constraint using the chain-rule, leveraging derivatives with respect to Mach computed during **Gammas2**:

$$ \left(\frac{\partial p_2}{\partial \phi}\right)_{\rho_2} = \frac{\partial p_2}{\partial \phi} - \frac{\partial p_2}{\partial M_1} \frac{\left(\partial \rho_2/\partial \phi\right)}{\left(\partial \rho_2/\partial M_1\right)} , \qquad \phi \in \{T_1, p_1\} $$

Results are now **stable and consistent** for both scalar and array Mach inputs.

## Updated `ShockTurbulenceSolver`

Reorganize and generalize the `shockturbulence` subpackage to improve maintainability and enable parametric sweeps on upstream parameters beyond the pre-shock Mach number.

- `solve()` now returns `mixArray1` and `mixArray2`, with LIA outputs stored in mixArray2(i).lia as a structure.
- Refactoring and cleanup of solver/model interfaces for easier extension and reuse.

## Added `SHOCKTURBULENCE_*` problems to the Combustion Toolbox `App`

All `SHOCKTURBULENCE_*` problems are now available directly from the Combustion Toolbox App, enabling interactive configuration and execution of shock–turbulence interaction cases without scripting.

<img width="632" height="816" alt="CleanShot 2026-01-15 at 11 26 44" src="https://github.com/user-attachments/assets/40f89ec8-a95a-4164-be83-8b2f13d072ef" />
<img width="634" height="817" alt="CleanShot 2026-01-15 at 11 35 28" src="https://github.com/user-attachments/assets/97bd525b-08c7-4ff1-92a3-57410707e7a1" />

## Bug fixes

- Invoke `clean()` / `cleanMoles()` when updating `ChemicalSystem.propertiesMatrix` to avoid stale values
- Fix chemical equilibrium failures at low temperature when ionized species may be present

## Minor changes

- Added `eta`, `chi`, `etaVorticity`, and `lia` as properties of `Mixture` class
- Included printing option in `Mixture`class for `SHOCKTURBULENCE_*` problems
- Added missing labels in the `interpreterLabel` utility function

---

**Full Changelog**: https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.8...v1.2.9
