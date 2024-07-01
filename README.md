
# Recipe Management System

*Recipe Management System* is an MVC application that manages food recipes.

## Technology

*Recipe Management System* is using the following technologies:

- Java [version: 8] (the language used to write the application)
- Maven [version: 3.6] (the tool for managing dependencies and building the project)
- Spring-Boot [version: 2.2.5.RELEASE] (the framework for creating spring application that just runs)
- Spring-Boot-Data-JPA [version: 2.2.5.RELEASE] (the dependency for easier access and manipulation of a relational database)
- Spring-Boot-Thymeleaf [version: 2.3.0 Release] (the Java template engine for both web and standalone environments)

## Setup

Execute the following commands:

- mvn clean install (to build the project)
- mvn spring-boot:run (to run the project)

Access application in url below:

- http://localhost:8080/recipes [Http method: GET] (home page of recipes application)

### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.2.4/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.2.4/maven-plugin/reference/html/#build-image)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#using.devtools)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#web)
* [Thymeleaf](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#web.servlet.spring-mvc.template-engines)
* [Spring Data JPA](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#data.sql.jpa-and-spring-data)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Handling Form Submission](https://spring.io/guides/gs/handling-form-submission/)
* [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)
* [Accessing data with MySQL](https://spring.io/guides/gs/accessing-data-mysql/)

```
recipes/
├── mvnw
│   ├── mvnw.cmd
│   ├── pom.xml
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── edu/
│   │   │       └── pes/
│   │   │           └── recipes/
│   │   │               ├── controller/
│   │   │               │   ├── HomeController.java
│   │   │               │   └── RecipeController.java
│   │   │               ├── model/
│   │   │               │   ├── Recipe.java
│   │   │               │   └── RecipeRepository.java
│   │   │               ├── service/
│   │   │               │   ├── RecipeService.java
│   │   │               │   └── RecipeServiceInterface.java
│   │   │               ├── RecipeManagementSystemApplication.java
│   │   │               └── ServletInitializer.java
│   │   └── resources/
│   │       ├── static/
│   │       │   ├── css/
│   │       │   │   └── (various CSS files)
│   │       │   ├── js/
│   │       │   │   └── (various JS files)
│   │       ├── templates/
│   │       │   ├── edit-recipe.html
│   │       │   ├── error.html
│   │       │   ├── home.html
│   │       │   ├── new-recipe.html
│   │       │   ├── recipes.html
│   │       │   └── view-recipe.html
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── edu/
│               └── pes/
│                   └── recipes/
│                       └── RecipeManagementSystemApplicationTests.java
│
├── .mvn/
│   └── wrapper/
│       ├── maven-wrapper.jar
│       └── maven-wrapper.properties
│
├── Dockerfile
│
├── pipelines/
│   ├── build.jenkins
│   └── deployment.jenkins
│
├── kubernetes/
│   └── manifest/
│       ├── mysql-deployment.yaml
│       ├── mysql-pv.yaml
│       ├── mysql-pvc.yaml
│       ├── mysql-secret.yaml
│       ├── mysql-service.yaml
│       ├── namespace.yaml
│       └── springboot-deployment.yaml
│       └── springboot-configmap.yaml
│
├── .gitignore
├── README.md
```

# Recipe Management System

The Recipe Management System is a web application designed to streamline the process of managing and sharing food recipes. It provides a user-friendly interface for users to create, view, edit, and delete recipes. With features such as ingredient lists, cooking instructions, and difficulty levels, users can easily organize and access their favorite recipes.

## Key Features

- **Recipe CRUD Operations**: Users can perform basic CRUD (Create, Read, Update, Delete) operations on recipes.
- **User-friendly Interface**: The application offers an intuitive interface for users to navigate and interact with recipes effortlessly.
- **Thymeleaf Templates**: Utilizing Thymeleaf templates, the frontend is dynamically generated, providing a seamless user experience.
- **MySQL Integration**: The application integrates with MySQL database to store recipe data securely.
- **Docker Support**: Dockerization allows for easy deployment and scalability of the application across different environments.
- **Kubernetes Deployment**: Kubernetes manifests facilitate the deployment and management of the application in a Kubernetes cluster.
- **Jenkins Pipelines**: Jenkins pipelines automate the build, test, and deployment processes, ensuring efficiency and consistency in the development lifecycle.

---
README that includes the steps and resources for setting up MySQL and integrating it with your Recipe Management System. I’ve also included a section for adding your existing files as points:
---

## 1st Way to Deploy: Setting Up MySQL for Recipe Management System

This guide outlines the steps to set up MySQL, configure it for your Recipe Management System, and integrate it with a Spring Boot application using Kubernetes. Follow these steps to get everything up and running.

### Step 1: Pull MySQL Image and Create a Single Instance MySQL Deployment

1. **Pull the MySQL Docker Image**  
   Use the official MySQL Docker image to create a MySQL instance. Follow these [documentation steps](https://medium.com/@midejoseph24/deploying-mysql-on-kubernetes-16758a42a746) for pulling the image and creating the deployment.

2. **Create MySQL Kubernetes Resources**  
   Follow these [Kubernetes guidelines](https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/) for setting up a single instance MySQL deployment.

   - **mysql-deployment.yaml**  
     Defines the MySQL deployment.
   - **mysql-service.yaml**  
     Configures the MySQL service with NodePort.

   Place these files in the `optit-lab-springmvc-example/recipes/kubernetes/manifests/` directory:
   - `mysql-deployment.yaml`
   - `mysql-service.yaml`
   - `mysql-secret.yaml` (for storing MySQL credentials)
   - `mysql-storage.yaml` (for configuring persistent storage)
   - `mysql-pv.yaml` (for the Persistent Volume)
   - `mysql-pvc.yaml` (for the Persistent Volume Claim)

   ```bash
   kubectl apply -f mysql-pv.yaml
   kubectl apply -f mysql-pvc.yaml
   kubectl apply -f mysql-deployment.yaml
   kubectl apply -f mysql-service.yaml
   kubectl apply -f mysql-secret.yaml
   ```

3. **Verify Microservices**  
   Ensure that all microservices are in the running state after applying the configurations:

   ```bash
   kubectl get pods
   ```

### Step 2: Configure the Spring Boot Application

1. **Update Application Properties**  
   Edit the `application.properties` file to configure the database connection settings:

   ```properties
   spring.datasource.url=jdbc:mysql://<mysql-service-ip>:<mysql-service-port>/recipe_management
   spring.datasource.username=<your-username>
   spring.datasource.password=<your-password>
   ```

2. **Build the Spring Boot Application**  
   Use Maven to clean and install the application:

   ```bash
   mvn clean install -X
   ```

   Ensure the build is successful. 

### Step 3: Create Dockerfile and Build Docker Image

1. **Create a Dockerfile**  
   Use the Maven snapshot file to create a Dockerfile for your application:

   ```dockerfile
   FROM openjdk:11-jre-slim
   COPY target/your-application-snapshot.jar /app/your-application.jar
   ENTRYPOINT ["java", "-jar", "/app/your-application.jar"]
   ```

2. **Build the Docker Image**

   ```bash
   docker build -t your-application-image:latest .
   ```

### Step 4: Update Kubernetes Manifests for Spring Boot Application

1. **Add the Docker Image to Kubernetes Manifests**  
   Update `springboot-deployment.yaml` with the newly created Docker image.

2. **Apply Kubernetes Configurations**  

   ```bash
   kubectl apply -f springboot-deployment.yaml
   kubectl apply -f springboot-service.yaml
   kubectl apply -f ingress.yaml
   ```

### Step 5: Create a CI/CD Pipeline for Automation

1. **Set Up a CI/CD Pipeline**  
   Create a pipeline to automate the build and deployment processes. This includes automating Docker builds and Kubernetes deployments.

   Consider using tools like Jenkins, GitLab CI/CD, or GitHub Actions for this step.

### File Directory Structure

Your Kubernetes manifest files and their purpose:

- **`mysql-storage.yaml`**  
  - Configuration for MySQL persistent storage.

- **`mysql-deployment.yaml`**  
  - Defines the MySQL deployment.

- **`mysql-secret.yaml`**  
  - Contains MySQL credentials.

- **`mysql-service.yaml`**  
  - Configures the MySQL service.

- **`mysql-pv.yaml`**  
  - Defines the Persistent Volume for MySQL.

- **`mysql-pvc.yaml`**  
  - Defines the Persistent Volume Claim for MySQL.

- **`springboot-deployment.yaml`**  
  - Deployment configuration for the Spring Boot application.

- **`springboot-service.yaml`**  
  - Service configuration for the Spring Boot application.

- **`ingress.yaml`**  
  - Configures ingress rules for external access to the application.

### Resources

- [Deploying MySQL on Kubernetes](https://medium.com/@midejoseph24/deploying-mysql-on-kubernetes-16758a42a746)
- [Kubernetes Single Instance Stateful Application](https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/)

### Summary

1. Deploy MySQL using the provided documentation.
2. Configure your `application.properties` file for MySQL.
3. Build the application and create a Docker image.
4. Update Kubernetes manifests and deploy the microservices.

By following these steps, you will have a fully deployed MySQL instance and microservices running on Kubernetes.

# 2nd way to deploy[download and install mysql in local machine]
## DevOps Engineering Practices

As a DevOps engineer, here are key practices to incorporate into the Recipe Management System:

1. **Continuous Integration and Delivery (CI/CD)**: Implement CI/CD pipelines using Jenkins to automate the build, test, and deployment processes. This ensures faster delivery of updates and improvements to the application.

2. **Infrastructure as Code (IaC)**: Define infrastructure components, such as Kubernetes manifests, in code to enable reproducibility and consistency in deployment environments.

3. **Containerization with Docker**: Dockerize the application to encapsulate dependencies and ensure consistency across different environments, from development to production.

4. **Orchestration with Kubernetes**: Utilize Kubernetes for container orchestration, enabling efficient deployment, scaling, and management of containerized applications.

5. **Monitoring and Logging**: Implement monitoring and logging solutions to gain insights into application performance, identify issues, and troubleshoot effectively.

6. **Security Best Practices**: Apply security best practices, such as securing database connections, implementing access controls, and scanning container images for vulnerabilities, to protect the application and its data.

By incorporating these DevOps practices, you can enhance the development, deployment, and operations of the Recipe Management System, ensuring reliability, scalability, and security.


### MySQL Installation and Configuration [local einstall and configure]

1. **Install MySQL**: Start by installing MySQL on your system. You can download MySQL Community Server from the official website or use a package manager like Homebrew on macOS or apt on Ubuntu.

2. **Start MySQL Service**: After installation, start the MySQL service on your system. On Unix-based systems, you can do this using the `systemctl` command:
   ```bash
   systemctl start mysql
   ```

3. **Secure MySQL Installation**: Run the MySQL secure installation script to enhance the security of your MySQL installation. This script prompts you to set a root password, remove anonymous users, disallow root login remotely, and remove the test database.
   ```bash
   mysql_secure_installation
   ```

4. **Create Database and User**: Log in to MySQL as the root user and create a database for your Recipe Management System. Also, create a user and grant privileges to that user on the newly created database.
   ```bash
   mysql -u root -p

   mysql> CREATE DATABASE recipes_db;
   mysql> CREATE USER 'recipes_user'@'%' IDENTIFIED BY 'password';
   mysql> GRANT ALL PRIVILEGES ON recipes_db.* TO 'recipes_user'@'%';
   mysql> FLUSH PRIVILEGES;
   mysql> EXIT;
   ```

5. **Update application.properties**: Update the `application.properties` file in your Spring Boot application's `src/main/resources` directory with the MySQL database connection details.
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/recipes_db
   spring.datasource.username=recipes_user
   spring.datasource.password=password
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
   spring.jpa.hibernate.ddl-auto=update
   ```

6. **Verify Connection**: Restart your Spring Boot application and verify that it successfully connects to the MySQL database. You can check the console logs for any connection errors.

### Jenkins Pipeline Setup

Now, let's set up Jenkins pipelines for building and deploying your Spring Boot application along with MySQL in Kubernetes.

#### build.jenkins

1. **Clone Repository**: Start by cloning your Recipe Management System repository to Jenkins workspace using Git.
   ```groovy
   git 'https://github.com/your-username/recipes.git'
   ```

2. **Build Docker Image**: Use the Dockerfile in the repository to build a Docker image for your Spring Boot application.
   ```groovy
   sh 'docker build -t your-dockerhub-username/recipes:latest .'
   ```

3. **Push Docker Image**: Push the built Docker image to Docker Hub to make it accessible for deployment.
   ```groovy
   sh 'docker push your-dockerhub-username/recipes:latest'
   ```

#### deployment.jenkins

1. **Deploy MySQL in Kubernetes**: Apply the MySQL Kubernetes manifests located in the `kubernetes/manifest` directory to deploy MySQL in your Kubernetes cluster. These manifests define resources like Deployment, PersistentVolume, PersistentVolumeClaim, and Service for MySQL.
   ```groovy
   sh 'kubectl apply -f kubernetes/manifest/mysql-deployment.yaml'
   ```

2. **Deploy Spring Boot Application**: Apply the Kubernetes manifests for your Spring Boot application, including Deployment and Service definitions. These manifests ensure your application is deployed and access
By incorporating these DevOps practices, you can enhance the development, deployment, and operations of the Recipe Management System, ensuring reliability, scalability, and security.
ible within the Kubernetes cluster.
   ```groovy
   sh 'kubectl apply -f kubernetes/manifest/springboot-deployment.yaml'
   ```

3. **Verify Deployment**: Check the Kubernetes dashboard or use kubectl commands to verify that both MySQL and your Spring Boot application are successfully deployed and running in the cluster.

By following these steps, you'll have MySQL installed, configured, and integrated with your Spring Boot application, along with Jenkins pipelines set up for building and deploying your application in Kubernetes.
