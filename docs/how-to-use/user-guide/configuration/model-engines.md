# Model engines

To successfully run a model using OpenAgua, there must be a working connection between OpenAgua and a _model engine_. A _model engine_ is a generalized executable modeling application that is designed to 1\) connect with and read data from the OpenAgua database, 2\) perform some action using the data \(most likely a simulation or optimization of the system\), and 3\) save results back to OpenAgua.

There is no hard constraint on what action is performed within the model engine, so this setup actually affords a significant amount of flexibility in terms of customization of the model, from the trivial \(e.g., do nothing\) to the complex \(e.g., simulate a coupled human-water system using multiple sub-models in various physical and management domains\).

## Conceptual overview

When [running a model](https://github.com/openagua/openagua-documentation/tree/e5fde739d6daf4b5cb8dc0d39118d38f234eab0d/docs/user-guide/configuration/user-guide/running-models.md), a user initiates a set of actions that results in the model engine starting. The model engine may be located on one or more computers connected to the internet. Generally, there are three modes that OpenAgua can use to communicate with a model engine.

1. **Directly** on the host computer. In this case, the model engine is located on the same computer as the OpenAgua server. OpenAgua sends the command to run the model engine directly \(using Python's [Popen](https://docs.python.org/2/library/subprocess.html#popen-constructor) constructor\). 
2. **Directly via** [**SSH**](https://en.wikipedia.org/wiki/Secure_Shell) on a remote computer: In this case, the model engine is located on a computer different than the main OpenAgua server. OpenAgua sends the command to run the model using SSH \(secure shell\). SSH is a way of logging directly into a computer remotely to execute commands on that computer.
3. **Indirectly via a task \[scheduler\]\(**[https://en.wikipedia.org/wiki/Scheduling\_\(computing](https://en.wikipedia.org/wiki/Scheduling_%28computing)**\)\)**: In this case, the model engine may be on one or more computers, and may include the OpenAgua server itself. Running the model involves two steps behind-the-scenes. First, OpenAgua sends the command to a _scheduler_ \(specifically, a [RabbitMQ](https://www.rabbitmq.com/) task queue\). Second, one of the model engines, which are setup as _workers_ to continually wait for new tasks, takes the task out of the queue and performs the model computations.

The indirect, queue-based setup offers the greatest flexibility, as any computer connected to the internet, including a personal laptop, can provide the computing power necessary to run a model. Nonetheless, OpenAgua includes all three modes to offer the greatest flexibility as needed.

The practical implications of these are that model engine setup requires configuration in two places: in OpenAgua and in the model engine itself. Both of these are described here.

## Configuration of OpenAgua for model engine use

**NOTE**: For the time being, only administrative users can set up and configure models within OpenAgua for different computing modes, but this will change in the future as OpenAgua is improved. However, non-administrative users can still set up model engines to perform the modeling computations, as explained below.

\(To be completed.\)

## Configuration of the model engine itself

\(To be completed.\)

