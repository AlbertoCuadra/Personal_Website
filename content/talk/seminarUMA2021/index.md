---
title: "Seminar on the development of an open-source thermochemical code: basics and applications into shock-turbulence interaction problems in the hypersonic regime"
event: "Seminars"
event_url: "" 

#location: Source Themes HQ
address:
  city: "Málaga"
  country: "Spain"

summary: ""
abstract: "We present the basics of how we have developed a thermochemical code (hereafter Combustion-Toolbox) for solving gaseous combustion problems by minimization of the Gibbs–Helmholtz free energy by using Lagrange multipliers. To evaluate the thermodynamic properties the code employs NASA’s 9-coefficient polynomial fits. We will see the general formulation to solve any equilibrium problem defined by a pair of thermodynamic inputs, e.g., enthalpy and pressure. Combustion Toolbox also solves incident and reflected planar shock waves, as well as ideal detonations according to Chapman-Jouguet theory and overdriven detonations, assuming always ideal gases. The code also computes equilibrium properties of ideal plasmas, i.e., no coulombic interactions are considered. The tool has been equipped with a Graphical User Interface developed in MATLAB 2021 under AppDesigner. A preview of the tool will be shown. Second, we introduce a theoretical work based on the thermochemical effects of hypersonic shock waves interacting with weak turbulence and how we have extended this theory using Combustion Toolbox. The theoretical study begins obtaining modified Rankine-Hugoniot jump conditions that account for dissociation and vibrational excitation by using linear interaction analysis (LIA). These jump conditions have been employed in a Fourier analysis of a hypersonic shock interacting with three-dimensional isotropic vortical disturbances. Besides confirming known endothermic effects of hypersonic thermochemistry in decreasing the mean post-shock temperature and velocity, these LIA results indicate that the enstrophy, anisotropy, intensity, and turbulent kinetic energy of the fluctuations are much more amplified through the shock than in the calorically perfect case. Additionally, the turbulent Reynolds number is amplified across the shock at hypersonic Mach numbers in the presence of dissociation and vibrational excitation, as opposed to the attenuation observed in the calorically perfect case. These results suggest that thermochemical effects arising at hypersonic velocities appear to enhance turbulent fluctuations in the post-shock gas."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2021-12-15T11:00:00Z"
date_end: "2021-12-15T11:45:00Z"

# Schedule page publish date (NOT talk date).
publishDate: "2017-01-01T00:00:00Z"

authors: [admin, César Huete, Marcos Vera, Javier Urzay]
tags: [Thermochemistry, Thermochemical, Hypersonics, Shock Waves]

# Is this a featured talk? (true/false)
featured: true

image:
  caption: ''

links:
- icon: researchgate
  icon_pack: fab
  name: Follow
  url: https://www.researchgate.net/profile/Alberto_Cuadra_Lara
- icon: linkedin
  icon_pack: fab
  name: Follow
  url: https://www.linkedin.com/in/albertocuadralara/
url_code: ""
url_poster: ""
url_video: ""
url_slides: ""

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
