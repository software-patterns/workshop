# Tools

This directory contains tools for analyzing the patterns.

## `tools/draw-link-graph graph.png`

Run this script to visualize the graph of references among pattern files. The
example above generates a file named `graph.png`.

Any links to nonexistent files will be colored red, so you can easily find
and fix broken links.

You must have [graphviz](https://graphviz.gitlab.io/) and Ruby installed for
this script to work.  If you use Homebrew, `brew install graphviz` and `brew
install ruby` should get you set up.
