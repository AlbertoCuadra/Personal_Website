---
title: "Automating DOI extraction with Python"
date: 2023-11-30
math: true
diagram: true
# Schedule page publish date (NOT publication's date).
publishDate: "2023-11-30T00:00:00Z"
#image:
#  placement: 3
#  caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'

tags:
- Python
- BibTeX

#   url: ""
links:
- name: Github
  url: 'https://github.com/AlbertoCuadra/doi_scraper'
---

Greetings! A few months ago, I was working on – the [DOI Scraper](https://github.com/AlbertoCuadra/doi_scraper). This Python script reads a `.bib` file, hunts down articles without a DOI (Digital Object Identifier), and effortlessly fetches the missing DOIs using the [Crossref API](https://www.crossref.org/documentation/retrieve-metadata/rest-api/). It then updates the `.bib` file with the new data.

## Why Did I Create This?

As a researcher, citation management is a critical yet often time-consuming task. I frequently encountered articles missing DOIs, and the manual search for them proved to be a real headache. To save time and enhance efficiency, I decided to automate the process and share this tool with you all.

## Prerequisites

- Python
- `requests` library

## How to Get Started

1. Clone the repository or snag the `doi_scraper.py` file.
2. Install the required dependencies with:

```shell
pip install requests
```

## How to Use
Place your input `.bib` file in the script's directory, tweak a couple of variables in `doi_scraper.py` to fit your needs

```python
input_file = 'input.bib'   # Name of the input .bib file
output_file = 'output.bib' # Name of the output .bib file
INDENT_PRE = 4             # Number of spaces before the field name
INDENT_POST = 16           # Number of spaces after the field name
```

and run the script:

```shell
python doi_scraper.py
```

## Example

### Before
```bibtex
@article{Cuadra2020,
title            = {Effect of equivalence ratio fluctuations on planar detonation discontinuities},
author   = {Cuadra, Alberto and Huete, C{\'e}sar and Vera, Marcos},
year    = 2020,
journal  = {Journal of Fluid Mechanics},
publisher    = {Cambridge University Press},
volume       = 903,
pages= {A30 1--39}
}
```

## After

```bibtex
@article{Cuadra2020,
    title            = {Effect of equivalence ratio fluctuations on planar detonation discontinuities},
    author           = {Cuadra, Alberto and Huete, C{\'e}sar and Vera, Marcos},
    year             = 2020,
    journal          = {Journal of Fluid Mechanics},
    publisher        = {Cambridge University Press},
    volume           = 903,
    pages            = {A30 1--39},
    doi              = {10.1017/jfm.2020.651}
}
```

## License
This project is licensed under the MIT License.
