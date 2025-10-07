pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'  // Make sure this matches your Maven installation in Jenkins
    }

    stages {
        stage('Clone Repository & Clean') {
            steps {
                // Remove old project folder (if exists)
                bat 'rmdir /s /q mavenjava'

                // Clone repo from GitHub
                bat 'git clone https://github.com/ashokitschool/maven-web-app.git mavenjava'

                // Clean Maven project
                bat 'mvn clean -f mavenjava/pom.xml'
            }
        }

        stage('Install') {
            steps {
                bat 'mvn install -f mavenjava/pom.xml'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test -f mavenjava/pom.xml'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package -f mavenjava/pom.xml'
            }
        }
    }
}
