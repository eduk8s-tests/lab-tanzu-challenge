This challenge walks you through the workflow of an enterprise Operations engineer that wants to have a cluster with some additional capabilities so that the development teams can use it right away.

The Operations engineer will use a provided application (a simple service with a scale to zero configuration) and will monitor the application behavior through Tanzu Observability.

As the task is not meant to test your coding skills, we’re going to provide you with the source code to use in a Git repository along with the deployment descriptors to have the application built and then fully running on a Kubernetes cluster. You will need to adapt these, though, to your environment.

Your goal is to create a Kubernetes cluster and provision all the required capabilities for the application, deploy the provided application (adapted to your environment), and verify in Tanzu Observability that it runs fine.

Every application might have different requirements that the underlying cluster needs to satisfy. This challenge is what can be defined as a basic cluster setup.

The challenge today is to deploy a cluster, add KPack and Knative capabilities in order to (build an image from xyz registry and create a Knative Service), then configure TO and monitor how your application runs.