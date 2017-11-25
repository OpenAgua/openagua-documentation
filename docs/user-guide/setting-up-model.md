# Setting up a new model

This describes how to create and set up up a model. This assumes you have read [Key Concepts](/user-guide/key-concepts) and that you have successfully created an account and logged on.

## Create/edit projects

### Create a project
To create a project, which will contain one or more network, click ‘Add Project’ from the HOME area.

### Edit a project

### Delete a project

## Define the model template

### Overview

For an overview of templates, please see [Getting Started](/user-guide/getting-started/#network-templates).

The template facility enables you to view "official" (built-in) templates and create/modify additional templates. Official templates may be "forked" to create a copy which may then be edited.

### Getting there

To get to the template viewer/editor, go to _Wrench_ -> _Templates_.

### Usage

#### Fork an official template

To fork an official template:

1. Right click the template and click "fork". The template will be copied to "My templates", where you may edit the forked template.

#### Edit a template

To edit in "My templates":
[documentation forthcoming]

#### Caveats

1. The template editor is not totally smooth. For example, sometimes tabs don't render right away, such that you have to click on another then come back to the desired tab; this is a problem with the underlying framework, which will be fixed some day.
2. The editor is not totally functional. For example, you cannot currently change the icons, or apply units universally (e.g., specify that all flow rates are in m3/s). These core and other features will be added.
3. Changing units does not yet change units in the core model. So changing units has no effect on the units that you should provide to the model.

## Create/edit networks

### Create network

Once logged-in, click "add network" in order to start building your project. A window will pop up so you can name and describe your project. Each network can have different versions where you will be able to switch within without loosing any data, we recommend selecting the latest version and looking at the "version history" link before modifying the template. This feature will function in later versions of OpenAgua.

### Edit network properties

### Edit network contents

Once your network is created, you can start creating and editing specific features (rivers, dams, etc.) by clicking 'OPEN', which appears over the network's thumbnail.
