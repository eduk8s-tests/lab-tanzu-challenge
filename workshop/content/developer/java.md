For this challenge, you're going to develop a Java application. We know you might not know any Java, and we don't expect you to do any coding, but since it's the most popular language on the Enterprise and since we provide Spring as a VMware product, we thought you should definitely try the experience for these type of developers.

Before you can get started, you will need to have Java installed on your local machine. To ease you the process of getting started we provide you with the easiest way to get it installed on your machine, so that later you can remove it.

[SDKman](https://sdkman.io/) provides the easiest way for you to install the Java required tools, that is the JDK (compiler) and Maven (build tools).

These are the [instructions on how to install SDKman](https://sdkman.io/install) on your laptop. Once you have it installed, you can install Java JDK and Maven with these 2 commands:

```copy
sdk install java 11.0.2-open
sdk install maven
```

The application you will be using is the famous [Petclinic application](https://github.com/spring-projects/spring-petclinic). So go ahead, and clone this repository to your local laptop.

## First time Java users
If this is your first time with Java, we understand you might not know how to build the application. It's an easy command:

```copy
./mvnw package
```

This will create a file [target/spring-petclinic-2.3.1.BUILD-SNAPSHOT.jar] that is your SpringBoot application that you will need to run.

You can test your application locally by doing:

```copy
./mvnw spring-boot:run
```

This will start your application and make it accesible on port 8080, so to verify that it deployed correctly, you can access try [this link](http://localhost:8080)

Now it's time for you to get it to run in Kubernetes. For this part of the exercise, we will only give you a list of steps, since the goal of this challenge is that you do this yourself without further guidance.

You will need to:
* Create a container image. You can use for this task:
    * A dockerfile
    * SpringBoot image building capabilities
    * [Cloud Native Build Packs](https://buildpacks.io/)
* Create your deployment descriptors that will deploy your application on your Kubernetes cluster
* Deploy a database. Spring Petclinic app will connect easily to a MySQL database. You will find more details [here](https://github.com/spring-projects/spring-petclinic#database-configuration). [This docker-compose file](https://github.com/spring-projects/spring-petclinic/blob/main/docker-compose.yml) will give you more details on the required ENV variables that you will need.
* Connect your application to your database. Now that you have a database up and running, you should be able to connect to that database from within your Spring Petclinic application. In the previous links you will have information on how to do that.


At this point you have built and deployed an application into your Kubernetes cluster. But this is not all. Since developers typically go through what is called `[inner loop](https://mitchdenny.com/the-inner-loop/)` many times a day, we want you to also experience that part of their day to day.

For this, you would need to use one of the following tools (you choose):
* [Skaffold](https://skaffold.dev/)
* [Tilt](https://tilt.dev/)
* [Devspace](https://devspace.sh/)
* [Okteto](https://okteto.com/docs/reference/cli#up)
* [Garden](http://garden.io/)
* [Odo](https://odo.dev/)

Once you have choosed the tool and get a grasp on how it works, you will need to:
* Configure your local clone to work with the tool
* Make a change in your code
* Push the change to your running app
* See the change live

As we understand that you might not know what to change, we propose you two options:

* Change a message that is displayed on the main page for the application. Locate [this file and edit the first line](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/resources/messages/messages.properties#L1)
* Change Java code. [Locate and change this line](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/java/org/springframework/samples/petclinic/system/CrashController.java#L34). This code is displayed when you click on the `Error` menu item on the main page for the application.