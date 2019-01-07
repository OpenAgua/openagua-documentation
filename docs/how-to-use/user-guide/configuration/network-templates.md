# Network templates

For each resource type \(node, link, network\), a template defines the name, icon to be used \(nodes\) or line style \(links\), as well as attributes. In the case of the "network" \(i.e., the network as a whole, not specific nodes and links\), "resources" may be added to represent arbitrary groupings of global attributes for the network.

Templates are matched with models: a template should describe \(at least\) the input and output expected by a core model. A network defined by a particular template may be used by one ore more models. A model might also use more than one template, but this might be more restrictive, as a model's input requirements are typically fixed; any variation on a template would need to consider this.

## Types

Under construction.

## Attributes

Under construction.

For each attribute \(variable\), a template further defines the following:

* Data type \(_scalar_, _timeseries_, etc.\)
* Dimension \(_volume_, _flow rate_, etc.\)
* Units \(_cubic meters_, _cubic meters per second_, etc.\)
* Scope \(whether or not the attribute is an input or output\)

