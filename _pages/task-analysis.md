---
permalink: /tasks/analysis
title: Analysis Task
header:
  image: /assets/images/feature_image_task_analysis.jpg
---

The goal of the analysis task is to get acquainted with the user interface for conducting confidentiality analyses.

## Material
* [Palladio tooling]({{ site.baseurl }}/material#palladio-drop)
* Modeling project `TravelPlanner_04_ModeledRBACWithIssue` (already in tool workspace)
* [Tooling documentation]({{ site.baseurl }}/material#manual-on-using-palladio-drop) (optional)

## Scenario
You completely specified the characteristics of nodes and data in the previous task. In addition, you created the query for checking the compliance of the architecture with the RBAC policy and wrote it into the file `travelPlanner.DCPDSL`. Only the run configuration to execute the analysis is still missing. Therefore, you have to create it.

Side note: In the meantime, the domain expert adjusted the usage model without consulting you. We will check if this change violates the policy by running the analysis.

## Task Instructions
Your task is to create and run a run configuration. Create a new run configuration (ignore existing ones) and refer to the requested models and files from the `TravelPlanner_04_ModeledRBACWithIssue` project. As a result file, define the file `result.txt` in the `TravelPlanner_04_ModeledRBACWithIssue` project. Afterwards, run the analysis. Inspect the result file and try to find the cause of the violation.

The project `TravelPlanner_05_RBACAnalysis` contains a fixed version of the model. You can run the corresponding analysis by running the run configuration `TravelPlanner_RBAC`. Have a look at the produced result.

## Expected Results
The result file `result.txt` should be created in the `TravelPlanner_04_ModeledRBACWithIssue` project. It should report a violation when sending the credit card data to the flight booking service of the Airline. This is a problem because the declassification step is missing from the usage scenario of the user.

You can compare the output with the result of the run configuration `TravelPlanner_RBACWithIssue` that creates a file `result.txt` in the project `TravelPlanner_06_RBACAnalysisWithIssue`. The results should be the same.

In contrast, the results in the correctly modeled project `TravelPlanner_05_RBACAnalysis` should not indicate a violation.