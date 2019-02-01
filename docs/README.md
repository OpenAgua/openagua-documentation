# What is OpenAgua?

OpenAgua is a web-based application for modeling water systems for water resources planning and management. It aims to help develop insights to complex water issues in a collaborative online space. To achieve this, it offers a powerful set of basic tools for most use cases, as well as an increasing number of advanced tools for more complex modeling and computing cases. While OpenAgua is oriented toward water systems, it can also be easily adapted for other kinds of systems, such as energy systems.

OpenAgua is built by [a dedicated team](learn-more/the-team.md) of developers, water experts, and funders.

{% hint style="info" %}
This documentation is under development. Please contact the developers for specific help, or to highlight areas for priority documentation.
{% endhint %}

## Key Innovations

OpenAgua includes a range of key innovations over existing desktop-based software applications:

* **Integrated collaboration and sharing** - The modern web facilitates technical collaboration and sharing for transparency and data discovery, central motivations of OpenAgua; collaboration and sharing features are deeply integrated into OpenAgua, though much additional work remains. [Read more](how-to-use/user-guide/collaboration.md).
* **Cloud-based computing** - Although desktop computers are continually increasing speed, on-demand access to even more powerful and numerous cloud computers significantly increases our ability to discover water management solutions in an increasingly deeply uncertain world. OpenAgua allows users to use any internet-connected computer to take on tough computing tasks, from commercial cloud computers to personal laptops. [Read more](how-to-use/user-guide/configuration/model-engines.md).
* **Open source \(mostly\)** - As much of OpenAgua as is possible and reasonable is open source. In particular, the default water allocation model is completely open source \([see it here](https://github.com/openagua/waterlp)\). The core OpenAgua API is not yet open source, but will be. [Read more](learn-more/contributing/open-source.md).

## Availability

For now, OpenAgua is only available online at [www.openagua.org](https://www.openagua.org), though we are working to create a self-hosting option.

## Main Features

### Water system modelling

Water system modeling needs is built into the DNA of OpenAgua, even though OpenAgua is also flexible enough to accommodate any arbitrary model. OpenAgua by default includes a demand-driven, priority-based simulation model, similar in concept to WEAP. [Read more](https://openagua.github.io/waterlp).

### **Standardized data organization**

All data of OpenAgua is organized using the [Hydra Platform](http://www.hydraplatform.org) software, which ensures consistent and quality-controlled data organization. The use of Hydra Platform also ensures cross-compatibility between OpenAgua and other Hydra-compliant software systems, such as the Hydra-native web application [https://hydra.org.uk](https://hydra.org.uk)

### **Advanced scenario builder**

In order to adequately asses several decision frameworks, aside from the baseline scenario, OpenAgua has the feature of constructing scenarios. The user will be able to incorporate a mix of potential uncertainties and make projections in a specified time frame. By implementing scenarios, the user’s project will developed a more robust and deep analysis. Evaluation, identification and establishment of the best strategies into potential plans will ensure the user to select the best future projection for water planning.

Learn more in the [user guide](how-to-use/user-guide/setup-model/view-edit-scenarios.md).

### **Collaborative modeling and scenario analysis**

OpenAgua is designed from the ground up for collaboration and sharing. Practical examples of collaboration include:

* Technical collaboration between modelers.
* A modeling consultant can share a model with a client, with either view-only access, or full edit access.
* Sharing a model with the public for transparency in decision-making.

Despite these options, OpenAgua requires neither collaboration nor transparency; access to data is controlled, and private data is secure.

### **Flexible computing**

Flexible computing is another core feature of OpenAgua. As noted above, OpenAgua ships with a default model that can be run without any configuration on the part of the user. However, models can also be configured to use a range of different computing modes, with the only requirement being that the computer is connected to the internet. Read more about [model engine configuration](how-to-use/user-guide/configuration/model-engines.md).

### **Advanced analytical tools**

OpenAgua integrates modern visualization tools, based on the popular [Plotly library](https://plot.ly/javascript/). Since no single platform can meet all user needs, users can also either download data for offline analysis or connect directly to their data from other data analysis platforms, such as R or Jupyter Notebook.

### **Security**

Standard website data security best practices ensure that your data is protected and sharing is controlled. OpenAgua has employed a tiered ownership system. The user controls who has access to their projects, networks and other resources, as well as the level of permission they have. Inheriting the Hydra Platform permissions model, sharing chains are limited: trust levels for further sharing extend only one level beyond the project or network owner: If John allows Jane to share a project, Jane cannot allow others to further share the project.

### **Open source \(mostly\)**

OpenAgua fully appreciates the open source paradigm, while also recognizing the need to protect and control some source code. All of the technologies employed directly by OpenAgua are open source, and the default water system planning model is 100% open source. Currently, the OpenAgua API is not open source, but will be in the future. The website user interface code will likely not be open source for the foreseeable future. The driving principle here is that back-end \*processes\* are open source, while front-end \(what you see and interact with in the browser\) are not currently. The OpenAgua team is exploring the development of an \[open core\]\([https://en.wikipedia.org/wiki/Open-core\_model](https://en.wikipedia.org/wiki/Open-core_model)\) approach to development, whereby a core, basic version of OpenAgua is 100% open source, keeping some advanced features non-open source.

This hybrid \(and evolving!\) open source model recognizes that at the very least the core generalized modeling logic should be open to all, and free for all to modify and improve, but that some of the value-added tools developed by the OpenAgua team represent unique intellectual property that should be protected. However, this only represents the current state of practice, and not necessarily the long-term outcome.  We would very much welcome your opinion about this.

