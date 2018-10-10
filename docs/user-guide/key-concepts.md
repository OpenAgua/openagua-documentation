# Key concepts

## Data organization

OpenAgua builds on the data organizing scheme defined by Hydra Platform, whereby:

* water system model components are grouped into networks, which are further grouped into projects, and
* data is grouped into scenarios.

  OpenAgua extends this functionality by adding _studies_, which consist of any arbitrary combination of network and scenarios. These are described below.

### Project & networks

In Hydra Platform, a _network_ is a user-created collection of nodes \(e.g., reservoirs and demand sites\) connected to each other by links \(e.g., rivers and conveyances\). A _project_ is a collection of one or more networks; a network may belong to only one project.

All the projects and networks are stored in the library called **Home**. In here, the user will be yable to create new networks and arrange them by the user's preferences. Networks can be shared, edited, exported, deleted and cleaned.

### Network templates

In OpenAgua, a "template" is a definition of the overall structure of a network. Specifically, a template defines the _kinds_ of resources \(nodes, links, and global resources\) and attributes \(i.e., constants and variables\) that a network may have. For example, a template would indicate that there is a node type called "reservoir" and link type called "river". The template would then further indicate that, for example, a reservoir has a "capacity" and an "inactive zone".

The user does not need to deal with templates to get started with OpenAgua. However, as a model becomes more sophisticated, or if the core modeling logic is changed, OpenAgua comes with a [template editor](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/user-guide/setting-up-model/README.md#define-the-model-template), which may then be applied to a new or existing network as [described here](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/user-guide/setting-up-model/README.md#createedit-networks).

Templates are matched with models: a template should describe \(at least\) the input and output expected by a core model. A network defined by a particular template may be used by one ore more models. A model might also use more than one template, but this might be more restrictive, as a model's input requirements are typically fixed; any variation on a template would need to consider this.

For each resource type \(node, link, network\), a template defines the name, icon to be used \(nodes\) or line style \(links\), as well as attributes. In the case of the "network" \(i.e., the network as a whole, not specific nodes and links\), "resources" may be added to represent arbitrary groupings of global attributes for the network.

For each attribute \(variable\), a template further defines:

* Data type \(_scalar_, _timeseries_, etc.\),
* Dimension \(_volume_, _flow rate_, etc.\),
* Units \(_cubic meters_, _cubic meters per second_, etc.\), and
* Scope \(whether or not the attribute is an input or output\).

### Scenarios

