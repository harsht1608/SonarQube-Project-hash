# SonarQube Project with Spring Boot

This project demonstrates the implementation of SonarQube code quality analysis with a Spring Boot application using Jenkins pipeline for CI/CD.

## Project Overview

This is a simple Spring Boot web application that serves as a demonstration for setting up:
- SonarQube code quality analysis
- Jenkins CI/CD pipeline
- Docker containerization
- Automated deployment

## Prerequisites

- JDK 17
- Maven 3.x
- Docker
- Jenkins
- SonarQube
- Ubuntu server (t2.large or equivalent)

## Tech Stack

- **Backend:** Spring Boot 2.7.5
- **Frontend:** Thymeleaf, HTML, CSS
- **Build Tool:** Maven
- **CI/CD:** Jenkins
- **Code Quality:** SonarQube
- **Containerization:** Docker
- **Server:** Ubuntu 24.04

## Local Development Setup

1. Clone the repository:
```bash
git clone https://github.com/YourUsername/SonarQube-Project-hash.git
cd SonarQube-Project-hash
```

2. Build the project:
```bash
mvn clean install
```

3. Run the application:
```bash
java -jar target/spotify-app-1.0.0.jar
```

The application will be available at `http://localhost:5555`

## Infrastructure Setup

### 1. Jenkins Setup

1. Install Jenkins on Ubuntu:
```bash
sudo apt install openjdk-17-jre-headless -y
# Follow Jenkins installation steps from Jenkins.io
```

2. Required Jenkins Plugins:
- SonarQube Scanner
- Eclipse Temurin installer
- Pipeline Stage View

### 2. SonarQube Setup

1. Install using Docker:
```bash
sudo apt install docker.io
sudo chmod 666 /var/run/docker.sock
docker run -d --name sonarqube -p 9000:9000 sonarqube:lts-community
```

2. Access SonarQube at: `http://<your-server-ip>:9000`
   - Default credentials: admin/admin

### 3. Jenkins Pipeline Configuration

1. Configure tools in Jenkins:
   - JDK 17
   - Maven 3
   - SonarQube Scanner

2. Add credentials:
   - SonarQube token
   - Docker Hub credentials

3. Configure SonarQube server in Jenkins:
   - Add SonarQube server details
   - Configure authentication token

## Deployment

The project uses a Jenkins pipeline for automated deployment:

1. Code checkout from Git
2. Compilation and testing
3. SonarQube analysis
4. Building JAR file
5. Docker image creation
6. Push to Docker Hub
7. Container deployment

## Application Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/
│   │       └── hash/
│   │           └── spotify/
│   │               ├── Application.java
│   │               └── HomeController.java
│   └── resources/
│       ├── static/
│       │   ├── css/
│       │   └── js/
│       └── templates/
│           └── index.html
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Kastro Kiran V

## Acknowledgments

- Spring Boot team
- SonarQube community
- Jenkins community
