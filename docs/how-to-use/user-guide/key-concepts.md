# Key concepts

There are several concepts that are important to understand when using OpenAgua. Specifically the user should be familiar with general _data organization_, the concept of _templates_, how _model engines_ work \(optional\), and OpenAgua's _data visualization_ capabilities.

## Data organization

OpenAgua builds on the data organizing scheme defined by [Hydra Platform](https://github.com/openagua/openagua-documentation/tree/88bbc167c05dd40a267cf0802dc9b30fedd4b5b2/docs/user-guide/www.hydraplatform.org) \(Hydra\). Data is broadly organized as follows, yet the actual data organization is much more complex \(refer to Hydra documentation\):

* Water system model components are grouped into _networks_, which are further grouped into _projects_.
* Data is grouped into _scenarios_

OpenAgua builds on this and other Hydra data organization concepts with a wide range of other data and metadata that either are directly tied to Hydra data structures \(e.g., a river's shape\) or are stored independently \(e.g., results charts and tables\).

### Project & networks

In Hydra Platform, a _network_ is a user-created collection of nodes \(e.g., reservoirs and demand sites\) connected to each other by links \(e.g., rivers and conveyances\). A _project_ is a collection of one or more networks; a network may belong to only one project.

All the projects and networks are stored in the library called **Home**. In here, the user will be able to create new networks and arrange them by the user's preferences. Networks can be shared, edited, exported, deleted and cleaned.

### Scenarios

Under construction.

## Templates

In OpenAgua, a "template" is a definition of the overall structure of a network. Specifically, a template defines the kinds \(_types_\) of resources \(nodes, links, and global resources\) and attributes \(i.e., constants and variables\) that a network may have. For example, a template would indicate that there is a node type called "reservoir" and link type called "river". The template would then further indicate that, for example, a reservoir has a "capacity" and an "inactive zone". Thus, although OpenAgua is inspired by solving water system problems, templates can be created for any network type.

The user does not need to deal with templates to get started with OpenAgua. However, modelers will often find the need to modify the template associated with their networks. For this reason, OpenAgua includes the ability to edit templates. Two template viewers/editors exist for this purpose:

1. **General templates** - Templates that are not used by a specific network are included listed as "general templates". Templates in this area are editable only by their owner. If the owner makes a template public, this template may be viewed and copied by others for use in their own projects.
2. **Project templates** - Templates that are in use by specific networks are listed in the project viewer, where they may be edited by anybody who can edit the project.

## Model engines \(optional\)

Under construction.

## Data visualization

Under construction.

