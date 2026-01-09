---
title: "Combustion Toolbox: first peer-reviewed article published and v1.2.8 released"
date: 2026-01-08
lastmod: 2026-01-08
math: true
diagram: true
publishDate: "2026-01-08T00:00:00Z"

tags:
- CombustionToolbox
- Thermochemistry
- MATLAB

links:
- name: Website
  url: 'https://combustion-toolbox-website.readthedocs.io/'
- name: GitHub
  url: 'https://github.com/CombustionToolbox/combustion_toolbox'
- name: DOI
  url: 'https://doi.org/10.1016/j.cpc.2025.110004'
- name: Full Changelog
  url: 'https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.7...v1.2.8'
---

We are pleased to announce that the first peer-reviewed article describing the Combustion Toolbox framework has been published as open access in Computer Physics Communications.

> _Cuadra, A., Huete, C., & Vera, M., (2026). Combustion Toolbox: An open-source thermochemical code for gas-and condensed-phase problems involving chemical equilibrium. Computer Physics Communications 320, 110004. [DOI: 10.1016/j.cpc.2025.110004](https://doi.org/10.1016/j.cpc.2025.110004)._

In addition, we are excited to announce the release of **Combustion Toolbox v1.2.8**, which includes a new module for linear shock-turbulence interaction analysis, a generalized Prandtl-Meyer expansion solver using different caloric models, and a broad set of robustness improvements, bug fixes, and documentation updates across the Combustion Toolbox ecosystem.

---

## 1. New CT-LIA module for solving shock-turbulence interaction problems using linear theory

This v1.2.8 presents a **Linear Interaction Analysis (LIA) framework for shock-turbulence interaction (STI) problems in compressible flows**, hereafter **CT-LIA**. This new module enables the computation of turbulence amplification statistics across a normal shock interacting with weak upstream turbulence, under the assumptions of linearity, inviscid flow, and thermochemical equilibrium across a thin relaxation layer.

The solver is fully integrated into the Combustion Toolbox framework and supports calorically perfect, thermally perfect, and calorically imperfect gas models, as well as multi-component mixtures.

The solver follows the theoretical formulation described in:

> _Cuadra, A., Williams, C. T., Di Renzo, M., & Huete, C. The role of compressibility and vibrational-excitation in hypersonic shock-turbulence interactions. Journal of Fluid Mechanics (under review)._

### Solver architecture

#### ShockTurbulenceSolver
A new high-level class, `ShockTurbulenceSolver`, orchestrates the complete LIA workflow:

1. Computation of shock jump conditions using `EquilibriumSolver`, `ShockSolver`, and `JumpConditionsSolver`
2. Selection of the appropriate turbulence interaction model based on the prescribed upstream disturbance type
3. Spectral integration of post-shock turbulence statistics
4. Optional reporting and visualization of results

The solver dispatches to a specific turbulence model via the `problemType`
argument:

- `vortical`
- `vortical_entropic`
- `acoustic`
- `compressible`

This design cleanly separates thermodynamics, shock physics, and turbulence
modeling, while maintaining a consistent user-facing API.

#### ShockTurbulenceModel Hierarchy
A new abstract base class, `ShockTurbulenceModel`, defines a unified interface for
all LIA turbulence models. Four concrete implementations are provided:

- `ShockTurbulenceModelVortical`
- `ShockTurbulenceModelVorticalEntropic`
- `ShockTurbulenceModelAcoustic`
- `ShockTurbulenceModelCompressible`

Each model:
- Implements the appropriate linear transfer functions for its modal content
- Uses a dimension-dependent (2D / 3D) wavenumber probability density function
- Computes ensemble-averaged post-shock quantities via spectral integration
- Returns consistent amplification metrics, including:
  - Turbulent kinetic energy (TKE)
  - Longitudinal and transverse TKE components
  - Enstrophy
  - Anisotropy measures

### Characterization of upstream turbulence field

#### Vortical-Entropic Correlation (`chi`)
The parameter $\chi$ prescribes the correlation between entropic density fluctuations and vortical velocity perturbations in the upstream turbulence. This quantity represents dilatational content implicit in the vortical-entropic mode and does not correspond to propagating acoustic energy.

Following Eq. (3.9) of the reference formulation, $\chi$ is defined as

$$ \langle \chi \rangle = \frac{\langle \delta \rho_1^e \delta u_1^r\rangle}{\langle \delta u_1^r \delta u_1^r \rangle} \frac{\langle c_1 \rangle}{\langle \rho_1 \rangle},$$

where $\delta \rho_1^e$ denotes entropic density fluctuations, $\delta u_1^r$ denotes rotational (vortical) velocity fluctuations, and $c_1$ and $\rho_1$ are the upstream speed of sound and density.

#### Dilatational-to-Solenoidal TKE Ratio (`eta`)
The parameter $\eta$ controls the relative contribution of propagating acoustic (dilatational) fluctuations to the upstream turbulent kinetic energy. It is defined as

$$\eta = \frac{TKE_{1a}}{TKE_{1r}},$$

where $TKE_{1a}$ and $TKE_{1r}$ denote the acoustic and vortical-entropic contributions to the upstream turbulent kinetic energy, respectively.

### Examples
This pull request includes some examples illustrating all supported configurations:

- **Vortical Shock-Turbulence Interaction**
  - Purely solenoidal upstream turbulence
  - No acoustic or entropic content (`eta = 0`, `chi = 0`)

- **Vortical-Entropic Shock-Turbulence Interaction**
  - Solenoidal turbulence with correlated entropic density fluctuations
  - Controlled via `chi`

- **Acoustic Shock-Turbulence Interaction**
  - Purely dilatational, propagating acoustic disturbances
  - No vortical or entropic modes

- **Fully Compressible Shock-Turbulence Interaction**
  - Combined vortical, entropic, and acoustic fluctuations
  - Controlled via `chi` and `eta`

## 2. Generalized Prandtl-Meyer expansion solver for different caloric models

A new `SHOCK_PRANDTL_MEYER` problem type has been added to the `ShockSolver` class, extending the shock module beyond compression waves to include isentropic expansion fans in real-gas flows.

This feature extends the shock module beyond compression waves and introduces a **real-gas Prandtl-Meyer expansion solver**, compatible with both **frozen** and **equilibrium** thermochemical models, with built-in path history for visualization and analysis.

### Capabilities

- Computes downstream state after a flow expansion through a deflection angle `θ₂`
- Marches along a **constant-entropy and specific-volume (SV) path**
- Uses **perfect-gas Prandtl-Meyer theory only for initialization**
- Tracks full **expansion path history** in `mix2.polar` (for polar plotting)
- Enforces **stagnation enthalpy conservation** during expansion
- Control number of points through the isentropic expansion path using `numPointsPrandtMeyer` during `ShockSolver` definition


### Supported caloric models

- Calorically perfect gas (`FLAG_TCHEM_FROZEN = true`) #1083
- Thermally perfect gas (`FLAG_FROZEN = true`)
- Calorically imperfect gas at chemical equilibrium (default mode)

### Numerical Method Summary

- Initial guess `(ρ₂, M₂)` generated from classical Prandtl-Meyer relations
- Expansion path traced using `tracePrandtlMeyerExpansion` under SV constraints
- Iterative refinement of downstream density using **Newton-Raphson**
- At each iteration:
  - Thermodynamic state enforced via `stateSV`
  - Velocity and Mach updated from **constant stagnation enthalpy**
  - Generalized Prandtl-Meyer integrand used instead of γ-based analytical formula
  
### Validation

The implementation was verified against **Caltech’s Shock-Detonation Toolbox** for both thermally perfect and calorically imperfect (equilibrium) gas models. The figure below shows the equilibrium Prandtl-Meyer expansion for deflection angles $\theta_2 \in [0, 82^\circ]$ in an air mixture (79% $\text{N}_2$ / 21% $\text{O}_2$) at a free-stream Mach number $\mathcal{M}_1 = 1$.

![test_validation](https://github.com/user-attachments/assets/eb6af2af-8acd-4106-836f-de84672b23fd)

### Example

```matlab
% Import packages
import combustiontoolbox.databases.NasaDatabase
import combustiontoolbox.core.*
import combustiontoolbox.shockdetonation.*
import combustiontoolbox.utils.display.*

% Definitions
FLAG_FROZEN = false;

% Get Nasa database
DB = NasaDatabase();

% Define chemical system
system = ChemicalSystem(DB);

% Initialize mixture
mix = Mixture(system);

% Define chemical state
set(mix, {'N2', 'O2'}, [79, 21]/21);

% Define properties
mixArray1 = setProperties(mix, 'temperature', 3000, 'pressure', 1, 'M1', 1, 'theta', 82);

% Initialize solver
solver = ShockSolver('problemType', 'SHOCK_PRANDTL_MEYER');

% Solve problem
[mixArray1, mixArray2] = solver.solveArray(mixArray1);

% Generate report from mixArray
report(solver, mixArray1, mixArray2)

% Generate report from polar of last mixArray2
mixArray2(end).polar(1).rangeName = 'theta';
report(solver, mixArray2(end).polar, mixArray2(end).polar)
```

### Benchmark

𝗦𝘆𝘀𝘁𝗲𝗺 𝗜𝗻𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻

    CT version    MATLAB version    OS version      CPU name      Clock speed    Cache L2    Cores
    __________    ______________    __________    ____________    ___________    ________    _____

      1.2.8           R2025b          15.6.1      Apple M2 Pro        N/A         65536       10  

𝗕𝗲𝗻𝗰𝗵𝗺𝗮𝗿𝗸𝗶𝗻𝗴

    Module      Solver             Problem                             Filename                       Cases    Species    Tolerance    AvgTime
    ______    ___________    ___________________    ______________________________________________    _____    _______    _________    _______

    CT-SD     ShockSolver    SHOCK_PRANDTL_MEYER    run_validation_SHOCK_PRANDTL_MEYER_SDToolbox_1      1        11       1.00e-05      1.2191
    CT-SD     ShockSolver    SHOCK_PRANDTL_MEYER    run_validation_SHOCK_PRANDTL_MEYER_SDToolbox_2     81        11       1.00e-05     0.94038

𝗦𝘂𝗺𝗺𝗮𝗿𝘆 𝗕𝗲𝗻𝗰𝗵𝗺𝗮𝗿𝗸𝗶𝗻𝗴

    Module          Problem          GroupCount    sum_Cases    mean_Cases    sum_Species    mean_Species    sum_AvgTime    mean_AvgTime
    ______    ___________________    __________    _________    __________    ___________    ____________    ___________    ____________

    CT-SD     SHOCK_PRANDTL_MEYER        2            82            41            22              11           2.1594          1.0797   

## 3. New `CaloricGasModel` enumeration

A new enumeration class, `CaloricGasModel`, has been introduced to explicitly define the caloric gas model:

- `perfect`
- `thermallyPerfect`
- `imperfect`

This replaces the previous dual-flag mechanism and prevents invalid or ambiguous configurations.

### Backward Compatibility

- Legacy flags are still accepted.
- CaloricGasModel.fromFlag() maps them safely to enum values.

### Example

```matlab
caloricGasModel = CaloricGasModel.perfect;

if caloricGasModel.isPerfect()
    % configure perfect gas behavior...
end

```

## 4. Minor changes

This v1.2.8 also introduces a small set of utility plotting classes in the `utils.display` subpackage to improve figure management and layout consistency.

- **Canvas (abstract base class)**  
  Provides a common interface for figure creation, tiled layouts, axis management, and formatting via `PlotConfig`. This class centralizes shared plotting logic and reduces code duplication.

- **PlotFigure**  
  Extends `Canvas` to provide a unified interface for plotting thermodynamic and transport properties against an arbitrary independent variable, with consistent styling and optional validation overlays.

- **PlotComposition**  
  Extends `Canvas` to generate species composition plots (e.g. molar fractions `Xi`) with automatic species filtering, log scaling, and validation support.

---

**Full Changelog**: https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.7...v1.2.8
