---
title: "Combustion Toolbox: A MATLAB-GUI based open-source tool for solving gaseous combustion problems"
authors:
- admin
- César Huete
- Marcos Vera
# Departamento de Ingeniería Térmica y de Fluidos, Universidad Carlos III de Madrid, 28911 Leganés, Spain
date: "2022-02-09T00:00:00Z"
doi: "https://doi.org/10.5281/zenodo.5554911"

# Schedule page publish date (NOT publication's date).
publishDate: "2019-02-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["8"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "(v0.9.99c). Zenodo. https://doi.org/10.5281/zenodo.5554911"

abstract: "In this work, we present the development of a new thermochemical code (hereafter Combustion Toolbox, CT) that can be applied to gaseous combustion problems, even with condensed species. The kernel of the code is based in NASA’s Chemical Equilibrium with Applications (CEA) code. The corresponding thermodynamic properties of the species are modelled with the ideal gas equation of state and an up-to-date version of NASA’s 9-coefficient polynomial fits that uses the Third millenium database which includes part of the active thermochemical tables (ATcT). Combustion Toolbox is written in a modular architectural format composed of three main modules: CT-EQUIL, CT-SD and CT-ROCKET. Firstly, CT-EQUIL stems from the minimization of the Gibbs free energy of the system using Lagrange multipliers combined with a multidimensional Newton-Raphson method, upon the condition that the mixture properties are defined by two functions of states (e.g., enthalpy and pressure). Secondly, CT-SD solves processes that involve strong changes in the dynamic pressure, such as detonations and shock waves in steady state for either normal or oblique stream configurations, including regular shock reflections. Lastly, CT-ROCKET estimates rocket propellant performance in ideal conditions. The tool has been equipped with a Graphical User Interface (GUI) developed in MATLAB and has been successfully used for both teaching and research in BSc and MSc Thesis over the last three years. Results are in excellent agreement with NASA's CEA code, CANTERA within Caltech's Shock and Detonation Toolbox (SD-Toolbox), and TEA code. Combustion Toolbox is available under an open-source GPLv3 license via https://github.com/AlbertoCuadra/combustion_toolbox and its documentation can be found in the website  https://combustion-toolbox-website.readthedocs.io."

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

links:
- name: Website
  url: 'https://combustion-toolbox-website.readthedocs.io'

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
