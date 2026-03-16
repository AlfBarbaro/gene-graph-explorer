# Gene Graph Explorer

Interactive browser-based tool for visualizing and querying gene dependency graphs extracted from Perturb-seq data via XGBoost.

## Usage

1. Open `index.html` in a browser (or visit the [live site](https://YOUR_USERNAME.github.io/gene-graph-explorer/))
2. Load a graph CSV (edge list with `source, target, weight` columns)
3. Explore using three views:
   - **Ego Graph** — focused neighborhood of a selected gene
   - **Hub Radial** — top hub genes arranged radially with their targets
   - **Full Graph** — complete network with weight filtering
4. Use the sidebar to search genes, query top hubs/spokes/edges, and view statistics

A sample CSV (`adata_full_edges.csv`) is included in this repo.