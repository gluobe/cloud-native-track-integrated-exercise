# Cloud Native Track - Integrated Exercise

## Goal

The goal of this exercise is to put everything you have learned these 2 days in 
practice.  The workshops should have prepared you most of the exercise, however 
you might have to do some Googling yourself as well.

In this exercise you will need to run your application (Spring Boot) and 
database (Postgres) into an OpenShift cluster.

## Exercise

### Task 1:

The steps below can be executed using the UI, the main goal is to get your
application up-an-running inside OpenShift:

* create your own OpenShift project on the cluster
* use the Docker image / `Dockerfile` that you created yesterday
* deploy a Postgres DB into your OpenShift project
* deploy your application into your OpenShift project
* find a way to dynamically inject your configuration into your application
* expose your application to the outside world
* post the public link to Slack

### Task 2:

This task focusses on removing the manual actions required to deploy your 
application + database.  In this task you will need to get your hands dirty and
write some YAML.

What you should end up with is a single YAML that you can `oc apply` to deploy 
your stack (application + database).

As a pointer, at the minimum your YAML should contain the following objects:

* deploymentconfig (application)
* service (application)
* route (application)
* configmap (application)
* deploymentconfig (database)
* service (database)

### Task 3:

The goal of this task is to optimise the YAML you created in the previous task, 
add the following to your yaml:

* liveness probe
* readiness probe
* requests
* limits
* secret
* CI/CD
* SSL

## Resources

Some useful resources:

* OpenShift docs: https://docs.openshift.com
* Kubernetes website: https://kubernetes.io/docs/home/
* Kubernetes API: https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/

Specifics:

* Liveness/Readiness probes:
    * https://docs.openshift.com/container-platform/3.11/dev_guide/application_health.html
    * https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/
* Requests/Limits:
    * https://docs.openshift.com/container-platform/3.11/dev_guide/compute_resources.html#dev-compute-resources
    * https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/
* deploymentconfig
    * https://docs.openshift.com/container-platform/3.11/dev_guide/deployments/how_deployments_work.html