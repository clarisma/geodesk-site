---
id: query
layout: doc-gol
title: load
---

# `save`

Exports tiles to a folder.

Usage:

    gol save <gol-file> <destination> [<options>]

- If no area is defined (via [`--bbox`](#option-bbox) or [`--polygon`](#option-polygon)),
  all tiles are exported.

- Missing tiles will be imported from another repository, if one is specified via [`--url`](#option-url).

## Options

{% include gol/option-bbox.md %}
{% include gol/option-polygon.md %}
{% include gol/option-quiet.md %}
{% include gol/option-silent.md %}
{% include gol/option-url.md %}
{% include gol/option-verbose.md %}
{% include gol/option-wait.md %}