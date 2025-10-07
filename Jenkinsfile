pipeline {
    agent any

    tools {
        maven 'MAVEN-HOME' 
    }

    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }

        stage('Clone Repository') {
            steps {
                // Clone your repo into "mavenjava" folder
                bat 'git clone https://github.com/AileniVarun/maven-file.git mavenjava'
            }
        }

        stage('Clean Maven Project') {
            steps {
                bat 'mvn clean -f mavenjava\\pom.xml'
            }
        }

        stage('Install') {
            steps {
                bat 'mvn install -f mavenjava\\pom.xml'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test -f mavenjava\\pom.xml'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package -f mavenjava\\pom.xml'
            }
        }
    }
}
