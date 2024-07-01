
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

###1st way to deploy.
adding soon... 










###2nd way to deploy[download and install mysql in local mchine]
## DevOps Engineering Practices

As a DevOps engineer, here are key practices to incorporate into the Recipe Management System:

1. **Continuous Integration and Delivery (CI/CD)**: Implement CI/CD pipelines using Jenkins to automate the build, test, and deployment processes. This ensures faster delivery of updates and improvements to the application.

2. **Infrastructure as Code (IaC)**: Define infrastructure components, such as Kubernetes manifests, in code to enable reproducibility and consistency in deployment environments.

3. **Containerization with Docker**: Dockerize the application to encapsulate dependencies and ensure consistency across different environments, from development to production.

4. **Orchestration with Kubernetes**: Utilize Kubernetes for container orchestration, enabling efficient deployment, scaling, and management of containerized applications.

5. **Monitoring and Logging**: Implement monitoring and logging solutions to gain insights into application performance, identify issues, and troubleshoot effectively.

6. **Security Best Practices**: Apply security best practices, such as securing database connections, implementing access controls, and scanning container images for vulnerabilities, to protect the application and its data.

By incorporating these DevOps practices, you can enhance the development, deployment, and operations of the Recipe Management System, ensuring reliability, scalability, and security.

# mysql [2ways]
To set up MySQL and configure it for your Recipe Management System, follow these comprehensive steps:
###pull image and create single instance mysql file
look for documentation



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
