pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'  // Your configured Maven tool name
    }

    stages {
        stage('Clean Workspace') {
            steps {
                // Clean the workspace before build to avoid leftovers
                deleteDir()
            }
        }

        stage('Build with Maven') {
            steps {
                // Runs mvn clean install on the checked out repo
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
    }
}
