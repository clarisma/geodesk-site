---
id: query
layout: doc-gol
title: load
---

# `info`

Provides general statistics about a library. If a bounding box or polygon are specified,
this command provides additional statistics about that area.

Usage:

    gol info <gol-file> [<options>]  

## Options

{% include gol/option-bbox.md %}

<a name="option-index">
### `-i`, `--index`

Provides additional information about the library's indexes.

{% include gol/option-new.md %}
{% include gol/option-output.md %}
{% include gol/option-polygon.md %}
{% include gol/option-quiet.md %}
{% include gol/option-silent.md %}
{% include gol/option-url.md %}
{% include gol/option-verbose.md %}
{% include gol/option-wait.md %}
