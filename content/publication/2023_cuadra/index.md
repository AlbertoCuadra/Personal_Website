---
title: "Combustion Toolbox: An open-source thermochemical code for gas- and condensed-phase problems involving chemical equilibrium"
authors:
- admin
- César Huete
- Marcos Vera
# Departamento de Ingeniería Térmica y de Fluidos, Universidad Carlos III de Madrid, 28911 Leganés, Spain
date: "2023-06-20T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2019-02-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "Work in progress"

abstract: "We present a new thermochemical code---hereafter referred to as Combustion Toolbox (CT)---for the solution of problems that involve chemical equilibrium of gas- and condensed-phase species. The kernel of the code is based in the theoretical framework set forth by NASA's computer program CEA (Chemical Equilibrium with Applications), while incorporating new algorithms that result in a significant speed up of the convergence rate. The thermochemical properties are computed under the ideal gas approximation using an up-to-date version of NASA’s 9-coefficient polynomial fits. These fits use the Third Millenium Database which includes the available values from Active Thermochemical Tables. Combustion Toolbox is programmed in MATLAB with a modular architecture composed of three main modules: CT-EQUIL, CT-SD and CT-ROCKET. The core module, CT-EQUIL, minimizes the Gibbs/Helmholtz free energy of the system using the technique of Lagrange multipliers combined with a multidimensional Newton-Raphson method, upon the condition that the mixture properties are defined by two functions of state (e.g., enthalpy and pressure). CT-SD solves processes that involve strong changes in the dynamic pressure, such as steady shock and detonation waves under both normal or oblique incidence angles within the limits of regular shock reflections. Finally, CT-ROCKET estimates rocket engine performance under ideal conditions. The new tool is equipped with a versatile Graphical User Interface and has been successfully used for both teaching and research activities during the last three years. Results are in excellent agreement with CEA, CANTERA within Caltech's Shock and Detonation Toolbox (SD-Toolbox), and the recent Thermochemical Equilibrium Abundances (TEA) code. CT is available under an open-source GPLv3 license via Github https://github.com/AlbertoCuadra/combustion_toolbox and its documentation can be found in https://combustion-toolbox-website.readthedocs.io."

#Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- Numerical code
- App
- Thermochemistry
- Shock waves
- Detonations
- Oblique fronts
- Rocket performance

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
url_preprint: 'files/cuadra2023a_preprint.pdf'
url_code: ''
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

