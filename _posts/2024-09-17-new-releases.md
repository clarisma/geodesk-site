---
date: 2024-09-17
title: "New Releases: 0.2 (Python) & 0.2.1 (Java)"
categories:
  - releases
---
We've shipped two releases today:

# GeoDesk for Python 0.2

- *Breaking changes*: The filter methods `intersects`, `contains` and `crosses` are now
  called `intersecting`, `containing` and `crossing`, matching the naming style used by GeoDesk for Java. 

   Examples:

    ```
    areas.containing(my_location)
    bridges.crossing(danube)
    ``` 

- Support for Python 3.13
  
- Support for ARM-based Macs (experimental)

- Various bug fixes concerning the handling of numeric tag values and spatial-filter edge cases

Install / upgrade: `pip install geodesk -U`

# GeoDesk for Java 0.2.1

We've completed the transition to the simplified API, which now covers all relational operations, such as `Feature.parents()`.

For Maven projects, use:

```
<dependency>
    <groupId>com.geodesk</groupId>
    <artifactId>geodesk</artifactId>
    <version>0.2.1</version>
</dependency>
```

For Gradle:

```
dependencies { implementation 'com.geodesk:geodesk:0.2.1' }
```