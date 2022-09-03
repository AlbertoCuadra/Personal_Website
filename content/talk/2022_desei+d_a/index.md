---
title: "Desarrollo de un código termoquímico para la evaluación de las propiedades teóricas de explosivos (CT-EXPLO) y la estimación del rendimiento de motores cohete (CT-ROCKET)"
event: IX Congreso Nacional de I+D en Defensa y Seguridad
event_url: https://www.tecnologiaeinnovacion.defensa.gob.es/es-es/Presentacion/deseid_2022/Paginas/Presentaci%C3%B3n.aspx

#location: Source Themes HQ
address:
  city: Pontevedra
  country: Spain

summary: Short talk presented in the 9th ''Congreso Nacional de I+D en Defensa y Seguridad''.
abstract: "Se presenta un código termoquímico (en adelante Combustion Toolbox, CT) para el cálculo de problemas de combustión gaseosa con especies condensadas, choques reactivos y no reactivos, descomposición exotérmica de materiales energéticos y rendimiento teórico de cohetes. En particular, se exponen dos de los cuatro módulos que lo componen: CT-EXPLO y CT-ROCKET. El primero permite evaluar las propiedades termodinámicas teóricas de materiales energéticos (altos explosivos y propulsantes). El segundo permite estimar el rendimiento teórico de motores cohetes considerando una cámara de combustión finita con área transversal constante. Para ello se utiliza la ecuación de estado semi-empírica BKW en CT-EXPLO y la ecuación de estado de gas ideal en CT-ROCKET. Las propiedades termodinámicas se obtienen utilizando los ajustes polinómicos de 9 coeficientes de la NASA que, a excepción de CT-EXPLO, incorporan la Third Millenium Database para combustión de gases ideales y fases condensadas con actualización de tablas termoquímicas activas. La herramienta, desarrollada en MATLAB, está equipada con una interfaz gráfica de usuario (GUI) y ha sido utilizada con éxito tanto a nivel docente como investigador durante los últimos tres años. Aunque CT-EXPLO se encuentra aún en fase de desarrollo, el resto de los módulos han pasado la fase de validación y los resultados están en excelente acuerdo con códigos termoquímicos de referencia: CEA de la NASA, CANTERA junto con el paquete SD-Toolbox del Caltech, y el código TEA. Salvo el módulo de explosivos CT-EXPLO, de difusión limitada, el resto de CT está sujeto a una licencia de código abierto GPLv3 a través de https://github.com/AlbertoCuadra/combustion_toolbox y su documentación se puede encontrar en la página web https://combustion-toolbox-website.readthedocs.io."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2022-11-15T09:00:00Z"
date_end: "2022-11-17T18:00:00Z"

# Schedule page publish date (NOT talk date).
publishDate: "2017-01-01T00:00:00Z"

authors: [admin, César Huete, Marcos Vera]
tags: [Combustion Toolbox, Thermochemistry, Rocket, Explosives]

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
url_pdf: "files/DESEi_D2022a.pdf"
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
