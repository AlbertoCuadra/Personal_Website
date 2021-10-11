---
title: "Combustion Toolbox: A MATLAB-GUI based open-source tool for solving combustion problems"
authors:
- admin
- César Huete
- Marcos Vera
# Departamento de Ingeniería Térmica y de Fluidos, Universidad Carlos III de Madrid, 28911 Leganés, Spain
date: "2021-10-07T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2019-02-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["8"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "(v0.3.65). Zenodo. https://doi.org/10.5281/zenodo.5554911"

abstract: As a first step towards the development of a wider-scope thermochemical tool, in this work we present a thermochemical code with application to gaseous combustion problems recently implemented by the authors in MATLAB and Python. The MATLAB version solves six chemical equilibrium problems (`TP, HP, SP, TV, EV and SV transformations`; where T denotes temperature, P pressure, H enthalpy, S entropy, E internal energy and V volume), `incident and reflected planar shock waves`, as well as `ideal detonations according to Chapman-Jouguet theory and overdriven detonations`, assuming always ideal gases in all cases. The code also computes equilibrium properties of ideal plasmas, i.e., no coulombic interactions are considered. Moreover, part of our theoretical work "Thermochemical effects on hypersonic shock waves interacting with weak turbulence" is included. This allow us to compute from a theoretical perspective the jump conditions of an incident shock wave of a diatomic species (e.g., N2, O2, H2, F2) considering only dissociation of the species. The code computes the equilibrium composition by minimization of the Gibbs–Helmholtz free energy by using Lagrange multipliers, and employs NASA’s 9-coefficient polynomial fits to evaluate the thermodynamic properties. Results computed with Combustion Toolbox have been validated against, and are in good agreement with, NASA’s Chemical Equilibrium with Applications (CEA) program, CANTERA and Caltech’s Shock and Detonation Toolbox. Along with the plain code, the new tool has been `equipped with a Graphical User Interface` developed in MATLAB 2021 under AppDesigner.

#Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Numerical code
- App
- Thermochemistry
- Shock waves
- MATLAB
- Open-source

featured: false

# links:
# - name: ""
#links:
#- icon: researchgate
#  icon_pack: fab
#  name: Follow
#  url: https://www.researchgate.net/profile/Alberto_Cuadra_Lara
#- icon: linkedin
#  icon_pack: fab
#  name: Follow
#  url: https://www.linkedin.com/in/albertocuadralara/

#   url: ""
url_pdf:
url_preprint:
url_code: 'https://github.com/AlbertoCuadra/combustion_toolbox'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ''
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: example
---

