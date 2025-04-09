# ASSIGNMENT 1
README for SIT_215_TASK1_4_annoted (2).ipynb


SIT_215_TASK1_4_annoted (2).ipynb
A Wheelchair Navigation System using A, Dijkstra, and a Colab-based GUI*

Overview
This Jupyter Notebook provides an annotated solution for a wheelchair navigation system, developed for the SIT215 assignment. It demonstrates:

A* with both Euclidean and Accessibility‐Adjusted heuristics.

Dijkstra’s algorithm as a baseline pathfinding approach.

A graph‐based environment, modeling physical locations (nodes) and distances/constraints (edges).

A Colab / Jupyter user interface using ipywidgets to input start/end nodes, select algorithms, and visualize routes with Matplotlib.

Key Features
Graph Model:

Nodes represent locations (e.g., entrances, restrooms, lifts).

Edges store travel distances and constraints (steep slopes, blocked paths, event closures).

Search Algorithms:

A* Search: Optionally toggles between Euclidean or Accessibility heuristics.

Dijkstra's Algorithm: Demonstrates a pure cost-based approach with no heuristic.

Heuristic Enhancements:

Accessibility‐Adjusted: Adds penalty values for problematic areas, encouraging wheelchair-friendly routes.

GUI in Colab:

Provided by ipywidgets – user inputs start/end, toggles event conditions, picks an algorithm, and sees results inline.

Requirements
Python 3.x

Jupyter Notebook or Google Colab

Packages:


pip install ipywidgets
pip install networkx
pip install matplotlib
pip install numpy
ipywidgets Enabled (if running locally):


jupyter nbextension enable --py widgetsnbextension
How to Use
1. Google Colab
Open Google Colab and upload the notebook SIT_215_TASK1_4_annoted (2).ipynb.

In the first cell (if needed), install libraries:


!pip install ipywidgets networkx matplotlib numpy
Run all cells to define the graph (wheelchair_map), the problem class (WheelchairProblem), search algorithms (a_star_search, dijkstra_search), and the GUI function (colab_gui_navigation).

Display GUI:


colab_gui_navigation(
    wheelchair_map,
    wheelchair_graph_data,   # for visualization
    WheelchairProblem,
    a_star_search,
    dijkstra_search,
    show_path                # function to display route
)
Enter start/end nodes, select algorithm (A* or Dijkstra), toggle event conditions, then Compute Path. Path details and a Matplotlib figure will appear inline.

2. Local Jupyter
Clone or download the repo containing this notebook.

Install required packages (see above).

Enable ipywidgets if necessary:


jupyter nbextension enable --py widgetsnbextension
Launch notebook:


jupyter notebook
Open SIT_215_TASK1_4_annoted (2).ipynb, run cells, and call colab_gui_navigation(...) in the final cell. The widget interface will appear in the notebook output.

Project Structure
python
Copy
Edit
myproject/
├── SIT_215_TASK1_4_annoted (2).ipynb   # Main annotated notebook
├── README.md                           # This README
└── other files (if any)...
Within the notebook:

Graph Setup: Defines wheelchair_map, wheelchair_graph_data.

Search Algos: a_star_search, dijkstra_search (with updated code returning or handling Node objects).

Heuristic: Euclidean or Accessibility (penalties for slopes, terrain, closures).

GUI: ipywidgets code to create text boxes, dropdown, and a button that runs the algorithm and displays results.

Visualization: show_path function draws routes via Matplotlib.

Common Issues
No Path Found: Ensure the nodes you typed exist in the graph and event closures aren’t blocking all routes.

'list' object has no attribute 'path()': Ensure your Dijkstra code is updated or the GUI handles the difference in return types.

Plot Not Showing: Verify %matplotlib inline or %matplotlib notebook is set, or in Colab just run the cell.
