---
date: 2026-07-13
title: "GOL 2.3: Export query results as OSM PBF"
categories:
  - releases
---
We just released GOL Tool 2.3, which now allows you to export the results of a query in OSM PBF format. This makes it easy to create regional or thematic extracts.

You can also filter tags using the `--keys` (`-k`) option.

Example:

```
gol query germany na[amenity=restaurant] 
    -a bavaria.wkt 
    -k amenity,cuisine,opening_hours 
    > restaurants.osm.pbf
```

This queries `germany.gol` and creates a PBF containing all restaurants in Bavaria (specified as a Well-Known Text multipolygon), including only the `amenity`, `cuisine` and `opening_hours` tags.

To ensure that untagged way-nodes are included in the output, build or load your GOL with the `--waynode-ids` (`-w`) option.

To get the (multi)polygon for the query's `--area` (`-a`) option, first export the desired region like this:

```
gol query germany a[boundary=administrative][name:en=Bavaria] 
    > bavaria.wkt
```

[Download](https://www.geodesk.com/download) / [GitHub](https://github.com/clarisma/geodesk-gol) / [Documentation](https://docs.geodesk.com/gol)