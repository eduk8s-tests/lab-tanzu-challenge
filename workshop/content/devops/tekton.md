The Tekton Pipelines project provides Kubernetes custom resource definitions for declaring CI/CD pipelines.

The custom resources needed to define a CI/CD pipeline using Tekton are listed below:
* `Task`: an ordered series of steps that perform a specific task (e.g. building a container image)
* `Pipeline`: a series of Tasks that can be performed in a particular order or in parallel
* `PipelineResource`: inputs (e.g. a git repository) and outputs (e.g. a container image) into and out of a Pipeline or Task
* `TaskRun`: the execution and result (i.e. success or failure) of running a Task
* `PipelineRun`: the execution and result (i.e. success or failure) of running a Pipeline

All of the above custom resources are namespaced, meaning they can only be created and run in a particular Kubernetes namespace. For example, to run a Pipeline (i.e. a PipelineRun), a Pipeline, the Tasks that are part of a Pipeline, and the PipelineRun and associated TaskRuns all must be present and run in the same namespace.

### Installation

Follow the Tekton pipelines [documentation for installating](https://github.com/tektoncd/pipeline/blob/master/docs/install.md#installing-tekton-pipelines) the Tekton pipeline component on your Kubernetes cluster.

### Helpful Tools

Some helpful tools for using Tekton:
* `tkn` - The Tekton CLI. [Installation instructions](https://github.com/tektoncd/cli#installing-tkn).
* `dashboard` - The Tekton UI. [Installation instructions](https://github.com/tektoncd/dashboard/blob/master/docs/install.md#installing-tekton-dashboard).
* `triggers` - Webhooks for Tekton. [Installation instructions](https://github.com/tektoncd/triggers/blob/master/docs/install.md#installing-tekton-triggers).
* `catalog` - Reusable example Tasks to use with Tekton. [Catalog link](https://github.com/tektoncd/catalog/tree/master/task).
* Tekton visual studio code extension can be found [here](https://github.com/redhat-developer/vscode-tekton#visual-studio-code-tekton-pipelines-extension--)
* General documentation on Tekton can be found [here](https://github.com/tektoncd/pipeline/tree/master/docs)

### Sample Application To Build and Deploy

The application you will be using is the famous [Spring Petclinic application](https://github.com/spring-projects/spring-petclinic). The pipeline you will create 
build the application into a container image, push the image to a registry, and deploy the application to a namespace that your pipeline will also create.
