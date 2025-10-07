pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'  // Make sure this matches your Jenkins Maven tool name
    }

    environment {
        IMAGE_NAME = 'ashokit/mavenwebapp'  // Docker image name
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t $IMAGE_NAME ."
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s-deploy.yml'
            }
        }
    }
}
