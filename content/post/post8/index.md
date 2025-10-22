---
title: "Combustion Toolbox v1.2.7 Released"
date: 2025-10-14
lastmod: 2025-10-14
math: true
diagram: true
publishDate: "2025-10-14T00:00:00Z"

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
  url: 'https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.0...v1.2.7'
---

This release introduces new capabilities, plasma diagnostics, updated database (Burcat, January 2023), bug fixes, and performance improvements across the **Combustion Toolbox** framework.

## 1. New `JumpConditionsSolver` class for calculation of dimensionless Rankine–Hugoniot slopes
A dedicated solver class has been implemented to compute **thermochemical Rankine–Hugoniot jump conditions** and the **dimensionless RH slopes** required in shock-turbulence interaction linear analysis (*[Cuadra2024b](https://web.stanford.edu/group/ctr/ctrsp24/iii01_CUADRA.pdf), [Cuadra2025a](https://doi.org/10.1063/5.0255816)*).

- Computes upstream/downstream shock states with thermochemistry.
- Provides direct access to **RH slope parameters** for post-processing of STI amplification factors.
- Implemented as a standalone solver, ready for integration with the upcoming `ShockTurbulenceSolver` module.

## 2. Plasma diagnostics for weakly ionized mixtures

A new diagnostic suite has been added to the `Mixture` class to evaluate whether a reacting gas mixture can be treated as a **weakly ionized plasma**, i.e., when Coulomb interactions remain negligible.

### New diagnostic quantities:
- **Electron number density** $(\hat{n}_e)$
- **Ion number density** $(\hat{n}_i)$
- **Degree of ionization** $(\chi)$
- **Debye length** $(\lambda_D)$
- **Number of electrons in a Debye sphere** $(N_D)$
- **Species-wise plasma coupling parameter** $(\mathcal{G}_j)$
- **Mean plasma coupling parameter** $(\mathcal{G})$
- Detection of **weakly coupled plasmas** based on the condition $(\mathcal{G} \ll 1)$

## 3. New thermodynamic setters in `Mixture` class

Three new state-setting methods are now available in `Mixture`, allowing the thermodynamic state to be directly defined using entropy, enthalpy, or internal energy, namely

- `setEntropy`
- `setEnthalpy`
- `setInternalEnergy`

## 4. Burcat's database updated to January 2023 release

The Burcat thermochemical database has been updated to the latest publicly available version (January 2023).

## 5. New `Benchmark` class for automated performance analysis

A new utility class has been developed to systematically evaluate the computational performance of the Combustion Toolbox framework across different problem types and hardware configurations.

𝗕𝗘𝗡𝗖𝗛𝗠𝗔𝗥𝗞 𝗥𝗘𝗣𝗢𝗥𝗧


𝗦𝘆𝘀𝘁𝗲𝗺 𝗜𝗻𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻

    CT version    MATLAB version    OS version      CPU name      Clock speed    Cache L2    Cores
    __________    ______________    __________    ____________    ___________    ________    _____

      1.2.7           R2025b          15.6.1      Apple M2 Pro        N/A         65536       10

𝗕𝗲𝗻𝗰𝗵𝗺𝗮𝗿𝗸𝗶𝗻𝗴

     Module           Solver                Problem                             Filename                       Cases    Species    Tolerance    AvgTime
    _________    _________________    ___________________    ______________________________________________    _____    _______    _________    _______

    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_TEA_1                            300        12      1.00e-06      1.2725
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_TEA_2                             90        26      1.00e-06      0.9694
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_TEA_3                             90        26      1.00e-06     0.96146
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_TEA_4                             90        26      1.00e-06     0.94948
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_1                            351        94      1.00e-06      1.5101
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_2                            351        94      1.00e-06      1.4609
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_3                            351        94      1.00e-06      1.3866
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_4                            351        94      1.00e-06      1.4681
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_5                            181       247      1.00e-06       1.449
    CT-EQUIL     EquilibriumSolver    TP                     run_validation_TP_CEA_6                            481       177      1.00e-06       1.992
    CT-EQUIL     EquilibriumSolver    TV                     run_validation_TV_CEA_1                            351        94      1.00e-06       1.476
    CT-EQUIL     EquilibriumSolver    TV                     run_validation_TV_CEA_2                            351       213      1.00e-06      1.7019
    CT-EQUIL     EquilibriumSolver    HP                     run_validation_HP_CEA_1                            351        94      1.00e-03      2.0117
    CT-EQUIL     EquilibriumSolver    HP                     run_validation_HP_CEA_2                            351        94      1.00e-03      1.9549
    CT-EQUIL     EquilibriumSolver    HP                     run_validation_HP_CEA_3                            351        94      1.00e-03      1.9791
    CT-EQUIL     EquilibriumSolver    HP                     run_validation_HP_CEA_4                            351        94      1.00e-03      1.9141
    CT-EQUIL     EquilibriumSolver    EV                     run_validation_EV_CEA_1                            351        94      1.00e-03      1.9471
    CT-EQUIL     EquilibriumSolver    SP                     run_validation_SP_CEA_1                            351        94      1.00e-03      3.1354
    CT-EQUIL     EquilibriumSolver    SV                     run_validation_SV_CEA_1                            351        94      1.00e-03      3.1185
    CT-SD        ShockSolver          SHOCK_I                run_validation_SHOCK_IONIZATION_CEA_1              260        51      1.00e-05      1.5735
    CT-SD        ShockSolver          SHOCK_I                run_validation_SHOCK_IONIZATION_CEA_2              260        61      1.00e-05      1.6415
    CT-SD        ShockSolver          SHOCK_R                run_validation_SHOCK_R_IONIZATION_CEA_1            225        51      1.00e-05      1.9375
    CT-SD        ShockSolver          SHOCK_R                run_validation_SHOCK_R_IONIZATION_CEA_2            225        61      1.00e-05      2.0467
    CT-SD        ShockSolver          SHOCK_POLAR            run_validation_SHOCK_POLAR_SDToolbox_1               4        11      1.00e-05      2.3553
    CT-SD        ShockSolver          SHOCK_POLAR            run_validation_SHOCK_POLAR_SDToolbox_2               4        13      1.00e-05       2.397
    CT-SD        DetonationSolver     DET                    run_validation_DET_CEA_1                           351        94      1.00e-05      2.4159
    CT-SD        DetonationSolver     DET                    run_validation_DET_CEA_2                           351       157      1.00e-05      3.0528
    CT-SD        DetonationSolver     DET                    run_validation_DET_CEA_3                           351        94      1.00e-05      2.0356
    CT-SD        DetonationSolver     DET                    run_validation_DET_CEA_4                           351        94      1.00e-05       1.893
    CT-SD        DetonationSolver     DET_OVERDRIVEN         run_validation_DET_OVERDRIVEN_SDToolbox_1           91        25      1.00e-05       1.287
    CT-SD        DetonationSolver     DET_POLAR              run_validation_DET_POLAR_SDToolbox_1                 5        30      1.00e-05      2.7438
    CT-ROCKET    RocketSolver         ROCKET_FAC             run_validation_ROCKET_CEA_20                       351        96      1.00e-04      12.305
    CT-ROCKET    RocketSolver         ROCKET_FAC             run_validation_ROCKET_CEA_21                       351        96      1.00e-04      10.445
    CT-ROCKET    RocketSolver         ROCKET_FAC             run_validation_ROCKET_CEA_22                       351        12      1.00e-04      5.1941
    CT-ROCKET    RocketSolver         ROCKET_FAC             run_validation_ROCKET_CEA_23                       351        96      1.00e-04      10.516
    CT-ROCKET    RocketSolver         ROCKET_IAC             run_validation_ROCKET_CEA_24                       351        12      1.00e-04      2.8258
    CT-ROCKET    RocketSolver         ROCKET_IAC             run_validation_ROCKET_CEA_25                       351        12      1.00e-04      1.8727

𝗦𝘂𝗺𝗺𝗮𝗿𝘆 𝗕𝗲𝗻𝗰𝗵𝗺𝗮𝗿𝗸𝗶𝗻𝗴

     Module            Problem          GroupCount    sum_Cases    mean_Cases    sum_Species    mean_Species    sum_AvgTime    mean_AvgTime
    _________    ___________________    __________    _________    __________    ___________    ____________    ___________    ____________

    CT-EQUIL     TP                         10          2636         263.6           890               89          13.42           1.342
    CT-EQUIL     TV                          2           702           351           307            153.5         3.1779           1.589
    CT-EQUIL     HP                          4          1404           351           376               94         7.8598          1.9649
    CT-EQUIL     EV                          1           351           351            94               94         1.9471          1.9471
    CT-EQUIL     SP                          1           351           351            94               94         3.1354          3.1354
    CT-EQUIL     SV                          1           351           351            94               94         3.1185          3.1185
    CT-SD        SHOCK_I                     2           520           260           112               56         3.2151          1.6075
    CT-SD        SHOCK_R                     2           450           225           112               56         3.9842          1.9921
    CT-SD        SHOCK_POLAR                 2             8             4            24               12         4.7522          2.3761
    CT-SD        DET                         4          1404           351           439           109.75         9.3973          2.3493
    CT-SD        DET_OVERDRIVEN              1            91            91            25               25          1.287           1.287
    CT-SD        DET_POLAR                   1             5             5            30               30         2.7438          2.7438
    CT-ROCKET    ROCKET_FAC                  4          1404           351           300               75         38.459          9.6149
    CT-ROCKET    ROCKET_IAC                  2           702           351            24               12         4.6985          2.3492
    
## Bug Fixes and Refinements

* Corrected duplicated and inconsistent species naming in `BurcatDatabase`.
* Added database merge operator `+` to combine NASA and Burcat sources with conflict control.
* Replaced repeated thermo evaluation calls with `updatePropertiesMatrixThermo`, avoiding redundant struct access and enabling persistent caching of thermodynamic curve handles.
* Update `generateDatabase` to trigger when `thermoFile` is provided and assign deterministic IDs to merged database object.
* Fixed specific volume (`vSpecific`) calculation when condensed species are present.
* Rename `thermoMillennium_2_thermoNASA9` to `thermoMillennium2thermoNASA9` for naming consistency.
* Assigned a deterministic 32-bit ID to each `Species` object entry.
* Resolved convergence error in `DetonationCJ` method within `DetonationSolver` when the initial guess falls below tolerance.
* Updated all `Example_*` files: removed manual `listSpecies` definitions in `ChemicalSystem` in favor of automatic selection and adopted the `report` method in solvers for cleaner output formatting.

---

**Full Changelog**: https://github.com/CombustionToolbox/combustion_toolbox/compare/v1.2.0...v1.2.7
