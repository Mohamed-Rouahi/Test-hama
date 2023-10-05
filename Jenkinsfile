pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from the repository.
                script {
                    https://github.com/Mohamed-Rouahi/Test-hama.git
                    checkout scm
                }
            }
        }

        stage('Unit Tests') {
            steps {
                // Add commands to run your unit tests here using the 'sh' step.
                // For example, if you're using Maven for a Java project:
                 sh 'mvn clean test'
            }
        }

        // Add more stages for building, deployment, etc. as needed.
    }

    post {
        // Define post-build actions if necessary.
    }
}
