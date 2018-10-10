# index

## Overview

OpenAgua is a web-based application for modeling water systems for water resources planning and management. It aims to help develop insights to complex water issues in a collaborative computing environment. See a [5-minute demo](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/demos/README.md#tutorial1)\[TO-DO\] for a brief overview. OpenAgua is built by [a dedicated team](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/the-team/README.md) of developers, water experts, and visionary funders, and is based on the Hydra Shared Software Platform, an open source suite of tools for building network models.

## Key Innovations

The key innovations of OpenAgua over existing water system modeling platforms stem from its use of web technologies, which existing similar platforms lack. Web technologies enable:

* Cloud-based high-speed computing
* Collaboration/sharing in modeling and scenario analysis
* Easy continual improvement through the open source development model and widely-used [core technologies](index.md#core-technologies).
* Interoperability between other web apps.

Additionally, OpenAgua explicitly uses economic optimization by default, while also allowing a traditional similation approach.

## Availability

OpenAgua may be either used online at [www.openagua.org](https://www.openagua.org), or downloaded \(for free\) [from GitHub](https://github.com/OpenAgua/OpenAgua) for use on a desktop or local server. OpenAgua.org enables ready-to-go modeling, with no setup required, whereas the downloadable version is mostly free and customizable \(some advanced features require a license; these are disabled by default\). In all cases, we offer paid support for both modeling and custom installation.

## Main Features

**Water system modelling**

OpenAgua uses the standard water system modeling techniques to help understand complex, real-world water management challenges. Three generic approaches to modeling are supported. First, a hydroeconomic modeling approach with perfect foresight \(of hydrologic conditions, water demands, etc.\) can be used to maximize the total benefit derived from system operations. Second, the first approach can be modified by using imperfect foresight instead of perfect foresight. Finally, a traditional rule-based simulation approach can be used, whereby no foresight is assumed. \(**Note**: Currently, only the first approach is implemented, though the latter two are planned.\). Furthermore, in the future users will be able to use their own custom model, but still use OpenAgua to interact with their data and run their model.

Read more about the default [water allocation logic](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/user-guide/water-allocation-logic/README.md), and see the [list of publications](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/publications/README.md).

**Advanced scenario builder**

In order to adequately asses several decision frameworks, aside from the baseline scenario, OpenAgua has the feature of constructing scenarios. The user will be able to incorporate a mix of potential uncertainties and make projections in a specified time frame. By implementing scenarios, the user’s project will developed a more robust and deep analysis. Evaluation, identification and establishment of the best strategies into potential plans will ensure the user to select the best future projection for water planning.

Learn more in the [scenario builder demo](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/demos/README.md#scenarios), the [user guide](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/user-guide/creating-scenarios/README.md), or in the [scenario builder tutorial](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/tutorials/creating-scenarios/README.md).

**Standardized data organization**

All data of OpenAgua is organized using [Hydra Platform](http://hydraplatform.org), a data representation layer and web server for the remote management of networks and data. By using this server, OpenAgua can store and process data on a web based service, it is important to mention that OpenAgua and Hydra are both implemented in Python.

**Advanced analytical tools**

OpenAgua is packed with a suite of modern visualization tools, including graphs, charts and maps, some of which are interactive. By default, OpenAgua uses Plotly for creating charts \(see some [Plotly examples](https://plot.ly/javascript/#basic-charts)\). Since no single platform can meet all user needs, users can also either download data for offline analysis or connect directly to their data from other data analysis platforms, such as R or Jupyter Notebook.

**Collaborative modeling and scenario analysis**

Real-time interaction, remote collaborations and web interface communication methods are gradually becoming more common. OpenAgua’s platform is designed to target these communication approach. With OpenAgua, multiple users can share and work in one or more networks. These feature provide a flexible and transparent tool for water managers, stakeholders, citizens, researchers etc. Moreover, different levels of access can be assigned to the networks, this ensures developers to allow collaborators certain privileges such as edit or just read. With this feature, users will get involved and be potential contributors to other existing projects. Furthermore, they will be able to find popular and trending or starred projects.

**Flexible computing**

Flexible computing is another essential part of OpenAgua. Based on Internet-connected servers, OpenAgua may be downloaded/installed locally or used directly online at [OpenAgua web page](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/docs/www.openagua.org) to leverage the power of cloud computing. This enables dynamism, scalability and plasticity to users’ projects.

**Security**

Standard website data security best practices ensure that your data is protected. OpenAgua has employed a tiered ownership system. The user is able to have restrictions and control who has access to your networks and projects as well as the level of permission they have

**Open Source**

The OpenAgua software is open source and mostly free \(some optional functions require a license\). Open Source software lie on the practice of granting wide range of rights to users. OpenAgua is determined to engage innovation and development throughout the contributions of water management social figures. Benefits on letting actors of knowledge and learning, to compute processes and products, are sources of innovation on the water field.

The fact that users’ needs and approaches to target problems are in constant change, open source softwares enables the opportunity to evolve by the constant developing of prototype code innovations. For instance, the user’s community of OpenAgua can freely make improvements and innovate codes on the platform or in their networks. The source code of OpenAgua is written in Python and it can be checked out on GitHub.

While the main functionality of OpenAgua is free, some additional useful features require a license to use. These features are disabled by default, but can be enabled, and are available in the paid version of OpenAgua.org.

## Core Technologies

Core technologies used to configure OpenAgua are a mix of open source libraries. This will enable the platform to be in constant improvement and evolution. We thank the thousands of developers out there for all of these!

**Data Management**

To start and as mention above, data management in OpenAgua is built on [Hydra Platform](http://hydraplatform.org) a network-based data management platform.

**Web stack \(front-end and back-end\)**

Like any interactive, data-driven web-based application, OpenAgua uses a mix of front-end \(client\) and back-end \(server\) technologies, with data processing occuring both client-side and server-side. The front-end user interface is developed with [Bootstrap](http://getbootstrap.com), one of the most widely-used front-end web application frameworks, combined with custom HTML, CSS, and JavaScript. Many JavaScript libraries are used for website interactivity, including [jQuery](https://jquery.com/), [Lodash](https://lodash.com/), and others.

The back-end is built with [Flask](http://flask.pocoo.org), a "microframework for Python based on Werkzeug, Jinja 2 and good intentions". This means that server-side website actions are written in Python, enabling easy development. Server-side work includes serving individual webpages and interactions with Hydra Platform, among other various functions. Numerous Python packages are used for server-side data processing.

**Modeling**

The default hydroeconomic model used by OpenAgua is written using [Pyomo](http://www.pyomo.org), a Python package used to formulate and solve optimization models. [GLPK](https://www.gnu.org/software/glpk/) is the linear programming solver used by the default hydroeconomic model.

