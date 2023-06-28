---
title: "Linear analysis on shock-turbulence interaction implemented with the Combustion Toolbox"
event: "Seminars"
event_url: "" 

location: University of Salento
address:
  city: "Lecce"
  country: "Italy"

summary: ""
abstract: "In this seminar, we present the development of an in-house thermochemical code ---hereafter referred to as Combustion Toolbox (CT)--- for the solution of problems that involve chemical equilibrium of gas- and condensed-phase species. The thermochemical properties are computed under the ideal gas approximation using an up-to-date version of NASA’s 9-coefficient polynomial fits. CT is programmed in MATLAB with a modular architecture composed of three main modules: CT-EQUIL, CT-SD and CT-ROCKET. The core module, CT-EQUIL, minimizes the Gibbs/Helmholtz free energy of the system, upon the condition that the mixture properties are defined by two functions of state. CT-SD solves processes that involve strong changes in dynamic pressure, such as steady shock and detonation waves under both normal and oblique incidence angles within the limits of regular shock reflections. Finally, CT-ROCKET estimates rocket engine performance under ideal conditions. The new tool is equipped with a versatile Graphical User Interface.\

We will also introduce a theoretical work based on the thermochemical effects of hypersonic shock waves interacting with weak turbulence in air. The problem begins with the prediction, based on first principles only, of the Hugoniot curve when the shock triggers vibrational excitation and molecular dissociation in a single-species diatomic gas. CT is used to extend this theory to include further effects, such as dissociation, ionization, and recombination in multi-species ideal gas mixtures. The post-shock gas properties are then used to compute the turbulent amplification across the shock using linear interaction analysis (LIA). The LIA results presented here for air indicate that the enstrophy, anisotropy, intensity, and turbulent kinetic energy (TKE) of the fluctuations are more amplified through the shock than in the thermochemical frozen case. Moreover, the turbulent Reynolds number is also amplified across the shock at hypersonic Mach numbers in the presence of dissociation and vibrational excitation, as opposed to the attenuation observed in the thermochemical frozen case. Multi-species effects reshape the TKE curve by rendering two maxima that fit fairly well within the O2 and N2 dissociation processes."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2023-02-15T17:30:00Z"
date_end: "2023-02-15T18:30:00Z"

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
url_slides: ""

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
