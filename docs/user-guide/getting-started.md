# About this guide

This user guide includes four parts, yet includes many more sections.

First, it describes key concepts that underpin the data organization and modeling principles used by OpenAgua. 

Second, it describes how to use interface features unique to OpenAgua, such as creating new projects, networks, and studies.

Third, it includes documentation for specific functional areas within OpenAgua (e.g., Network Editor, Basic Data Editor, etc.), which are developed--and documented--in a modular fashion.

Finally, it includes a [glossary](docs.openagua.org/user-guide/glossary) of specific terms.

# Key Concepts

## Data organization

OpenAgua builds on the data organizing scheme defined by Hydra Platform, whereby:
- water system model components are grouped into networks, which are further grouped into projects, and
- data is grouped into scenarios.
OpenAgua extends this functionality by adding *studies*, which consist of any arbitrary combination of network and scenarios. These are described below.

## Project & networks

In Hydra Platform, a *network* is a user-created collection of nodes (e.g., reservoirs and demand sites) connected to each other by links (e.g., rivers and conveyances). A *project* is a collection of one or more networks; a network may belong to only one project.

All the projects and networks are stored in the library called **Home**. In here, the user will be yable to create new networks and arrange them by the user's preferences. Networks can be shared, edited, exported, deleted and cleaned.

## Scenarios