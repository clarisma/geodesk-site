---
layout: guide
title: Why Geodesk?
next: core-concepts.md
---
# Why GeoDesk?

Since its launch in 2004, a vibrant software ecosystem has emerged around OpenStreetMap. However, geospatial analytics remains a difficult task. Most processing tasks are resource-intensive, requiring high-end workstations and in-depth expertise. The OSM project was meant to democratize geospatial data, but these hurdles discourage many potential adopters.

GeoDesk aims to change all that.

TODO: why database matters

- **Compact file size**: GOLs are stored as single files, which are typically only 40 percent larger than the dataset in `.osm.pbf` format. This is a small fraction of the footprint of a traditional database.

- **Lightning-fast queries**: The most common spatial queries perform *fifty times faster* than their SQL equivalents.

- **Designed for OSM**: Unlike most spatial databases, GOLs store not only the geometries of features, but also support OSM concepts like relations.   

- **Simplified distribution** of OSM data: Any GOL can be turned into a compressed tile repository, from which users download only the regions they need. This greatly reduces storage and download costs.  

- **Easy to use**: The GeoDesk API provides a powerful query language based on familiar MapCSS. Results are returned as Java objects --- no need for tedious object-relational mapping. 

- Seamless integration with the [**Java Topology Suite (JTS)**](https://locationtech.github.io/jts/) for **advanced vector operations**: buffer, generalize, union, convex and concave hulls, triangulation, Voronoi diagrams, and much more.  
 
- **Modest hardware requirements**: GeoDesk performs well on just about any system that can run a 64-bit JVM.

