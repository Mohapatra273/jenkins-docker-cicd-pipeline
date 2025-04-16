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
            }
        }
        stage('Docker Build & Push') {
            steps {
                sh 'docker build -t mohapatra273/sample-app .'
                sh 'docker push mohapatra273/sample-app'
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 8080:8080 mohapatra273/sample-app'
            }
        }
    }
}
