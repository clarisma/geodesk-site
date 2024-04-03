---
date: 2024-04-03
title: Geometric Filters in GeoDesk for Python 0.1.10
categories:
  - releases
---

[GeoDesk for Python](https://docs.geodesk.com/python) Version 0.1.10 introduces **geometric filters**, which select features based on the properties of their shape. Four new filter methods are available in this release:

- `min_area()`

- `max_area()`
  
- `min_length()`

- `max_length()`

These filters are particularly useful for quality assurance of OpenStreetMap data -- they quickly identify features that are abnormally large or small, such as buildings that are classified as "houses," but in reality represent sheds or garages.

Install / upgrade: `pip install geodesk -U`

