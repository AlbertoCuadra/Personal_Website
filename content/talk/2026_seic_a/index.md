---
title: "Combustion Toolbox: A reduced-order framework for high-speed reactive flows"
event: 2026 Joint Meeting of the Italian and Spanish Sections of The Combustion Institute
event_url: "https://www.combustion-institute.it/news-events/58-48th-meeting.html"

location: "Piano di Sorrento"
address:
  city: "Sorrento"
  country: "Italy"

summary: Poster presentation in the 2026 Joint Meeting of the Italian and Spanish Sections of The Combustion Institute
abstract: "Hypersonic propulsion systems operate in a regime where compressibility, shock–turbulence interactions, aerodynamic heating, combustion, transport phenomena, and thermochemical effects are strongly coupled. In scramjets, rotating detonation engines (RDEs), and related high-speed propulsion concepts, preliminary design requires tools capable of capturing the dominant gas-dynamic and thermochemical mechanisms at a fraction of the cost of high-fidelity multidimensional simulations. Combustion Toolbox (CT) is an open-source MATLAB framework, with graphical and command-line interfaces, originally developed for chemical-equilibrium calculations and later extended to shock, detonation, and propulsion applications. Here, we present recent and ongoing developments that expand the object-oriented CT ecosystem into a unified framework for high-speed reactive-flow modeling. First, CT now includes tools for scramjet compression-system design and internal-flow analysis. Inlet optimization is formulated as an oblique-shock problem in which multi-ramp geometries are obtained by maximizing total-pressure recovery subject to prescribed exit conditions. The approach extends beyond calorically perfect gases through efficient thermochemical-equilibrium calculations. In parallel, CT incorporates a quasi-one-dimensional solver for internal-flow calculations in isolators, combustors, and nozzles, accounting for variable-area effects, wall losses, fuel injection, mixing models, and finite-rate chemistry. Second, the CT shock-and-detonation solver has been extended with new wave-solution families, including Prandtl-Meyer expansions for multiple caloric models. These elements are being combined through compatibility conditions to construct multi-region wave-network solutions relevant to high-speed propulsion systems, including RDEs. Third, CT now includes CT-LIA, a linear interaction analysis module for quantifying turbulence amplification across shock waves in multi-component reactive mixtures. The model applies to inert and reactive shocks under different upstream perturbation modes and has recently been extended to non-ideal equations of state under frozen composition. These developments establish CT as a modular framework for high-speed reactive-flow analysis."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2026-05-28T10:30:00Z"
date_end: "2026-05-28T17:00:00Z"

# Schedule page publish date (NOT talk date).
publishDate: "2017-01-01T00:00:00Z"

authors: [admin, M. Vera, César Huete]
tags: [Hypersonics, Scramjet, Combustion Toolbox]

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
url_poster: 
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

