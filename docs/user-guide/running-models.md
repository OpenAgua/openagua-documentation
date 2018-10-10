# Running Models

## Model Dashboard

The **Model Dashboard** enables you to run models for one or more scenarios. Once the model is run, progress will be reported in one or more progress bars. Additionally, more detailed information about both, the model run as a whole and about each specific scenario run is shown. The main log information is always shown providing feedback including the parameters used in the current model run \(e.g. time span, level foresight, scenario ids, solver etc.\) and the general status of the model run.

The Scenario log is shown by clicking the view log button next to the progress bar. It provides text updates about the model run. Additionally, it provides limited information from Pyomo about the optimization problem \(e.g. number of objectives, constraints, variables etc.\) Importantly this information also includes the status of the problem after the model run including specifically the termination condition. Termination conditions could include optimal, infeasible and many others \(see [http://www.pyomo.org/blog/2015/1/8/accessing-solver](http://www.pyomo.org/blog/2015/1/8/accessing-solver)\).

During the run, the modeling can be stopped by clicking Stop model.

