# LawSearch - incident report error due to bad deployment
**Posted:** Saturday, May 9 2020

By: Camilo Bayona

### Issue Summary

On Saturday at 1:00 PT we started receiving previously configured alerts from one of our servers that indicated a 500 error from our backend servers.

For this reason, the service that performs the data extraction stopped responding to 40% of our users until 03:00 PT, due to an error in the update of said service, we apologize for the service drop and we inform you of the measures taken.

### Timeline (all times Pacific Time)
(format bullet point, format: time - keep it short, 1 or 2 sentences) must contain:

* 01:00: We received the first alert that the service was stopped.
* 01:07: Review begins.
* 01:07: The work is divided into groups to review suspicious parties.
* 01:45: One of the groups reports a specific error in the code because a bad deployment.
* 02:10: Bug is fixed and pre-deployment tests are started.
* 02:15: Correction is made and deployment starts again.
* 02:30: All services are verified and work correctly.

### Root cause

At 01:07, once the work was divided, the group in charge of reviewing the automatic deployment, realized that they have an excessively long deployment process and that it must be approved by several people.

This allowed us to infer a possible failure during the entire process, which is why efforts were doubled in this section of the infrastructure, which allowed us to find the error twice as fast as we had previously organized.

### Resolution

One of the groups realized that a configuration in the tests carried out prior to deployment was modifying the code that allowed the test to pass correctly and go into production without being manually revised.


### Corrective measures

It is suggested to correct the automatic deployment policies and avoid making changes to functions that are so important for the operation of the system.

It is also suggested a manual review of the deployments before implementing the implementation in transcendental functions.


### Preventative measures

It is suggested to configure alerts that inform when the code changes automatically for some configuration.

Having a more robust automatic deployment service that allows deeper configurations that avoid these inconveniences.