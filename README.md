# Structuring-Microservices-Projects
Quick guide to structure your microservices project

## What is a Microservice Architecture?
Microservice architecture is a form of service-oriented architecture (SOA) whereby software applications are built as a collection of loosely coupled services, as opposed to one monolithic software application.  Each microservice can be created independently from the other, or even in a completely different programming language and run on their own.

Modularising software this way makes the source code easier to understand and follow, developers can visualize the codebase and know roughly where to look for defects – thereby making maintenance more efficient. Software systems built using microservices architecture are also easier to scale as the number of users increase.

![alt text](https://www.devteam.space/wp-content/uploads/2018/04/image006-1.jpg)

In the sample microservice architecture above, you can see the following 3 microservices:

- Account Service
- Inventory Service
- Shipping Service

Here each microservice is accessed in one of two ways in this fictitious application:

- From an API gateway (via a mobile app)
- From a Web application (via the user’s web browser)

Each microservice also exposes a dedicated REST API. For example, the Inventory service REST API definition may contain an endpoint called GetAllProducts which allows consumers of the microservice to fetch all products in the e-commerce store, this could return a list of Product objects is JSON, XML or even C# POCO.

## Advantages of a Microservice Architecture
- More efficient debugging – no more jumping through multiple layers of an application, in essence, better fault isolation.
- Accelerated software delivery – multiple programming languages can be used thereby giving you access to a wider developer talent pool.
- Easier to understand the codebase.
- Reusability – as microservice are organized around business cases and not a particular project, due to their implementation, they can be reused and easily slotted into other projects or services, thereby reducing costs.
- Fault tolerance – reduced downtime due to more resilient services.
- Deployment – as everything is encapsulated into separate microservices, you only need to deploy the services that you’ve changed and not the entire application.

## Example Project Structure
<p align="left">
  <img src="https://github.com/NitheshSinghSanjay/Structuring-Microservices-Projects/blob/master/microservices_structure.PNG" width="350" title="Sample Microservices Project Structure">
</p>

Above picture shows the project structure of a simple python microservice using Flask.
- **Public** folder contains your public html files to be rendered.
- **Server**
     - **Config** folder contains basic server configurations.
     - **Database** folder contains database/models specific to microservices.
     - **Routes** folder contains all the route definitions.
     - **Services** folder contains all your microservices files.
- **Tests** folder contains the test code for your project.
- **manage.py** offers a variety of different run commands to match the proper situation:
     - start: starts a server in a production setting using gunicorn.
     - run: starts a native Flask development server.
     - build: compiles .py files within the project directory into .pyc files.
     - test: runs all unit tests inside of the project's test directory.

### Example projects to folllow for proper structuring
Below are some examples of python microservices projects you can follow to get a better understanding of the project structuring. You can also go through the code to understand how different core functions/components are segregated for better readability.

- https://github.com/umermansoor/microservices
- https://github.com/IBM/flask-microservice
