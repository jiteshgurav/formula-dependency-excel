
# Excel Dependency Graph

## Installation

You can install the package from PyPI using the following command:

```bash
pip install excel-dependency-graph==0.1.0
```

## Overview

This Python script reads an Excel file and builds a dependency graph of cell formulas using the `networkx` library. Each cell that contains a formula referencing other cells is represented as a directed graph node, with edges representing the dependencies. The dependency graph can be visualized and analyzed to understand how different cells are interrelated.

## Features

- Parses formulas in Excel sheets to identify cell dependencies.
- Builds a directed dependency graph using `networkx`.
- Visualizes the dependency graph with `matplotlib`.
- Allows retrieval of dependencies and dependents of specific cells.
- Saves the dependency graph in GML format.

## Requirements

This script requires the following Python libraries:

- `openpyxl` for reading Excel files
- `networkx` for creating and handling the dependency graph
- `matplotlib` for graph visualization

Install these libraries using `pip`:

```bash
pip install openpyxl networkx matplotlib
```

## Usage

1. **Initialize the Graph**: Instantiate the `ExcelDependencyGraph` class with the path to the Excel file.
2. **Build the Dependency Graph**: Call the `build_dependency_graph()` method to parse the file and build the graph.
3. **Visualize the Graph**: Use `visualize_graph()` to display the dependency graph.
4. **Retrieve Dependencies and Dependents**:
   - `get_dependencies(cell)` returns cells a given cell depends on.
   - `get_dependents(cell)` returns cells that depend on a given cell.
5. **Save the Graph**: Save the graph structure in GML format using `save_graph(output_path)`.



# Example usage
```
graph = ExcelDependencyGraph("example/example.xlsx")
graph.build_dependency_graph()
graph.visualize_graph()
print(graph.get_dependencies("Sheet1!A1"))
print(graph.get_dependents("Sheet1!A1"))
graph.save_graph("dependency_graph.gml")
```

# Sample Output

![image](https://github.com/user-attachments/assets/149da8f0-2b75-480d-bb64-f23e25d7ccd0)

