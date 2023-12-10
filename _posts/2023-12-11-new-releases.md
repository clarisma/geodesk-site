---
date: 2023-12-11
title: "New Releases: 0.1.9 (Java) & 0.1.1 (Python)"
categories:
  - releases
---
We've shipped two releases today:

# GeoDesk for Java 0.1.9

Includes the GOL Tool ([download here](https://github.com/clarisma/gol-tool/releases/download/0.1.9/gol-tool-0.1.9.zip))

## Bug Fixes

- `OsmPbfReader` now shuts down cleanly when reading a corrupt source file ([gol-tool#104](https://github.com/clarisma/gol-tool/issues/104)) -- this bug caused `gol build` to hang on truncated `.osm.pbf` files. 

- `gol build`: Fixed encoding bug that caused access to certain way-nodes to fail ([gol-tool#105](https://github.com/clarisma/gol-tool/issues/105))
  *Note: We recommend re-building any GOL with more than 16K tiles* 

## Other Changes

- `MapMaker` now uses the standard OSM Carto style by default ([geodesk-py#17](https://github.com/clarisma/geodesk-py/issues/17))

# GeoDesk for Python 0.1.1

Install / upgrade: `pip install geodesk -U`

## Enhancements

- Creating `Coordinate` objects is now easier using `lonlat()` and `latlon()` ([geodesk-py#10](https://github.com/clarisma/geodesk-py/issues/10))

- Feature sets now support `__contains__` for Python's `in` operator ([geodesk-py#23](https://github.com/clarisma/geodesk-py/issues/23))

- Number of tags in a `Tags` object can now be obtained using `len()` 

- Partial support for `Features.tiles`

## Deprecations

- `Feature.is_placeholder` has been deprecated and will be removed in the next major release. Missing relation members will no longer be represented by a "placeholder" feature, but will be omitted from the relation, and the relation will be tagged `geodesk:missing_members=yes`. 

## Bug fixes

- `Features.members_of()` now properly returns an empty set if called on features that are not relations ([geodesk-py#18](https://github.com/clarisma/geodesk-py/issues/18))

- `Tags`: Fixed bug that caused certain tags to be skipped while iterating

## Other changes

- Maps now use the standard OSM Carto style by default ([geodesk-py#17](https://github.com/clarisma/geodesk-py/issues/17))

## Related issues & workarounds

- [geodesk-py#19](https://github.com/clarisma/geodesk-py/issues/19): Way-node retrieval may fail when querying large GOLs (16K+ tiles) that were built with 
  GOL Tool version 0.1.8 or below, due to an encoding bug in `gol build` (gol-tool#105). 
  We recommend upgrading your GOL Tool and re-building any affected GOLs.

