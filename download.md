---
title:  Getting Started
layout: page
---

<div class="text-container" markdown="1">

<div class="box todo" markdown="1">
Our Early Access Release is coming soon...

*(The links below aren't active yet)*
</div>


### Download the GOL Tool

[Download as zipfile](https://github.com/clarisma/gol-tool/releases/download/{{ site.geodesk_version }}/gol-tool-{{ site.geodesk_version }}.zip) and uncompress in a folder of your choice. You must have **Java Runtime Version 16** or above (64-bit) installed on your system ([Download latest version of OpenJDK](https://jdk.java.net/)).

This distribution contains both `gol.bat` (for Windows) and `gol` shell script (for Linux and Mac). Please ensure that the `JAVA_HOME` environment property is set correctly.

> **Linux users:** You may have to make the launcher script executable using `chmod u+x gol`. To conveniently use the command from any folder, consider creating a symbolic link on your path, e.g. `ln -s gol_app_dir/gol ~/bin/gol`.

For usage, see [GOL User Guide](http://docs.geodesk.com/gol) or run `gol help`.

### Create your first geographic object library

Grab some OpenStreetMap data in OSM-PBF format from a provider such as [Geofabrik](http://download.geofabrik.de/) (We recommend starting with a country-sized extract, or maybe just a single state).

Run the `build` command:

```
gol build france france-latest.osm.pbf
```

(Depending on your hardware and the size of the extract, this could take a few minutes to half an hour to complete.)

Alternatively, download our pre-built example dataset (Switzerland -- 400 MB):

```
gol load -n swiss https://data.geodesk.com/switzerland
```

Now you can familiarize yourself with some of GeoDesk's capabilities by running [the <code>gol query</code> command](http://docs.geodesk.com/gol/query).

### Download the GeoDesk Java Library

You will need the [GeoDesk Java library](http://www.github.com/clarisma/geodesk) if you want to incorporate the GeoDesk database engine into your own geospatial applications. You can skip this step if you only want to use the GOL command-line tool. 

If you're using Maven, add this dependency to your project:

{% include maven.md %}

Alternatively, build the latest version from source:

```
git clone https://github.com/clarisma/geodesk.git
cd geodesk
mvn install
```

GeoDesk requires JRE 16 or above (64-bit), and the following third-party libraries (Maven should automatically install these for you):

- [Eclipse Collections](https://github.com/eclipse/eclipse-collections) Version 9.0 or above

- [Java Topology Suite (JTS)](https://github.com/locationtech/jts) Version 1.18 or above

- [ObjectWeb ASM](https://asm.ow2.io/) 9.0 or above 

## Need help?

Problems, questions or feedback? Visit the GeoDesk [GitHub repository](http://www.github.com/clarisma/geodesk).

</div>