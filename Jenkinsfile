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
        stage('Send Email') {
            steps {
                script {
                    def commitMessage = sh(script: "git log -1 --pretty=format:'%h %s'", returnStatus: true).trim()
                    emailext (
                        subject: "Nouveau commit sur le dépôt",
                        body: "Un nouveau commit a été effectué sur le dépôt.\n\nDétails du commit :\n\n${commitMessage}",
                        to: "mohamed.rouahi@esprit.tn,sabri.abassi@esprit.com",
                        attachLog: true,
                    )
                }
            }
        }



        // Add more stages for building, deployment, etc. as needed.
    }

}


