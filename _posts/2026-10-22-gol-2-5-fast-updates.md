---
date: 2026-10-22
title: "GOL 2.5: Fast incremental updates"
categories:
  - releases
---

GOLs are now updatable, so you can keep your local copy current with the latest changes to OpenStreetMap.

This feature is available in GOL Tool 2.5 ([download](https://www.geodesk.com/download)). 

You will need to build your initial GOL using option `--waynode-ids` (`-w`), which preserves node IDs even for nodes without tags. For example:

```
gol build germany germany-latest.osm.pbf -w
```

After that, you can update the GOL to the latest available version:

```
gol update germany
```

By default, this uses the replication server specified in the original PBF. The [planet file](https://planet.openstreetmap.org/) and [Geofabrik extracts](https://download.geofabrik.de/) already contain suitable replication URLs.

If your PBF doesn't have one, or you want to use a different service, you can provide an explicit URL. This is especially handy for the planet file, which defaults to minutely change files. If you're catching up on a longer period, it makes sense to switch to the hourly (or daily) change stream:

```
gol update planet https://planet.openstreetmap.org/replication/hour
```

On a modern midrange workstation, applying a day's worth of planet-wide changes takes about 5 minutes. This is considerably faster than the current workflow of patching the source PBF and rebuilding the GOL, which takes over an hour. 

`gol update` also reduces the required disk space: Apart from the GOL itself (which in updatable form takes about 130 GB for the full planet), it only needs storage for the updated tiles, with no interim copies of the PBF data.

## Current limitations

- The GOL is locked for writing during updates; this limitation will be lifted with the storage engine upgrade in v3.0, which supports true multi-reader/single-writer concurrency.

- Updates for very long periods on large datasets may run out of memory (As a conservative rule of thumb, budget 750 MB of RAM per day's worth of worldwide changes). Upcoming releases will automatically divide large updates into multiple stages if memory is tight.

[Download](https://www.geodesk.com/download) / [GitHub](https://github.com/clarisma/geodesk-gol) / [Documentation](https://docs.geodesk.com/gol/update)

