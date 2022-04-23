---
layout: guide
title:  Queries and Feature Collections
next:   goql.md
---
# Queries and Feature Collections

Geospatial applications typically work with subsets of features in a library, such as buildings in a town, or waterways in a particular region. These subsets are represented as **feature collections**, which are the result of **queries**.

All feature collections implement the [`Features`]({{site.javadoc}}feature/Features.html) interface, which provides methods to iterate the member features or constrain them further.

- `FeatureLibrary` itself is a feature collection, representing all features in the library.

- Feature collections are lightweight objects that merely described what should be returned; they don't actually contain any objects and take up minimal space. In other words, query execution is lazy: Features are fetched only once they are needed, in response to iteration or a call to `toList()`.

  You can assign queries to variables and pass them around, but be aware that once the 
  [underlying library has been closed](libraries#caution-closed), you **must not** call any of their methods (or iterate 
  over them).

- Feature collections can be **ordered** or **unordered**. Only the [nodes of a way](feature-subtypes#way) and the [members of a relation](feature-subtypes#relation) are ordered; all other query results are returned in arbitrary order.

Feature collections behave like Java `Collection` classes, and hence implement `size()`, `isEmpty()`, `contains()` and `toArray()`, as well as the ability to iterate. `Features` also offers these methods:  

- [`toList()`]({{site.javadoc}}feature/Features.html#toList()) creates an `ArrayList` containing all features in the collection.

- [`first()`]({{site.javadoc}}feature/Features.html#toList()) returns the first feature in the collection, or `null` if it is empty.

## Bounding-box queries

<img class="float" src="bboxes.png" width=360>

A **bounding box** (or **bbox**) describes an axis-aligned rectangle. Bounding-box queries are the most common type of spatial queries.

This type of query returns all features whose bounding box intersects with the bounding box of the query. Note that the result set may include features whose geometry itself does not fall inside the query bbox. Bounding-box queries are designed as a fast primary filter, intended to narrow down candidates from millions to a few hundred. To eliminate the false positives, you can then apply a second, stricter (but more computationally expensive) filter.   

- A bounding box may straddle the Antimeridian (+/- 180 degrees longitude). Features that
  cross the Antimeridian are returned as multiple `Feature` objects representing separate parts to the east and to the west.



A bounding box is represented by the [`Box`]({{site.javadoc}}core/Box.html) class, which offers multiple static factory methods. To create a `Box` from coordinates (longitude and latitude), use [`ofWSEN()`]({{site.javadoc}}core/Box.html#ofWSEN(double,double,double,double)):

```java
Box bbox = Box.ofWSEN(8.42, 53.75, 9.07, 53.98);   // West, South, East, North
```

To obtain the features in a given bbox, use [`in()`]({{site.javadoc}}feature/Features.html#in(com.geodesk.core.Bounds)): 

```java
Features<?> subset = features.in(bbox);   
```

## Filtering by type and tags

Features in a collection can be filtered by type:

```java
Features<Node>     nodes();
Features<Way>      ways();
Features<Relation> relations();   
```

There are also four methods that take a query string:

```java
Features<?>        features(String query);
Features<Node>     nodes(String query);
Features<Way>      ways(String query);
Features<Relation> relations(String query);
```

For example:

```java
nodes("emergency=fire_hydrant")   // nodes that represent fire hydrants
features("na[amenity=pub,cafe]")  // pubs and cafes (nodes and areas)
relations("route=bicycle")        // cycling routes  
```

The [next chapter](goql) covers the GeoDesk query language in detail.

- Some queries always produce an empty collection. For example, `nodes("a")` is always
  empty: areas can be of type `Way` or `Relation`, but never `Node`.


## Predicates

More sophisticated predicates are represented as `Predicate` objects, which can be applied to a collection using `that()`:

```java
library.ways().that(predicate)
```

`Predicate` provides static factory method for common spatial predicates (see below). To make your code more readable, use:

```java
import static com.geodesk.feature.Predicate.*;
...
library.ways().that(intersect(someFeature)) // = Predicate.intersect(...)
```

## Built-in spatial predicates

`Predicate` provides the following factory methods to test features for spatial relationships with a `Geometry` or `PreparedGeometry` object, or another `Feature`.

### <code>contain(<i>A</i>)</code>

Selects features that **contain** *A*:

- Every point of *A* is a point of the candidate feature, and the interiors of the two geometries have at least one point in common.

### <code>containedBy(<i>A</i>)</code>

Selects features that are **contained by** *A*:

- Every point of the candidate feature is a point of *A*, and the interiors of the two geometries have at least one point in common.

### <code>cross(<i>A</i>)</code>

Selects features that **cross** *A*:

- The geometries of *A* and the candidate feature have some (but not all) interior points in common

### <code>intersect(<i>A</i>)</code>

Selects features that **intersect** *A*:

- The geometries of *A* and the candidate feature have at least one point in common

### <code>maxMetersFrom(<i>m</i>, <i>A</i>)</code>

Selects features whose distance to *A* is less or equal to *m* meters (measured between the closest points of the candidate feature and *A*).

### <code>touch(<i>A</i>)</code>

Selects features that **touch** *A*:

- The geometries of *A* and the candidate feature have at least one point in common, but their interiors do not intersect.










