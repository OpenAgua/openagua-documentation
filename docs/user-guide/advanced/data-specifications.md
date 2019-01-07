# Data specifications

Data in OpenAgua builds on the data schema of Hydra Platform. Understanding these OpenAgua-specific data specifications is helpful if uploading data via Hydra API.

Hydra enables extensions through the `layout` field of many data objects (or, in the case of template types, the `properties` field). OpenAgua thus uses the `layout` field (and `properties` field) extensively.

## Scenarios

OpenAgua uses the following fields within the `scenario.layout` field:

* `class`: Options include `baseline`, `option`, `portfolio`, `scenario` and `results`.
  * The `baseline` scenario represents the main scenario from which all other scenarios are derived.
  * Scenarios with the `option`, `portfolio` and `scenario` class are shown in their respective parts of the application.
  * Scenarios with the `results` class are available for viewing in the results explorer.