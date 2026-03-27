---
title: "New JFM Publication: Compressibility and Vibrational Effects in Hypersonic STI"
date: 2026-03-27
lastmod: 2026-03-27
math: true
diagram: true
publishDate: "2026-03-27T00:00:00Z"
tags:
- LIA
- DNS
- Hypersonics
- Compressible turbulence
- Shock waves

links:
- name: DOI
  url: 'https://doi.org/10.1017/jfm.2026.11355'
---

[![Preview](/gif/cuadra2026b_dns.gif)](https://doi.org/10.1017/jfm.2026.11355)

I am very happy to share that our latest article, "The role of compressibility and vibrational excitation in hypersonic shock-turbulence interactions", has just been published in the Journal of Fluid Mechanics.

This work represents a long-standing collaboration between Universidad Carlos III de Madrid, Stanford University, and Università del Salento, originally initiated during the 2024 Summer Program at the Center for Turbulence Research (CTR) at Stanford.

We present a combined theoretical and numerical study (LIA & DNS) to further understand how shocks modulate turbulence under the intrinsic compressibility and vibrational excitation effects of hypersonic flight.

**Key findings & contributions:**

- We introduced a generalized LIA framework --- implemented within the Combustion Toolbox ecosystem --- that predicts the linear response of compressible homogeneous isotropic turbulence interacting with a planar shock wave while accounting for thermochemical effects.
- Our results at Mach 5 show that increasing upstream compressibility significantly enhances TKE amplification; even a modest 10% dilatational content can increase TKE by ~43%.
- We found that vibrational excitation further strengthens downstream turbulence amplification; an effect that LIA estimates to become more dominant as shock strength increases at higher Mach numbers.
- We demonstrate that LIA captures relative TKE amplification remarkably well at a fraction (milliseconds) of the high computational cost of DNS.
- We propose an improved LIA-based estimate for the post-shock Kolmogorov length scale, providing a reliable "safe basis" for determining spatial resolution requirements in future numerical STI studies.

Understanding these dynamics is a critical step toward accurately predicting heat transfer and aerodynamic stability in next-generation aerospace vehicles.

A huge thanks to my co-authors Christopher Williams, Mario Di Renzo, and César Huete!

**Read the Open Access paper here:** https://doi.org/10.1017/jfm.2026.11355 

**Check out the LIA implementation in the Combustion Toolbox:** https://combustion-toolbox-website.readthedocs.io/
