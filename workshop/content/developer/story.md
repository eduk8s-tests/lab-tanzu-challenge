This challenge walks you through the workflow of an enterprise developer that needs to deploy his first application to Kubernetes. It’s a simple service that uses a database to store information. As part of this challenge you will experience the inner loop workflow, that is starting from zero on your local laptop all the way to having a running application. The inner loop refers to the quick iterative development that happens before you push your code to a git repository. The objective of the challenge is a working application that you have developed and tested on a Kubernetes cluster and that can be shared/producticed via a URL.

As the challenge is not meant to test your coding skills, the source code will be provided for you. Your goal is to deploy the application to Kubernetes and make a change to the code base in order to see how that change is applied into your running application. This is the first step most developers would go through when targeting kubernetes as their deployment platform. It’s what can be defined as “developer day-1 workflow”

## Tasks
1. Create a Kubernetes cluster using TMC
1. Verify you can access your Kubernetes cluster (with kubectl)
1. Unzip the provided source code into a folder on your laptop
1. Create deployment descriptors
1. Build your application into a container image
1. Deploy your application to the cluster
1. Expose your application with a URL
1. Check that your application is running
1. Deploy a database of type X (using whatever mechanism you see fit)
1. Connect your application to the database
1. Access your application and test that it connects to your database
1. Make a change in the code and deploy the new version
1. Validate that your change is visible
1. You’ve done it!
