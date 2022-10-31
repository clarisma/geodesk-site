---
title:  Download
layout: page
---

<div class="text-container" markdown="1">

<div class="box todo" markdown="1">
The Preview Release is coming soon...

*(The links below aren't active yet)*
</div>


## Download the GOL Tool

[Download as zipfile](todo) and uncompress in a folder of your choice. You
must have **Java Runtime Version 16** or above (64-bit) installed on your system.

This distribution contains both `gol.bat` (for Windows) and `gol` shell script (for Linux & Mac).
Please ensure the `JAVA_HOME` environment property is set correctly.

For usage, see [GOL User Guide](http://docs.geodesk.com/gol) or run `gol help`.

## Download the GeoDesk Java Library

If you're using Maven, add this dependency to your project:

{% include maven.md %}

Alternatively, build from source:

```
git clone https://github.com/clarisma/geodesk.git
cd geodesk
mvn install
```

GeoDesk requires JRE 16 or above (64-bit), and the following third-party libraries (Maven should automatically install these for you):

- [Eclipse Collections](https://github.com/eclipse/eclipse-collections) Version 9.0 or above

- [Java Topology Suite (JTS)](https://github.com/locationtech/jts) Version 1.18 or above

- [ObjectWeb ASM](https://asm.ow2.io/) 9.0 or above 


</div>