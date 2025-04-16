# Jenkins CI/CD Pipeline with Docker and GitHub Integration

This project demonstrates a complete CI/CD workflow using Jenkins, Docker, and GitHub. It automates application build, test, image creation, and container deployment.

## 🚀 Tools Used
- Jenkins (Pipeline-as-Code)
- Docker
- GitHub
- Maven (Java build tool)

## ⚙️ CI/CD Pipeline Flow
1. Developer pushes code to GitHub
2. GitHub webhook triggers Jenkins job
3. Jenkins builds the code using Maven
4. Docker image is built and pushed to Docker Hub
5. Container is deployed automatically
6. Notifications sent on job success/failure

## 📁 Jenkinsfile (Pipeline Script)
```groovy
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Mohapatra273/sample-java-app.git'
            }
        }
        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
