pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from the repository.
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']], // You can specify the branch you want to build here.
                    userRemoteConfigs: [[url: 'https://github.com/Mohamed-Rouahi/Test-hama.git']]
                ])
            }
        }



        // Add more stages for building, deployment, etc. as needed.
    }

    post {
        failure {
            emailext subject: 'Build Failure Notification',
                    body: 'The build failed. Please check the Jenkins console output for details.',
                    to: 'mohamed.rouahi@eprit.tn'
        }
    }
}
