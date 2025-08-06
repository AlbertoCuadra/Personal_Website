---
title: "Combustion Toolbox v1.2.0 Released"
date: 2025-03-16
lastmod: 2025-03-16
math: true
diagram: true
publishDate: "2025-03-16T00:00:00Z"

tags:
- CombustionToolbox
- Turbulence
- Thermochemistry
- MATLAB

links:
- name: Website
  url: 'https://combustion-toolbox-website.readthedocs.io/'
- name: GitHub
  url: 'https://github.com/CombustionToolbox/combustion_toolbox'
- name: Full Changelog
  url: 'https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.1.3...v1.2.0'
---

**Combustion Toolbox v1.2.0** is now available! This release introduces a new turbulence module, a refactored equation-of-state system, significant performance improvements, and multiple usability enhancements across the entire ecosystem.

---

## **New Features and Enhancements**

### **1. New `+turbulence` subpackage**
A dedicated module for **turbulence analysis**.  

- **`HelmholtzSolver` class:**  
  - Implements Helmholtz decomposition to separate 3D velocity fields into:
    - **Solenoidal Component** (divergence-free)
    - **Dilatational Component** (curl-free)
  - Includes validation methods to ensure decomposition accuracy.

- **`TurbulenceSpectra` class:**  
  - Computes turbulence energy spectra using:
    - **Spherical Averaging**
    - **Cross-Plane Averaging** (configurable for `x`, `y`, or `z` axes)
  - Provides functions to validate energy cascade properties and visualize spectra.
  - Functions to compute **probability density functions (PDFs)** and **integral length scales**.
  - New routines for **computing and plotting joint-PDFs** with advanced visualization features.
  
- **`VelocityField` class:**  
  - Encapsulates 3D velocity field data (`u`, `v`, `w`) and offers:
    - Methods for computing magnitudes.
    - Utilities for normalizing and scaling velocity fields.

---

### **2. New HTR Data Utility classes**
A dedicated **HTR data handling module** has been introduced to facilitate **postprocessing and data analysis** from [**HTR solver simulations**](https://github.com/stanfordhpccenter/HTR-solver).

- **HTR Data Handling:**
  - **`HTRDataReader` class:** Reads simulation data from the **HTR solver**, extracting velocity, temperature, pressure, and species concentration fields.
  - **`HTRDataAverage` class:** Provides postprocessing utilities for **averaging** HTR simulation results, computing **spatial and temporal** averages of key flow properties.

---

### **3. Refactored EquationState class**
Significant refactoring has been performed in the `Mixture` class to improve flexibility, maintainability, and computational efficiency.

- Introduced `EquationState` as an **abstract base class** for different equations of state.
- New **`EquationStateIdealGas`** class implements the **ideal gas law**:
  - `getPressure(T, V)`: Computes pressure using $P = \frac{RT}{V}$.
  - `getVolume(T, P)`: Computes molar volume using $V = \frac{RT}{P}$.
- This structure prepares the framework for future real gas models (**e.g., Peng-Robinson, BKW, Heuzé EOS**).

---

### **4. Improved `Mixture` class Computation**
- **Refactored Methods:**
  - **`updateComposition()`** to handle composition changes independently.
  - **`updateThermodynamics()`** to compute thermodynamic properties without redundant recalculations.

- **Optimized State-Setting:**
  - `setTemperature()`, `setPressure()`, and `setVolume()` now trigger **only necessary updates**, avoiding redundant logic.

- **Performance Improvements:**
  - Removed unnecessary unit conversions in shock and detonation solvers.
  - Optimized the `ChemicalSystem` class by avoiding `get` methods for `indexElements` and `indexSpecies`, reducing overhead.
  - Improved `Units` class performance by replacing handle functions with direct conversion factors.
  
- **New `MixtureConfig` class:**  
  - Introduced to handle configuration settings for `Mixture` objects.
  - Supports `mol`, `molar fraction`, or `mass fraction` composition units.
  - Allows for compact composition output using the `FLAG_COMPACT` option.

- Include `setTemperatureSpecies` method to define **initial temperatures for each species in a mixture**.

  - **Key Features:**
    - Custom initialization of temperatures for individual species.
    - Automatic computation of equilibrium temperature.
    - Thermodynamic recalculations after changes in composition.
  
  - **Example Usage:**
    ```matlab
    set(mix, {'CH4'}, 'fuel', 1);
    set(mix, {'O2'}, 'oxidizer', 1);
    setTemperatureSpecies(mix, [300, 350]);
    ```


---

### **5. New Standalone Installer (`INSTALL_STANDALONE.sh`)**
A **cross-platform Bash script** to **automate installation** of the standalone version.

- **Key Features:**
  - Detects the **operating system** (Windows, macOS, or Linux).
  - Fetches the latest **release assets** from GitHub.
  - Extracts and executes the appropriate installer.

- **Usage Instructions:**
  ```bash
  sh INSTALL_STANDALONE.sh
  ```

- **Repository Optimization:**
  - Standalone installers are no longer stored in the repository.
  - They are now included as **release assets** to reduce repository size and improve maintainability.

---

## **Bug Fixes and Refinements**

- **Fixed errors in thermochemical property calculations** using the frozen approximation.
- **Resolved issues with internal energy and enthalpy calculations** in the `Species` object.
- **Fixed `molesGuess` bug** in `Mixture`, ensuring proper behavior when `indexProducts` differs from `indexSpecies`.
- **Corrected errors in `rocketFAC` method** for subsonic regions.
- **Fixed `setListSpecies` method when complete combustion is selected.**
- **Extended equivalence ratio range** in `EXAMPLE_HP_COMPLETE_INCOMPLETE` to observe **soot formation**.
- **Updated comments and documentation** for clarity and maintainability.

---

**Full Changelog**: https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.1.3...v1.2.0