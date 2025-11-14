# Netflix Java CI/CD Pipeline with Maven, Jenkins & Tomcat

## Overview
This project features a Java-based Netflix-style application demonstrating a full CI/CD pipeline using GitHub, Jenkins, Maven, and Tomcat. It covers the entire development lifecycle—from source code management, automated builds, testing, continuous integration, to deployment on a Tomcat server.

## Features
- Java application mimicking core Netflix functionalities
- Build automation with Maven
- Continuous Integration and Deployment via Jenkins
- Deployment on Apache Tomcat server
- Source code managed and versioned through GitHub

## Prerequisites
Before running this project, ensure you have:
- Java JDK installed (compatible version)
- Maven installed
- Jenkins server setup and configured
- Apache Tomcat server installed and running
- Git client installed

## Getting Started

### Clone the Repository
```
git clone https://github.com/Pratik543/netflix-java-deployment-automation.git
cd netflix-java-deployment-automation/
```

### Build Application
Use Maven to build the project:
```
mvn clean package
```

### Configure Jenkins
- Create a pipeline job in Jenkins
- Connect to this GitHub repository
- Configure build triggers (e.g., on Git push)
- Set build steps to use Maven goals like `clean package`
- Add post-build steps to deploy the WAR file to Tomcat

### Deploy on Tomcat
- Copy the generated `.war` file from `target/` directory to Tomcat's `webapps` directory
- Start/restart Tomcat server
- Access the application via `http://localhost:8080/your-app-context`

## CI/CD Workflow
- Code changes pushed to GitHub trigger Jenkins build
- Jenkins pulls code, runs Maven build and tests
- Successful builds deploy artifacts to Tomcat automatically

## Contributing
Contributions are welcome! Feel free to submit pull requests or open issues.

---

Built with ❤️ for learning and mastering Java app deployment with CI/CD pipelines.
