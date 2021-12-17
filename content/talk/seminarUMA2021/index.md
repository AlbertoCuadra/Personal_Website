---
title: "Development of an open-source thermochemical code: Fundamentals and application to shock turbulence interaction problems in the hypersonic regime"
event: "Seminars"
event_url: "" 

#location: Source Themes HQ
address:
  city: "Málaga"
  country: "Spain"

summary: ""
abstract: "In this seminar, we present the development of an in-house thermochemical code (hereafter Combustion-Toolbox) that can be applied to gaseous combustion problems. The code stems from the minimization of the Gibbs–Helmholtz free energy by using Lagrange multipliers, upon condition that initial gas properties are defined by two functions of states (e.g., enthalpy and pressure). The corresponding thermodynamic properties of the species are modelled with NASA’s 9-coefficient polynomial fits and the ideal gas equation of state. The tool has been equipped with a Graphical User Interface developed in MATLAB 2021 under AppDesigner. A preview of the tool will be shown. Combustion Toolbox can be used to solve processes that involve strong changes in the dynamic pressure, such as detonations and shock waves in the steady state. For sufficiently strong shocks, the code also takes into consideration effects like dissociation and ionization, i.e., equilibrium properties of ideal plasmas, which are of paramount importance in hypersonic conditions.\

We will also introduce a theoretical work based on the thermochemical effects of hypersonic shock waves interacting with weak turbulence. The problem begins with the prediction, based on first principles only, of the Hugoniot curve when the shock triggers vibrational excitation and molecular dissociation in a single-species diatomic gas. The results of the Combustion Toolbox are used to extend this theory to include further effects, such as ionization, dissociation and recombination in muti-species gases. The post-shock gas properties are then used to compute the turbulent amplification across the shock using linear interaction analysis (LIA): a Fourier analysis of a hypersonic shock interacting with three-dimensional small-amplitude isotropic vortical disturbances. Besides confirming known endothermic effects of hypersonic thermochemistry in decreasing the mean post-shock temperature and velocity, these LIA results indicate that the enstrophy, anisotropy, intensity, and turbulent kinetic energy of the fluctuations are much more amplified through the shock than in the calorically perfect case. Additionally, the turbulent Reynolds number is amplified across the shock at hypersonic Mach numbers in the presence of dissociation and vibrational excitation, as opposed to the attenuation observed in the calorically perfect case. These results suggest that thermochemical effects arising at hypersonic velocities appear to enhance turbulence in the post-shock gas."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2021-12-15T11:00:00Z"
date_end: "2021-12-15T11:45:00Z"

# Schedule page publish date (NOT talk date).
publishDate: "2017-01-01T00:00:00Z"

authors: [admin, César Huete, Marcos Vera]
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
url_slides: "files/Slides_seminar_UMA_2021_compressed.pdf"

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: ""

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
