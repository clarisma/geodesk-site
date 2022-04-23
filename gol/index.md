---
layout: doc-gol
---

# The `gol` Command Line Utility

The `gol` ("Geo-Object Librarian") command-line utility allows you to build, manage and
query [feature libraries](/libraries).

Usage:

    gol <command> <gol-file> [<arguments>] [<options>]

<img class="figure" src="/gol-diagram2.png" width=400>

## Commands

<table>
<tr>
<td markdown="1">
[`build`](build)
</td>
<td markdown="1">
Creates a feature library from OpenStreetMap data.
</td>
</tr>

<tr>
<td markdown="1">
[`check`](check)
</td>
<td markdown="1">
Verifies the library's integrity.
</td>
</tr>

<tr>
<td markdown="1">
[`copy`](copy)
</td>
<td markdown="1">
Copies tiles between libraries.
</td>
</tr>

<tr>
<td markdown="1">
[`help`](help)
</td>
<td markdown="1">
Displays documentation.
</td>
</tr>

<tr>
<td markdown="1">
[`info`](info)
</td>
<td markdown="1">
Provides basic file statistics.
</td>
</tr>

<tr>
<td markdown="1">
[`load`](load)
</td>
<td markdown="1">
Imports tiles for a specific area.
</td>
</tr>

<tr>
<td markdown="1">
[`query`](query)
</td>
<td markdown="1">
Extracts features.
</td>
</tr>

<tr>
<td markdown="1">
[`remove`](remove)
</td>
<td markdown="1">
Removes tiles in a specific area.
</td>
</tr>

<tr>
<td markdown="1">
[`retain`](retain)
</td>
<td markdown="1">
Removes tiles *outside* a specific area.
</td>
</tr>

<tr>
<td markdown="1">
[`save`](save)
</td>
<td markdown="1">
Exports tiles.
</td>
</tr>

<tr>
<td markdown="1">
[`vacuum`](vacuum)
</td>
<td markdown="1">
Compacts the library.
</td>
</tr>

</table>

<div class="box todo" markdown="1">
GeoDesk is **Pre-Release**. Some commands and options are not yet available in Version {{ site.geodesk_version }}.    
</div>


## Common Options

{% include gol/option-bbox.md %}
{% include gol/option-new.md %}
{% include gol/option-output.md %}
{% include gol/option-polygon.md %}
{% include gol/option-quiet.md %}
{% include gol/option-url.md %}
{% include gol/option-silent.md %}
{% include gol/option-verbose.md %}
{% include gol/option-wait.md %}
