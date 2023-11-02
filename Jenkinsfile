pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                script {
                    def scmVars = checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/SyedaMaheen888/APP_repo.git']]])
                }
            }
        }

        stage('Build') {
            steps {
                // You can add your build commands here
                sh 'echo "Building the project"'
            }
        }

        stage('Test') {
            steps {
                // You can add your test commands here
                sh 'echo "Running tests"'
            }
        }

        stage('Deploy') {
            when {
                // Add conditions for when to deploy, e.g., after a successful build and test
                expression { currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
            }
            steps {
                // You can add deployment steps here
                sh 'echo "Deploying the application"'
            }
        }
    }


}
