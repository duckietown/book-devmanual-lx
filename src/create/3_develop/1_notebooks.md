# Notebook Activities

## Educational purpose

```{admonition} Notebooks vs packages:
As a general rule, example code and visualizations should be developed by students 
directly in 
the notebooks.  Code for 
agents and other packages should be placed in the `packages/solutions` directory for students to edit in the 
respective Python files, then imported into the notebooks and unit tests for visualization and testing of their results.
```

```{admonition} A note on solutions:
Notebooks should generally walk through the knowledge required to implement some behavior on 
the Duckiebots, 
providing solutions to every notebook activity along way until the culminating activity in the final notebook. Students 
should then be editing 
package files to implement their work as directed by the notebook instructions, and the solution should be hidden in 
the separate solutions repository to enable evaluation.
```

## Edit zones

The following table contains a list of the files and directories that you may need to update to implement this type 
of LX activity. If you would like a full walkthrough showing how to implement notebooks, skip to the next section.

```{list-table} Edit zones
:header-rows: 1
:name: notebook-table

* - Feature
  - File Location
  - Purpose
* - Jupyter Notebook
  - `lx/notebooks`
  - Notebook files contain the knowledge portion of an LX, walking students through activities, visualizations, and 
  development.
* - Agent Code
  - `lx/packages`
  - Python files for agent implementations should remain in the `packages` directory, with students filling in TODOs 
  as instructed by the notebooks.
```

## Tutorial

```{todo}
Empty section here
```