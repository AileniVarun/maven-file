pipeline {
    agent any

    options {
        // Clean the workspace before checkout
        skipDefaultCheckout()  // skip automatic checkout
        // clean before checkout
        wipeWorkspace()
    }

    tools {
        maven 'MAVEN_HOME'
    }

    stages {
        stage('Checkout') {
            steps {
                // Manual checkout here after cleaning
                checkout scm
            }
        }

        stage('Build with Maven') {
            steps {
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
