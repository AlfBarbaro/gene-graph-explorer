# Gene Graph Explorer

Interactive browser-based tool for visualizing and querying gene dependency graphs extracted from Perturb-seq data.

## Quick Start

1. Visit the [live site](https://achieve-lab.github.io/gene-graph-explorer/) (or open `index.html` locally)
2. Click the upload area (top left) and load a CSV from `sample_graphs/`
3. The app automatically selects the top hub gene — start exploring

## Sample Graphs

| File | Description |
|------|-------------|
| `sample_graphs/adata_10000genes.csv` | Graph built from the full adata dataset using XGBoost (top 10k HVGs) |

Each CSV is an edge list (`source, target, weight`). Each row is a directed edge: the source gene's expression was a strong predictor of the target gene's expression under perturbation, as measured by normalized XGBoost feature gain.

## Views

- **Ego Graph** — select a gene to see its upstream regulators (left) and downstream targets (right). Best for exploring one gene at a time.
- **Hub Radial** — top 12 hubs arranged in a circle with their strongest targets. Good overview of the hub-and-spoke structure.
- **Full Graph** — force-directed layout of the entire network. Use the min-weight slider to filter weak edges and reduce clutter.

## Navigation

- **Scroll** to zoom (toward cursor), **drag** to pan, **click** a node to select, **double-click** to reset view
- Touch: pinch to zoom, one-finger drag to pan

## Sidebar Controls

- **Search** — type a gene name (partial match supported)
- **Hub threshold** — minimum outgoing weight for a gene to be classified as a hub (default: 90th percentile, adjustable)
- **Top Hubs / Spokes / Edges** — query buttons with customizable result count
- **Statistics** — graph summary (nodes, edges, density, weight distributions)
- **Theme toggle** (top right) — switch between light and dark mode

## How to Read the Graph

- **Hub** (orange) = gene whose expression is informative for predicting many others — likely an important regulator
- **Spoke** (gray) = gene that appears mostly as a target
- **Edge weight** = strength of the predictive relationship (higher = stronger)
- **outW** = total outgoing weight of a gene (sum of all its outgoing edge weights)
- **inW** = total incoming weight (sum of all incoming edge weights)

The hub/spoke classification depends on the hub threshold — lower it to see more hubs, raise it for a more selective classification.