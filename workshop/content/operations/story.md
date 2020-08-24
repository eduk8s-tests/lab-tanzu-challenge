This challenge walks you through the workflow of an enterprise Operations engineer that wants to have a cluster with some additional capabilities so that the development teams can use it right away.

The Operations engineer will use the provided application (a simple service with a scale to zero configuration) that will use the required capabilities and will monitor the application behavior through Tanzu Observability.

As the task is not meant to test your coding skills, we’re going to provide you with the source code to use in a Git repository along with the deployment descriptors to have the application built and then fully running on a Kubernetes cluster. You will need to adapt these, though, to your environment.

Your goal is to create a Cluster and provision all the required capabilities for the application, deploy the provided application (adapted to your environment) and verify in Tanzu Observability that it runs fine.

Every application might have different requirements that the underlying cluster needs to satisfy. This challenge is what can be defined as a “basic cluster setup”.

Deploy a cluster, add KPack and Knative capabilities in order to (build an image from xyz registry and create a KSVC), then configure TO and monitor how your application runs. 

## Tasks
1. Create a Kubernetes cluster using TMC or TKG
1. Verify you can access your Kubernetes cluster (with kubectl)
1. Deploy the following capabilities onto the cluster:
    * Contour
    * A container registry
    * KPack
    * Knative
    * Configure Tanzu Observability for your cluster
1. Use the build descriptor (adapted to your cluster) to build an image that will be pushed into the registry you provisioned
1. Use the deployment descriptor (adapted to your cluster) to deploy the application onto the cluster
1. Verify that the application scales to one when accessed
1. Verify that the application scales to zero after some inactivity time
1. Open Tanzu observability and monitor your cluster from it
1. In Tanzu Observability you should also see information about your application
1. You’ve done it!
