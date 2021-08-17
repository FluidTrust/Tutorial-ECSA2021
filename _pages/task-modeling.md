---
permalink: /tasks/modeling
title: Modeling Task
header:
  image: /assets/images/feature_image_task_modeling.jpg
---

The goal of the modeling task is to get acquainted with the modeling concepts specific for confidentiality analyses.

## Material
* [Palladio tooling]({{ site.baseurl }}/material#palladio-drop)
* Modeling project `TravelPlanner_02_ModelingTaskRBAC` (already in tool workspace)
* [Tooling documentation]({{ site.baseurl }}/material#manual-on-using-palladio-drop) (optional)

## Scenario
The various roles involved in the architectural design already created all required Palladio models, which includes a repository, a system, a resource environment, an allocation and a usage model.

We decided to define a confidentiality policy in terms of Role-based Access Control (RBAC) to protect the transmitted information in the system. Two parties are involved in the current system: A user and his/her apps located on his/her smartphone and an airline. A user or system has to have at least one role, which grants access to a particular data item. In general, the user and the airline have access to all data except for credit card data (ccd). Access to the credit card data is only granted to the user.

Before we can analyze whether the architecture complies with this policy, we have to
* assign roles to users and system parts
* define the propagation of data characteristics

We already defined most of the propagation but we are not finished yet. Your task is to complete this specification.

## Task Instructions
Your task is to complete the existing specification.

All characteristics of nodes are missing. Create the missing characteristics as described in the following table.

| Model                | Element                     | Characteristic Type | Value   |
|----------------------|-----------------------------|---------------------|---------|
| Usage Model          | UsageScenario User          | AssignedRoles       | User    |
| Usage Model          | UsageScenario FlightPlanner | AssignedRoles       | Airline |
| Resource Environment | Resource Mobile             | AssignedRoles       | User    |
| Resource Environment | Resource AirlineServer      | AssignedRoles       | Airline |

Some assignments in the usage model are missing. Create the missing assignments as described in the following table.

| Usage Scenario | Action           | Variable Usage | Assignments                     |
|----------------|------------------|----------------|---------------------------------|
| User           | store ccd        | ccd            | `ccd.GrantedRoles.User := true` |
| User           | look for flights | query          | `query.GrantedRoles.* := true`  |

Some assignments in service effect specifications (SEFFs) are missing. Create the missing assignments as described in the following table.

| SEFF                                       | Action                       | Variable Usage | Assignments                                                      |
|--------------------------------------------|------------------------------|----------------|------------------------------------------------------------------|
| CreditCardCenterLogic:declassifyForAirline | return declassified ccd      | RETURN         | `RETURN.*.* := ccd.*.*`<br>`RETURN.GrantedRoles.Airline := true` |
| TravelPlanner:findFlights                  | request flights from airline | flights        | `flights.*.* := RETURN.*.*`                                      |
| TravelPlanner:findFlights                  | return found flights         | RETURN         | `RETURN.*.* := flights.*.*`                                      |

## Expected Results
You can compare your models with the models contained in the modeling project `TravelPlanner_03_ModeledRBAC`, which is already located in your Palladio tooling.