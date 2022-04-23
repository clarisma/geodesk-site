---
id: query
layout: doc-gol
title: load
---

# `load`

Imports tiles into a feature library from a repository.

Usage:

    gol load <gol-file> [<repository-path>] [<options>]

- You must provide either the `<repository-path>` argument or the [`--url`](#option-url) option. If you specify both, the command will first look for tiles in `<repository-path>`, then download any missing tiles from the given URL. 

- If no area is defined (via [`--bbox`](#option-bbox) or [`--polygon`](#option-polygon)),
  all tiles that aren't already present in this library are imported from the repository.

## Options

{% include gol/option-bbox.md %}
{% include gol/option-new.md %}
{% include gol/option-polygon.md %}
{% include gol/option-quiet.md %}
{% include gol/option-silent.md %}
{% include gol/option-url.md %}
{% include gol/option-verbose.md %}
{% include gol/option-wait.md %}

