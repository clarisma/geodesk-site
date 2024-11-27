---
date: 2024-11-27
title: "GeoDesk for C++"
categories:
  - releases
---
We’re excited to announce the latest edition of our GeoDesk OpenStreetMap Toolkit, this time for C++. 

The GeoDesk C++ library is lightweight (250 KB compiled), without any link-time dependencies. It supports Windows, Linux and MacOS. Its query engine runs entirely in-process, without any need for a database server or other external services. And, of course, it's free and open-source. 

Just like its [Java](https://docs.geodesk.com/java) and [Python](https://docs.geodesk.com/python) cousins, GeoDesk for C++ supports a wide range of queries (`within()`, `around()`, `crossing()`, nodes of a way, members of a relation) and standard geospatial operations, such as computing areas and distances. For more advanced capabilities, you can also integrate it with the popular [GEOS](https://libgeos.org/) library.

- [Documentation](https://docs.geodesk.com/cpp)
 
- [API Reference](https://cppdoc.geodesk.com)
 
- [GitHub](https://github.com/clarisma/libgeodesk)
 
This is an **early access** release -- some of the documented capabilities are not yet fully implemented (Please see the [release notes](https://github.com/clarisma/libgeodesk/releases/tag/v0.1) for details). As always, we're grateful for [bug reports](https://github.com/clarisma/libgeodesk/issues) and other suggestions for improvement.
