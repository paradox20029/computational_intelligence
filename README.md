# ASSIGNMENT 1
# SIT_215_TASK1_4_annoted (2).ipynb

*A Wheelchair Navigation System using A*, Dijkstra, and a Colab-based GUI*

## Table of Contents
1. [Overview](#overview)
2. [Key Features](#key-features)
3. [Directory Structure](#directory-structure)
4. [Setup & Requirements](#setup--requirements)
5. [Usage Instructions](#usage-instructions)
   - [Running in Google Colab](#running-in-google-colab)
   - [Running Locally](#running-locally)
6. [Project Details](#project-details)
   - [Search Algorithms](#search-algorithms)
   - [Heuristic Functions](#heuristic-functions)
   - [GUI Interaction](#gui-interaction)
7. [Common Issues](#common-issues)
8. [Planned Enhancements](#planned-enhancements)
9. [License](#license)

---

## Overview

This Jupyter Notebook, **SIT_215_TASK1_4_annoted (2).ipynb**, is part of an assignment under SIT215. It demonstrates a *wheelchair-friendly* navigation system built upon a **graph-based environment**, using search algorithms like **A\*** (with Euclidean or Accessibility heuristics) and **Dijkstra**. A **Colab**-compatible GUI via *ipywidgets* is included to let users input start/end nodes, pick algorithms, toggle event conditions, and visualize the resulting path in-line.

---

## Key Features

- **Graph Model**:
  - Nodes as physical locations (entrances, restrooms, lifts, etc.).
  - Edges store distances and environmental constraints (steep slopes, closures, rough terrain).

- **A\* Search**:
  - *Euclidean Heuristic*: Straight-line distance from node to goal.
  - *Accessibility-Adjusted Heuristic*: Adds penalty values for steep slopes, rough terrain, or event-time closures.

- **Dijkstra Algorithm**:
  - Explores nodes by ascending accumulated cost.
  - Provides a comparison baseline without heuristic.

- **Colab GUI**:
  - Built with `ipywidgets`.
  - Allows text input for start/end, dropdown for algorithm, checkbox for event conditions, a “Compute Path” button, and in-notebook route visualization.

---

## Directory Structure


---

## Setup & Requirements

1. **Python 3.x**  
2. **Packages**:
   - `ipywidgets`
   - `networkx`
   - `matplotlib`
   - `numpy`
3. **(Optional) Jupyter**:
   - If running locally, ensure ipywidgets is enabled:
     ```
     jupyter nbextension enable --py widgetsnbextension
     ```

---

## Usage Instructions

### Running in Google Colab

1. Open [Google Colab](https://colab.research.google.com/) and **upload** `SIT_215_TASK1_4_annoted (2).ipynb`.
2. In the first cell, install necessary libraries if needed:
   ```python
   !pip install ipywidgets networkx matplotlib numpy
Run all cells up to the cell containing the GUI code (e.g., colab_gui_navigation(...)).

In a new cell, call:
colab_gui_navigation(
    wheelchair_map,
    wheelchair_graph_data,
    WheelchairProblem,
    a_star_search,
    dijkstra_search,
    show_path
)

## Running Locally

1. **Clone or Download** this repository.

2. **Install required packages**:
   ```bash
   pip install ipywidgets networkx matplotlib numpy
If using Jupyter Notebook/Lab, enable ipywidgets:

bash
Copy
Edit
jupyter nbextension enable --py widgetsnbextension
Launch the notebook:

bash
Copy
Edit
jupyter notebook
Open SIT_215_TASK1_4_annoted (2).ipynb, run cells in order, then call colab_gui_navigation(...) as described. The GUI will appear in the notebook output area.

Project Details
Search Algorithms
A*

Euclidean Heuristic: Straight-line distance only.

Accessibility Heuristic: Extra penalties for steep slopes, rough terrain, or event closures.

Dijkstra

Works purely by cumulative cost, no heuristic.

May return a list of Node objects if unmodified, or a final Node if updated to mirror A*.

Heuristic Functions
Euclidean:

plaintext
Copy
Edit
distance = sqrt((x1 - x2)^2 + (y1 - y2)^2)
Accessibility-Adjusted:

plaintext
Copy
Edit
distance + slope_penalty + terrain_penalty + event_penalty
GUI Interaction
ipywidgets text boxes for specifying start/end nodes, a dropdown for algorithm selection, and a checkbox for Event Conditions.

Clicking Compute Path runs the chosen search, printing path/cost/time in the output, and calls show_path(...) to visualize the route.

Common Issues
No path found: Possibly caused by blocked edges due to event closures, or incorrect node names that don’t exist in the graph.

"list object has no attribute .path()": If your Dijkstra code returns a list of Nodes, handle it in the GUI (or update Dijkstra to return a final Node object with a .path() method).

Plot not displayed: Make sure you’re using %matplotlib inline or %matplotlib notebook (if local) or just run the cell in Colab as normal.

pgsql
Copy
Edit

**Instructions**:
1. Insert this text into your README under the relevant sections.
2. Update any references (e.g., filenames, code references) to match your project’s structure.
3. Commit/push the updated README to GitHub, and the formatting should appear neatly.
