This challenge walks you through the workflow of an enterprise DevOps engineer that wants to productize an application by creating a software delivery pipeline using Tekton.
The DevOps engineer will use the application that the Developer persona in the previous story created. The application is a simple service that connects to a database to store it’s stateful information. 

As the task is not meant to test your coding or operations skills, we’re going to provide you with the source code to use in a Git repository and the image to use for the database along with the deployment descriptors. This will provide all of the necessary components required to have a fully running application on a Kubernetes cluster. We will also provide you with an installer script that will install all the required capabilities on the cluster for you to use.

Your goal is to create a Pipeline that will fetch the source code, build a container image, push the image into a container registry, create a kubernetes namespace on the cluster and finally to deploy the application in that namespace. You should get a URL to verify that your application is live. You will then make a change in the application source code, and trigger the execution of the pipeline (manually or automatically). You should be able to see the change in the URL you had before.

Every application that needs to be productized should have at a minimum a pipeline like this. It’s what can be defined as a “basic intro pipeline”.


## Tasks
1. Create a Kubernetes cluster using TMC
1. Verify you can access your Kubernetes cluster (with kubectl)
1. Create a GitHub (or any other SCM) repository with the sample application
1. Build your pipeline
1. Deploy your pipeline to the cluster
1. Trigger your pipeline (manually)
1. Check that your pipeline finalises OK
1. Obtain the URL to the deployed application
1. Verify that the application is running fine
1. Make a change in the code and push the change to the SCM
1. Trigger the execution of the pipeline (manually)
1. Check that your pipeline finalises OK
1. Validate that your change is visible in the deployed application
1. You’ve done it!
