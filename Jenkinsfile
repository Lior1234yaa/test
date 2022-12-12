pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                // add test if file exist
                echo 'Testing..'
                sh "cat mybash.sh"
                sh "ls -a | grep 'mybash.sh'"
            }
        }
        stage('Build') {
            steps {
                // build kit
                echo 'Build....'
                sh "zip target.zip mybash.sh"
            }
        }
        stage('DeployToNexsus') {
            steps {
                echo 'Deploy....'
                sh "ls -a"
                println ${BUILD_NUMBER}
            }
        }

    }
}