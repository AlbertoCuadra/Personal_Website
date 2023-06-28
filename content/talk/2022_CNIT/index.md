---
title: "Combustion Toolbox: an open source thermochemical code for solving gaseous combustion problems"
event: XII National and III International Conference on Engineering Thermodynamics
event_url: https://eventos.uc3m.es/46084.html

location: Universidad Carlos III de Madrid-Puerta de Toledo Campus
address:
  city: Madrid
  country: Spain

summary: Short talk presented in the 12th National and III International Conference on Engineering Thermodynamics.
abstract: "In this work, we present the development of a new thermochemical code (hereafter Combustion Toolbox, CT) that can be applied to gaseous combustion problems, even with condensed species. The kernel of the code is based in NASA’s Chemical Equilibrium with Applications (CEA) code. The corresponding thermodynamic properties of the species are modelled with the ideal gas equation of state and an up-to-date version of NASA’s 9-coefficient polynomial fits that uses the Third millenium database which includes part of the active thermochemical tables (ATcT). Combustion Toolbox is written in a modular architectural format composed of three main modules: CT-EQUIL, CT-SD and CT-ROCKET. Firstly, CT-EQUIL stems from the minimization of the Gibbs free energy of the system using Lagrange multipliers combined with a multidimensional Newton-Raphson method, upon the condition that the mixture properties are defined by two functions of states (e.g., enthalpy and pressure). Secondly, CT-SD solves processes that involve strong changes in the dynamic pressure, such as detonations and shock waves in steady state for either normal or oblique stream configurations, including regular shock reflections. Lastly, CT-ROCKET (not presented here) estimates rocket propellant performance in ideal conditions. The tool has been equipped with a Graphical User Interface (GUI) developed in MATLAB and has been successfully used for both teaching and research in BSc and MSc Thesis over the last three years. Results are in excellent agreement with NASA's CEA code, CANTERA within Caltech's Shock and Detonation Toolbox (SD-Toolbox), and TEA code. Combustion Toolbox is available under an open-source GPLv3 license via https://github.com/AlbertoCuadra/combustion_toolbox and its documentation can be found in the website  https://combustion-toolbox-website.readthedocs.io."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2022-06-29T16:15:00Z"
date_end: "2022-07-01T18:15:00Z"

# Schedule page publish date (NOT talk date).
publishDate: "2017-01-01T00:00:00Z"

authors: [admin, César Huete, Marcos Vera]
tags: [Combustion Toolbox, Thermochemistry, Shocks waves]

# Is this a featured talk? (true/false)
featured: false

image:
  caption: ""

links:
- icon: researchgate
  icon_pack: fab
  name: Follow
  url: https://www.researchgate.net/profile/Alberto_Cuadra_Lara
- icon: linkedin
  icon_pack: fab
  name: Follow
  url: https://www.linkedin.com/in/albertocuadralara/
url_pdf: ""
url_code: ""
url_poster: ""
url_slides: ""
url_video: ""

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
#projects:
#- internal-project

# Enable math on this page?
math: true
---
